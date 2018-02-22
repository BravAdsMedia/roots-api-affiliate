### URI / Method

All requests should be made to the URI and method specified on each section. 

### Headers

You should always include the following headers on your request:

Key           | Value
------------- | ---------------------------------
Content-Type  | application/json, charset=UTF-8
Accept        | application/json, text/plain, \*/\*
Cache         | no-cache
Authorization | Bearer TOKEN

The `TOKEN` details will be provided by a BravAds representative. 

### HTTP Errors

The API can generate the following HTTP errors:

Error | Description
------| --------------------------------------------------------------------------------------------
401   | Unauthenticated. You failed to provide the `Authorization` header or the `TOKEN` is invalid.
403   | Forbidden. You are not authorized to access the specified resource.
404   | Not found. The specified resource could not be found.
501   | Role not enabled for the specified action.

The response body will also include the following JSON with the error description:

```
{
    "error": {
        "code": 401,
        "message": "Unauthenticated"
    }
}
```