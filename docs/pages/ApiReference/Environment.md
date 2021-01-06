# API: Environment
Use the following API methods to request details about _**Rhino Parameters**_ and how to create or modify them.

## Get Parameters
Returns a list of available _**Rhino Parameters**_.

```
GET /api/v3/environment
```

#### Response Content
```js
{
  "firtsName": "foo",
  "lastName": "bar",
  ...
}
```

### Response Codes
|Code|Description                                                               |
|----|--------------------------------------------------------------------------|
|200 |Success, the _**Rhino Parameters**_ were returned as part of the response.|
|500 |Fail, the server encountered an unexpected error.                         |

## Get Parameter
Returns the value of the specified _**Rhino Parameter**_.

```
GET /api/v3/environment/:parameter_name
```
|Name            |Type  |Description                         |
|----------------|------|------------------------------------|
|parameter_name|string|The Name of the _**Rhino Parameter**_.|

#### Response Content
```
foo bar
```

### Response Codes
|Code|Description                                                                   |
|----|------------------------------------------------------------------------------|
|200 |Success, the _**Rhino Parameter**_ value was returned as part of the response.|
|404 |Not found, the _**Rhino Parameter**_ was not found by the specified name.     |
|500 |Fail, the server encountered an unexpected error.                             |

## Add or Replace Parameter
Updates the value of the specified _**Rhino Parameter**_ if the parameter exists or create a new one if not.

```
PUT /api/v3/environment/:parameter_name
```
|Name            |Type  |Description                         |
|----------------|------|------------------------------------|
|parameter_name|string|The Name of the _**Rhino Parameter**_.|

#### Response Content
```js
{
    "firstName": "bar"
}
```
The following system fields are always included in the response:

#### General
|Name          |Type  |Description                                            |
|--------------|------|-------------------------------------------------------|
|parameterName |string|The name of the parameter which was created or updated.|
|parameterValue|string|The value of the parameter after update or creation.   |

### Response Codes
|Code|Description                                                                   |
|----|------------------------------------------------------------------------------|
|200 |Success, the _**Rhino Parameter**_ value was returned as part of the response.|
|500 |Fail, the server encountered an unexpected error.                             |

## Delete Parameter
Deletes _**Rhino Parameter**_ if the parameter exists.

```
DELETE /api/v3/environment/:parameter_name
```
|Name          |Type  |Description                           |
|--------------|------|--------------------------------------|
|parameter_name|string|The Name of the _**Rhino Parameter**_.|

### Response Codes
|Code|Description                                                          |
|----|---------------------------------------------------------------------|
|204 |No Content, the _**Rhino Parameter**_ value was successfully deleted.|
|500 |Fail, the server encountered an unexpected error.                    |

## Delete Parameters
Deletes _**Rhino Parameter**_ if the parameter exists.

```
DELETE /api/v3/environment
```

### Response Codes
|Code|Description                                                      |
|----|-----------------------------------------------------------------|
|204 |No Content, all _**Rhino Parameters**_ were successfully deleted.|
|500 |Fail, the server encountered an unexpected error.                |