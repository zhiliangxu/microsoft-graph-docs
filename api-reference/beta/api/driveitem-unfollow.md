---
author: chackman
ms.author: chackman
title: Unfollow drive item
localization_priority: Normal
ms.prod: "sharepoint"
---
# Unfollow drive item

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Unfollow a [driveItem](../resources/driveitem.md).

>**Note:** To follow an item, see [Follow Item](driveitem-follow.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
DELETE /me/drive/following/{item-id} 
DELETE /users/{user-id}/drive/following/{item-id}
```

## Request body

No request body is required.

## Response

If successful, the API call returns a `204 No Content`. It does not return anything in the response body.

## Example
### Request
Here is an example of the request.
This example unfollows an item identified by `{item-id}`.

<!-- { "blockType": "request", "name": "unfollow-item", "scopes": "files.read" } -->

```http
DELETE /me/drive/following/{item-id}
```
### Response
<!-- { 
    "blockType": "response", 
    "truncated": true 
} -->
```http
HTTP/1.1 204 No Content
```
<!--
{
  "type": "#page.annotation",
  "description": "Unfollow an item that the user is following.",
  "keywords": "unfollow item",
  "section": "documentation",
  "tocPath": "Items/Unfollow",
  "suppressions": [
  ]
}
-->
