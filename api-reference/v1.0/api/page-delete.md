---
title: "Delete page"
description: "Delete a OneNote page."
localization_priority: Normal
author: "jewan-microsoft"
ms.prod: "onenote"
---

# Delete page

Delete a OneNote page.
## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Notes.ReadWrite, Notes.ReadWrite.All    |
|Delegated (personal Microsoft account) | Notes.ReadWrite    |
|Application | Notes.ReadWrite.All |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
DELETE /me/onenote/pages/{id}
DELETE /users/{id | userPrincipalName}/onenote/pages/{id}
DELETE /groups/{id}/onenote/pages/{id}
DELETE /sites/{id}/onenote/pages/{id}
```
## Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "delete_page"
}-->
```http
DELETE https://graph.microsoft.com/v1.0/me/onenote/pages/{id}
```
##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Delete page",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
