# Device detail

The 'Device Detail' page, is where you can configure and view the device state.

![device detail](/images/device-detail.jpg)

### Location pane

The location pane will show the location of the device. The location can be set in one of two ways.
The first way is from upstream messages via the Magix profile - this is recommended when the device 
emits location telemetry. As the device emits upstream messages that contain location telemetry, the map
will automatically reflect the most recent location. 

> Note: Once the location has been set via an upstream message, you cannot manually adjust its location

The second way is to to click the 'Set Location' button on the map, that will bring up a window where you can simply 
click on a location and save. That location will then reflect on the map.

### Telemetry pane

The 'Telemetry' pane will automatically show the most recent telemetry data received from the device.
The last seen time will reflect the timestamp of the most recent upstream message received. Values are shown in a key-value fashion,
where the key is on the left and value will be on the right.

### Actions pane

The 'Actions' pane is where you can configure actions. Actions are our platform's ability to send messages from
the platform down to the device. We call these downstream messages. A device must support receiving messages 
in order to use this feature. 

### Events pane

The 'Events' pane will show any event data from upstream messages. A device may, for example, emit an event
like `rain detected`. 

### Quick Telemetry pane

The 'Quick Telemetry' pane is our platform's ability to automatically inspect data in upstream messages,
to determine whether they can be drawn on the chart. This is mostly for numeric or boolean (true/false) values.
It will load and display data from the upstream messages received in the last 24-hours.

### Control pane & Content pane

The control pane is a tabbed list of options. When you select an option, the content pane will change to reflect the 
information for that option.

#### Configuration

This is the area where you can link your device to: a place, a device type or a Magix profile. You can also set up the destination for your downstream messages (Rest, Sigfox, Lora, SMS, Mqtt) or configure rules and integrations the device must adhere to.

![device configuration](/images/DeviceConfiguration.jpg)


#### Communication Settings

You can find communication information on how to send messages from your physical device to your virtual device in IotBridge.

![device communication](/images/DeviceCommunication.jpg)