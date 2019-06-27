---
title: "directoryRole: delta"
description: "Get newly created, updated, or deleted directory roles without having to perform a full read of the entire resource collection. See Using Delta Query for details."
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
---

# directoryRole: delta

Get newly created, updated, or deleted directory roles without having to perform a full read of the entire resource collection. See [Using Delta Query](/graph/delta-query-overview) for details.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).


|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Directory.Read.All, Directory.ReadWrite.All, Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Directory.Read.All, Directory.ReadWrite.All |

## HTTP request

To begin tracking changes, you make a request including the **delta** function on the [directoryRole](../resources/directoryrole.md) resource.

<!-- { "blockType": "ignored" } -->
```http
GET /directoryRoles/delta
```

## Query parameters

Tracking changes incurs a round of one or more **delta** function calls. If you use any query parameter 
(other than `$deltatoken` and `$skiptoken`), you must specify 
it in the initial **delta** request. Microsoft Graph automatically encodes any specified parameters 
into the token portion of the `nextLink` or `deltaLink` URL provided in the response. 
You only need to specify any desired query parameters once upfront. 
In subsequent requests, copy and apply the `nextLink` or `deltaLink` URL from the previous response, as that URL already 
includes the encoded, desired parameters.

| Query parameter	   | Type	|Description|
|:---------------|:--------|:----------|
| $deltatoken | string | A [state token](/graph/delta-query-overview) returned in the `deltaLink` URL of the previous **delta** function call for the same resource collection, indicating the completion of that round of change tracking. Save and apply the entire `deltaLink` URL including this token in the first request of the next round of change tracking for that collection.|
| $skiptoken | string | A [state token](/graph/delta-query-overview) returned in the `nextLink` URL of the previous **delta** function call, indicating there are further changes to be tracked in the same resource collection. |

### OData query parameters

This method supports OData query parameters to help customize the response.

- You can use a `$select` query parameter as in any GET request to specify only the properties your need for best performance. The _id_ property is always returned.

- There is limited support for `$filter`:

  - The only supported `$filter` expression is for tracking changes for specific resources, by their id:  `$filter=id+eq+{value}` or `$filter=id+eq+{value1}+or+id+eq+{value2}`. The number of ids you can specify is limited by the maximum URL length.

## Request headers

| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer &lt;token&gt;|
| Content-Type  | application/json |

## Request body

Do not supply a request body for this method.

### Response

If successful, this method returns `200 OK` response code and [directoryRole](../resources/directoryrole.md) collection object in the response body. The response also includes a `nextLink` URL or a `deltaLink` URL.

- If a `nextLink` URL is returned, there are additional pages of data to be retrieved in the session. The application continues making requests using the `nextLink` URL until a `deltaLink` URL is included in the response.

- If a `deltaLink` URL is returned, there is no more data about the existing state of the resource to be returned. Save `deltaLink` URL and apply it in the next **delta** call to learn about changes to the resource in the future.

### Example

##### Request

<!-- {
  "blockType": "request",
  "name": "directoryRole_delta"
}-->

```http
GET https://graph.microsoft.com/v1.0/directoryRoles/delta
```

##### Response

Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- { 
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.directoryRole",
  "isCollection": true 
} --> 
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/v1.0/$metadata#directoryRoles",
  "@odata.nextLink":"https://graph.microsoft.com/v1.0/directoryRoles/delta?$skiptoken=pqwSUjGYvb3jQpbwVAwEL7yuI3dU1LecfkkfLPtnIjsXoYQp_dpA3cNJWc",
  "value": [
      {
      "description": "description-value",
      "displayName": "displayName-value",
      "roleTemplateId": "roleTemplateId-value",
      "id": "id-value"
    }
  ]
}
```

### See also

- [Use delta query to track changes in Microsoft Graph data](/graph/delta-query-overview) for more details
- [Get incremental changes for users](/graph/delta-query-users) for an example requests.

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "directoryRole: delta",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
