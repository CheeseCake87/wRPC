# 📡 weeRPC

The wee RPC (weeRPC) protocol is a JSON POST request based protocol which is design to be small.

(Wee - meaning small in Scottish slang)

Known libraries that use weeRPC:

- [weeRPCjs](https://github.com/CheeseCake87/weeRPCjs)
- [Flask-RPC](https://github.com/CheeseCake87/flask-rpc)
- [Quart-RPC](https://github.com/CheeseCake87/quart-rpc)

### Version 1.1

Changes:
- `wrpc` key changed to `weerpc` to better reflect the naming.

#### Request

`weerpc`: This is the version of weeRPC you are using which tells the server to validate that the JSON data includes what the version expects.

`function`: A string value that contains the name of the function to run.

`data`: JSON serializable data that is passed to the function as an argument.

#### Response

`weerpc`: The server sends back what version of weeRPC it's using to process requests/responses.

`ok`: A bool [true/false] value returned to be used to easily check if a response has been successful.

`message`: OPTIONAL This value may or may not be sent back. It is used to send back more information.

`data`: The data returned as the result from running the function called in the request.

**A typical request/response cycle is as follows:**

**Request**

```json
{
  "weerpc": 1.1,
  "function": "add_numbers",
  "data": [
    1,
    2,
    3
  ]
}
```

**Response**

```json
{
  "weerpc": 1.1,
  "ok": true,
  "message": "Function 'add_numbers' executed successfully",
  "data": 6
}
```

### Version 1

#### Request

`wrpc`: This is the version of weeRPC you are using which tells the server to validate that the JSON data includes what the version expects.

`function`: A string value that contains the name of the function to run.

`data`: JSON serializable data that is passed to the function as an argument.

#### Response

`wrpc`: The server sends back what version of weeRPC it's using to process requests/responses.

`ok`: A bool [true/false] value returned to be used to easily check if a response has been successful.

`message`: OPTIONAL This value may or may not be sent back. It is used to send back more information.

`data`: The data returned as the result from running the function called in the request.

**A typical request/response cycle is as follows:**

**Request**

```json
{
  "wrpc": 1.0,
  "function": "add_numbers",
  "data": [
    1,
    2,
    3
  ]
}
```

**Response**

```json
{
  "wrpc": 1.0,
  "ok": true,
  "message": "Function 'add_numbers' executed successfully",
  "data": 6
}
```
