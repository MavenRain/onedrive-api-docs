# Error resource type

The error resource is returned whenever an error occurs in the processing
of a request.

Error responses follow the definition in the
[OData v4](http://docs.oasis-open.org/odata/odata-json-format/v4.0/os/odata-json-format-v4.0-os.html#_Toc372793091)
specification for error responses.

See the topic on [Error response](../misc/errors.md) for more information about
handling errors with the OneDrive API.

## JSON Representation

The error resource is composed of these resources:

<!-- { "blockType": "resource", "@odata.type": "oneDrive.error" } -->
```json
{
  "error": { "@odata.type": "odata.error" }  
}
```

#### odata.error resource type

Inside the error response is an error resource that includes the following
properties:

<!-- { "blockType": "resource", "@odata.type": "odata.error", "optionalProperties": [ "target", "details", "innererror"] } -->
```json
{
  "code": "string",
  "message": "string",
  "target": "string",
  "details": [{"@odata.type": "error.detail"}],
  "innererror": { "@odata.type": "odata.error" }
}
```

| Property name  | Value                  | Description\                                                                                               |
|:---------------|:-----------------------|:-----------------------------------------------------------------------------------------------------------|
| **code**       | string                 | An error code string for the error that occured                                                            |
| **message**    | string                 | A developer ready message about the error that occured. This should not be displayed to the user directly. |
| **target**     | string                 | Optional. Provides more information on the targer resource that generated the error.                       |
| **details**    | array of error details | Optional. Provides more information on the specifics of the error message.                                 |
| **innererror** | error object           | Optional. Additional error messages that may be more specific than the top level error.                    |



#### error.detail resource type

The details property is a collection of resources using this definition:

<!-- { "blockType": "resource", "@odata.type": "error.detail" } -->
```json
{
  "code": "string",
  "message": "string",
  "target": "string"
}
```

| Property name | Value  | Description\                                                                                               |
|:--------------|:-------|:-----------------------------------------------------------------------------------------------------------|
| **code**      | string | An error code string for the error that occured.                                                            |
| **message**   | string | A developer ready message about the error that occured. This should not be displayed to the user directly. |
| **target**    | string | Optional. Provides more information on the targer resource that generated the error.                       |


<!-- {
  "type": "#page.annotation",
  "description": "OneDrive API error resource definition.",
  "keywords": "onedrive,api,error,resource",
  "section": "documentation"
} -->
