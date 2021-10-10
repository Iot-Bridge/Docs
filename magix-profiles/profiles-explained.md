# Magix profiles explained

Magix is the name of our platform's component that is capable of running javascript code to prepare data from messages
both upstream and downstream. 

## Upstream 

The function of the javascript code is to normalise the raw data coming from the device and extracting 
the values from the required fields and mapping the values to the primitives.

#### Upstream primitives

Our platform supports 3 primitives for upstream messages.

1. $location
2. $events
3. $telemetry

`$location` is expected to be an object that contains longitude and latitude as properties.

```
$location:{"longitude":28.165022,"latitude":-25.905153}
```

`$events` is expected to be an array of strings.

```
$events:['rain detected', 'watering stopped']
```

`$telemetry` is expected to be an object containing key value pairs (dictionary)

```
$telemetry: {
    temp: 24.7,
    supply: 3.91
}
```

#### Full sample

```
{
    $telemetry: {
        temp: 24.7,
        supply: 3.91
    },
    $events:['rain detected', 'watering stopped'],
    $location:{"longitude":28.165022,"latitude":-25.905153}
}
```
