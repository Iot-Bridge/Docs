# Rest Channel Service

Our 'Rest Channel Service' provides support for devices that communicate via Rest.
We support consuming messages of three content types (shown below), using the POST method.

1. application/json
2. application/x-www-form-urlencoded
3. text/plain

### application/json

Below is an example of a json payload.

```
{
    "temp": 24.7,
    "supply": 3.91
}
```

### application/x-www-form-urlencoded


```
temp=24.7&supply=3.91
```

### text/plain

While you can use this for receiving any type of data, it is mostly used for receiving binary data.
This is useful for devices that use the same message protocol, but can, for example, communicate via Lora and Rest.

### Responses

Our system will return for both accepted (202) and bad requests (400) an object that we call `Command Result`.
This has the following definition.

```
{
    "success": boolean,
    "error": array of string
}
```

The Rest channel service will respond to every request in 1 of 2 ways.
If the data is valid and accepted, we will return the accepted response (202)

```
{
    "success": true,
    "error": null
}
```

If the data is not valid, or other validation errors ocurred,
we will always return a bad request (400).

When we return a bad request, we will always return a `Command Result` object, that has the following json shape.

```
{
    "success": false,
    "error": ['something went wrong']
}
```
