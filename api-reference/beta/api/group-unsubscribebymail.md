---
title: "group: unsubscribeByMail"
description: "Calling this method will disable the current user to receive email notifications for this group about new posts, events, and files in that group. Supported for Office 365 groups only. "
localization_priority: Normal
author: "dkershaw10"
ms.prod: "groups"
---

# group: unsubscribeByMail

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Calling this method will disable the current user to receive email notifications for this group about new posts, events, and files in that group. Supported for Office 365 groups only. 

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Group.ReadWrite.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Group.ReadWrite.All |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /groups/{id}/unsubscribeByMail
```

## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |
| Prefer | return=minimal. If minimal response header is included in the request header, then a successful response returns `204 No Content` code. Optional.  | 

## Request body
 Do not supply a request body for this method. 

## Response
If successful, this method returns `200 OK` response code. It does not return anything in the response body.

## Example
#### Request
The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "group_unsubscribebymail"
}-->
```http
POST https://graph.microsoft.com/beta/groups/{id}/unsubscribeByMail
```

#### Response
The following is an example of the response. 
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 200 OK
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "group: unsubscribeByMail",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
