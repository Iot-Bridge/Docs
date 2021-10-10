# Channel Services - Quick start

Iot devices not only come in many forms and sizes, they also make use of different methods to communicate.
Our platform supports multiple methods of communication, we call these channel services.

Below is a list of our current channel services

1. [Rest](channel-services/rest.md)
2. [Lora](channel-services/Lora.md)
3. [Sigfox](channel-services/sigfox.md)
4. [Mqtt](channel-services/mqtt.md)
5. [SMS](channel-services/sms.md)

> For Lora and Sigfox, we offer deep integration into the 'Sigfox Backend' and 'The Thing Stack V3'

## Upstream and downstream

All messages coming from a device into our platform are called 'upstream messages', inversely all messages going from
our platform to a device are called 'downstream messages'.

## Message processing

Iot devices, not only use different forms of communication, they also vary how and what they send as their payload.
In order for our platform to process incoming data, the payload must first be transformed. This is done by creating a Magix profile.
All messages upstream and downstream are routed to our Magix processor, that uses a profile to process the message.

## Magix profiles

A Magix profile, is where one can write javascript that decodes or transforms the raw data from a device into primitives 
that our platform supports. 

Below is a list of primitives supported today

1. $location
2. $events
3. $telemetry

> Read more about profiles here [Profiles explained](magix-profiles/profiles-explained.md)