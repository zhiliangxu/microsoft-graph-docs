---
title: "Update a directory setting"
description: "Update the properties of a specific directory setting object."
author: "davidmu1"
localization_priority: Normal
ms.prod: "microsoft-identity-platform"
---

# Update a directory setting

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a specific directory setting object.

> **Note**: The /beta version of this API is only applies to groups. The /v1.0 version of this API has been renamed to *Update groupSettings*.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Directory.ReadWrite.All, Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Directory.ReadWrite.All |

## HTTP request
<!-- { "blockType": "ignored" } -->
Update a tenant-wide or group specific setting.
```http
PATCH /settings/{id}
PATCH /groups/{id}/settings/{id}
```
## Optional request headers
| Name       | Description|
|:-----------|:-----------|
| Authorization  | Bearer {token}. Required.|

## Request body
In the request body, supply the values for relevant fields that should be updated. 

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
| values | [settingValue](../resources/settingvalue.md) collection | The updated set of values.  NOTE: You must supply the entire collection set. You cannot update a single set of values. |

## Response

If successful, this method returns a `204 OK` response code.

## Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_directorysetting"
}-->
```http
PATCH https://graph.microsoft.com/beta/settings/{id}
Content-type: application/json
Content-length: 178

{
  "values": [
    {
      "name": "name-value",
      "value": "value-value"
    }
  ]
}
```
##### Response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.directorysetting"
} -->
```http
HTTP/1.1 204 OK
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Update directorysetting",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
