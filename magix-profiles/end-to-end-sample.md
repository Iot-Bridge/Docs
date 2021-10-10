## End-to-end sample

In this walkthrough we will configure a profile for a device.
We used a TTGO v1 board and wrote some code that will, every 90 seconds, generate random data and transmit a message via the on-board Lora module.
The message will contain the following data values all packed into only 13 bytes.

1. Longitude
2. Latitude
3. Satellites
4. Temperature
5. Altitude

It will pack and transmit this data in the following way

```
bytes 1-4:	Latitude
bytes 5-8:  Longitude
byte 9:     Number of satellites
bytes 10-11:	Temperature
bytes 12-13:	Altitude [meter]
```

An example of the transmitted data would be 

```
49D676FEA6BAAD010716003D02
```

In order to process that data, we will need to create a Magix profile.
A Magix profile is essentially code that you need to write in order to unpack the payload and extract the values in such a way that it can be 
understood by our platform. You can read more about the primitives at this link [Profiles Explained](magix-profiles/profiles-explained.md)

Assuming you have previously followed the (Things Stack) deep integration and have already linked the device, 
you should be seeing data coming into your device on the `Device Detail` page - 3 flags would be present on the `Upstream` content pane, 
signaling there is an issue. This is because no Magix profile has been configured for the device yet.
If you now click on the view action, you should see the raw data that was received from your device.

Navigate to the `Magix Profiles` on the main menu, then on the top right, click on the `Add Magix profile` button.
First enter a name (we will use `ttgo-sample-1`). This will make it easy to remember in future as profiles can be used for many devices of the same type.

In the decode content pane, remove all the default code and replace it with the code snippet below.

```
var bytesToInt = function (bytes) {
    var i = 0;
    for (var x = 0; x < bytes.length; x++) {
        i |= (bytes[x] << (x * 8));
    }
    return i;
};

var uint8 = function (bytes) {
    if (bytes.length !== uint8.BYTES) {
        throw new Error('uint8 must have exactly 1 byte');
    }
    return bytesToInt(bytes);
};
uint8.BYTES = 1;

var int16 = function (bytes) {
    if (bytes.length !== int16.BYTES) {
        throw new Error('int16 must have exactly 2 bytes');
    }
    var value = +(bytesToInt(bytes));
    if (value > 32767) {
        value -= 65536;
    }
    return value;
};
int16.BYTES = 2;

var int32 = function (bytes) {
    if (bytes.length !== int32.BYTES) {
        throw new Error('int32 must have exactly 4 bytes');
    }
    var value = +(bytesToInt(bytes));
    if (value > 2147483647) {
        value -= 4294967296;
    }
    return value;
};
int32.BYTES = 4;

var latLng = function (bytes) {
    return +(int32(bytes) / 1e6).toFixed(6);
};
latLng.BYTES = int32.BYTES;

var temp = function (bytes) {
    return +(int16(bytes));
};
temp.BYTES = int16.BYTES;

var altitude = function (bytes) {
    return +(int16(bytes));
};
altitude.BYTES = int16.BYTES;

var decodeInput = function (bytes, mask, names) {

    var maskLength = mask.reduce(function (prev, cur) {
        return prev + cur.BYTES;
    }, 0);
    if (bytes.length < maskLength) {
        throw new Error('Mask length is ' + maskLength + ' whereas input is ' + bytes.length);
    }

    names = names || [];
    var offset = 0;
    return Array.from(mask)
        .map(function (decodeFn) {
            var current = bytes.slice(offset, offset += decodeFn.BYTES);
            return decodeFn(current);
        })
        .reduce(function (prev, cur, idx) {
            prev[names[idx] || idx] = cur;
            return prev;
        }, {});
};

function DecodeHexStringToByteArray(hexString) {
   var result = [];
   while (hexString.length >= 2) { 
       result.push(parseInt(hexString.substring(0, 2), 16));
       hexString = hexString.substring(2, hexString.length);
   }
   return result;
}

function decode(message, metadata)
{
    var data = {};
    var input = DecodeHexStringToByteArray(message.asString);

   data = decodeInput(input, [latLng, latLng, uint8, temp, altitude], ['latitude', 'longitude', 'sats', 'temp', 'altitude']);

  return data;
}
```

> Below is an illustration of how it should look.

![decode pane](/images/ttgo-walkthrough-decode.jpg)

Once that code has been added, we are now able to verify that it works as intended.
Click on the test selector, you will now see a message saying you have no tests set up. 

![test pane empty](/images/ttgo-walkthrough-test-empty.jpg)

Click on the 'Add a test' button.
We will use the sample data mentioned above `49D676FEA6BAAD010716003D02`. For the metadata field, we will leave it empty then push done and finally you can push the 'Test' button.

![test pane empty](/images/ttgo-walkthrough-test.jpg)

Then click on the test button and you should see 3 green icons, showing success.

![test pane empty](/images/Magix-profile-end-to-end-test.jpg)

If you hover over the first green icon, we can see the returned decoded data

![test pane empty](/images/ttgo-walkthrough-decode-test-results.jpg)

Next we will create the convert function.
This is where we will want to map the decoded data to the primitives that our system understands.

We will use the following code to replace in the convert window

```
function convert(message, metadata)
{
    return {
        $location:{
            latitude: message.latitude,
            longitude: message.longitude
        },
        $telemetry:{
            altitude: message.altitude,
            satellites: message.sats,
            temperatureC: message.temp,
            temperatureF: (message.temp * 1.8) + 32
        }
    }
}
```

> Below is an illustration of how it should look.

![test pane empty](/images/ttgo-walkthrough-convert-pane.jpg)

### Tips and tricks 

In the sample device we used, it transmits temperature in °C, it may be useful to be able to show this as °F.
You can simply do the conversion in the profile and, thus, create more data from your existing data.

You can also choose naming as you like, above from the decode step, it returns a variable called temp.
We opted to see temperatureC and temperatureF, so we can do simple remapping.


