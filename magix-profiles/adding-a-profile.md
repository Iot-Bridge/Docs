# Adding a Magix profile

After selecting 'Magix Profiles' from the menu on the left and clicking the 'Add a Magix profile' button on the top right you will land on the New Magix profile page.

The page is split up into Upstream (profile for messages being sent `into` IotBridge)

![device detail](/images/add-profile-upstream.jpg)

and Downstream (profile for messages being sent `out` of IotBridge)

![device detail](/images/add-profile-downstream.jpg)


## Upstream 

### Decode function

The decode section allows you to write a javascript function that takes the raw message that your device produces and returns an object that can be easily used in the convert function.

![profile decode](/images/ProfileDecode.jpg)

### Convert function

The convert section allows you to write a javascript function that takes in the output from the decode function and must return an object containing key-value pairs (temp: 50, humidity: 20...) as $telemetry, a list of strings ('TempTooHigh', 'TurnedOn', 'Restarted'...) as $events and a $location object containing longitude and latitude values.

![profile convert](/images/ProfileConvert.jpg)

### Validate function

The validate section allows you to write a javascript function that takes in the output from the convert function and runs conditional logic to determine if the data conforms to what you are expecting. This function should return true or false.

![profile validate](/images/ProfileValidate.jpg)

### Writing tests

You have the ability to test the functions you wrote. The message sample is the data that you are expecting your device to produce. The message sample data type is the type of data you are supplying (Text, Bytes, Hex, Base64). Once you are done, click 'Test' to see the results. Hover over the 3 coloured icons below to see the output from each function. Green indicates that the function succeeded and red indicates that it failed. You may also use console logging (console.log('foo')) to debug your issues.

![profile tests](/images/ProfileTest.jpg)

Once you have set up your profile, head over to your device or device type to assign it for use.

## Downstream

### Encode function

The encode section allows you to write a javascript function, that takes in an object containing content of type string and a list of name-value parameters and converts it into data that your device will understand.

![profile encode](/images/ProfileEncode.jpg)