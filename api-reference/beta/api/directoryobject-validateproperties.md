---
title: "directoryObject: validateProperties"
description: "Validate if an Office 365 group's display name or mail nickname complies with naming policies.  Clients can use the API to determine if a display name or mail nickname is valid before trying to **create** an Office 365 group. For validating properties of an existing group, use the validateProperties function for groups."
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
---

# directoryObject: validateProperties

Validate if an Office 365 group's display name or mail nickname complies with naming policies.  Clients can use the API to determine if a display name or mail nickname is valid before trying to **create** an Office 365 group. For validating properties of an existing group, use the [validateProperties function](group-validateproperties.md) for groups.

The following validations are performed for the display name and mail nickname properties: 
1. Validate the prefix and suffix naming policy
2. Validate the custom banned words policy
3. Validate the mail nickname is unique

This API returns with the first failure encountered. If one or more properties fail multiple validations, only the property with the first validation failure is returned. However, you can validate both the mail nickname and the display name and receive a collection of validation errors if you are only validating the prefix and suffix naming policy.

## Prerequisites

The following **permission** is required to execute this API: *Group.Read.All*

## HTTP request
<!-- { "blockType": "ignored" } -->
``` http
POST /directoryObjects/validateProperties
```

## Request headers

| Name           | Description      |
|:---------------|:-----------------|
| Authorization  | Bearer {code}    |
| Content-Type   | application/json |

## Request body
In the request body, provide a JSON object with the following parameters.

| Parameter    | Type   |Description|
|:---------------|:--------|:----------|
|entityType|String| `Group` is the only supported entity type. |
|displayName|String| The display name of the group to validate. The property is not individually required. However, at least one property (displayName or mailNickname) is required. |
|mailNickname|String| The mail nickname of the group to validate. The property is not individually required. However, at least one property (displayName or mailNickname) is required. |
|onBehalfOfUserId|Guid| The object ID of the user to impersonate when calling the API. The validation results are for the onBehalfOfUserId's attributes and roles. |

## Response

If successful and there are no validation errors, the method returns `204 No Content` response code. It does not return anything in the response body.

If the request is invalid, the method returns `400 Bad Request` response code. An error message with details about the invalid request is returned in the response body.

If there is a validation error, the method returns `422 Unprocessable Entity` response code. An error message and a collection of error details is returned in the response body.

## Examples

This is an example of a successful validation request.

### Request
<!-- {
  "blockType": "request",
  "name": "directoryobject_validateproperties"
}-->
``` http
POST https://graph.microsoft.com/beta/directoryObjects/validateProperties
Content-type: application/json
Content-length: 164

{
  "entityType": "Group",
  "displayName": "Myprefix_test_mysuffix",
  "mailNickname": "Myprefix_test_mysuffix",
  "onBehalfOfUserId": "onBehalfOfUserId-value"
}
```

### Response
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

This is an example of a request with validation errors.

### Request
```http
POST https://graph.microsoft.com/beta/directoryObjects/validateProperties
Content-type: application/json
Content-length: 164

{
  "entityType": "Group",
  "displayName": "test",
  "mailNickname": "test",
  "onBehalfOfUserId": "onBehalfOfUserId-value"
}
```

### Response
```http
HTTP/1.1 422 
Content-Type: application/json

{
  "error": {
    "code": "Request_UnprocessableEntity",
    "message": "The values provided contain one or more validation errors.",
    "innerError": {
      "request-id": "request-id-value",
      "date": "date-value"
    },
    "details": [
      {
        "target": "displayName",
        "code": "MissingPrefixSuffix",
        "message": "Property mailNickname is missing a required prefix/suffix per your organization's Group naming requirements.",
        "prefix": "Myprefix_",
        "suffix": "_mysuffix"
      },
      {
        "target": "mailNickname",
        "code": "MissingPrefixSuffix",
        "message": "Property mailNickname is missing a required prefix/suffix per your organization's Group naming requirements.",
        "prefix": "Myprefix_",
        "suffix": "_mysuffix"
      }
    ]
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "directoryObject: validateProperties",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
