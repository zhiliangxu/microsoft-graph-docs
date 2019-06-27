---
title: "Remove rejectedSender"
description: "Remove a user or group from the rejected-senders list."
author: "dkershaw10"
localization_priority: Normal
ms.prod: "groups"
---

# Remove rejectedSender

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Remove a user or group from the rejected-senders list of the specified group.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)  |
|:---------------------------------------|:-------------------------------------------- |
| Delegated (work or school account)     | Group.ReadWrite.All  |  
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
DELETE /groups/{id}/rejectedSenders/$ref?$id={id}
```

## Request headers

| Header         | Value                      |
|:---------------|:---------------------------|
| Authorization  | Bearer {token}. Required.  

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns `204 No Content` response code. It does not return anything in the response body.

## Examples
### Example 1: Remove a user from the rejected-senders list of the group.
#### Request

<!-- {
  "blockType": "request",
  "name": "remove_user_from_rejectedsenderslist_of_group"
}-->
```http
DELETE https://graph.microsoft.com/beta/groups/{id}/rejectedSenders/$ref?$id=https://graph.microsoft.com/beta/users/{id}
```
#### Response
The following is an example of the response. 
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

### Example 2: Remove a group from the rejected-senders list of the group.
#### Request
<!-- {
  "blockType": "request",
  "name": "remove_group_from_rejectedsenderslist_of_group"
}-->
```http
DELETE https://graph.microsoft.com/beta/groups/{id}/rejectedSenders/$ref?$id=https://graph.microsoft.com/beta/groups/{other-group-id}
```

#### Response
The following is an example of the response. 
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Remove rejectedSender",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
