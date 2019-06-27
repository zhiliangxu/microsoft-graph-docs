---
title: "user: delta"
description: "Get newly created, updated, or deleted users without having to perform a full read of the entire user collection. See Track changes for details."
localization_priority: Normal
author: "dkershaw10"
ms.prod: "microsoft-identity-platform"
---

# user: delta

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get newly created, updated, or deleted users without having to perform a full read of the entire user collection. See [Track changes](/graph/delta-query-overview) for details.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).


|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | User.Read, User.ReadWrite, User.ReadBasic.All, User.Read.All, User.ReadWrite.All, Directory.Read.All, Directory.ReadWrite.All, Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | User.Read, User.ReadWrite    |
|Application | User.Read.All, User.ReadWrite.All, Directory.Read.All, Directory.ReadWrite.All |

## HTTP request

To begin tracking changes, you make a request including the delta function on the users resource.

<!-- { "blockType": "ignored" } -->
```http
GET /users/delta
```

## Query parameters

Tracking changes in users incurs a round of one or more **delta** function calls. If you use any query parameter (other than `$deltatoken` and `$skiptoken`), you must specify it in the initial **delta** request. Microsoft Graph automatically encodes any specified parameters into the token portion of the `nextLink` or `deltaLink` URL provided in the response.

You only need to specify any desired query parameters once upfront.

In subsequent requests, copy and apply the `nextLink` or `deltaLink` URL from the previous response, as that URL already includes the encoded, desired parameters.

| Query parameter	   | Type	|Description|
|:---------------|:--------|:----------|
| $deltatoken | string | A [state token](/graph/delta-query-overview) returned in the `deltaLink` URL of the previous **delta** function call for the same user collection, indicating the completion of that round of change tracking. Save and apply the entire `deltaLink` URL including this token in the first request of the next round of change tracking for that collection.|
| $skiptoken | string | A [state token](/graph/delta-query-overview) returned in the `nextLink` URL of the previous **delta** function call, indicating there are further changes to be tracked in the same user collection. |

### OData query parameters

This method supports optional OData Query Parameters to help customize the response.

- You can use a `$select` query parameter as in any GET request to specify only the properties your need for best performance. The *id* property is always returned.
- There is limited support for `$filter`:
  - The only supported `$filter` expression is for tracking changes on a specific object: `$filter=id+eq+{value}`. You can filter multiple objects. For example, `https://graph.microsoft.com/beta/users/delta/?$filter= id eq '477e9fc6-5de7-4406-bb2a-7e5c83c9ffff' or id eq '004d6a07-fe70-4b92-add5-e6e37b8affff'`. There is a limit of 50 filtered objects.

## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer &lt;token&gt;|
| Content-Type  | application/json |
| Prefer | return=minimal <br><br>Specifying this header with a request that uses a `deltaLink` would return only the object properties that have changed since the last round. Optional. |

## Request body
Do not supply a request body for this method.

### Response

If successful, this method returns `200 OK` response code and [user](../resources/user.md) collection object in the response body. The response also includes a `nextLink` URL or a `deltaLink` URL.

- If a `nextLink` URL is returned:
  - This indicates there are additional pages of data to be retrieved in the session. The application continues making requests using the `nextLink` URL until a `deltaLink` URL is included in the response.
  - The response includes the same set of properties as in the initial delta query request. This allows you to capture the full current state of the objects when initiating the delta cycle.

- If a `deltaLink` URL is returned:
  - This indicates there is no more data about the existing state of the resource to be returned. Save and use the `deltaLink` URL to learn about changes to the resource in the next round.
  - You have a choice to specify the `Prefer:return=minimal` header, to include in the response values for only the properties that have changed since the time the `deltaLink` was issued.

#### Default: return the same properties as initial delta request

By default, requests using a `deltaLink` or `nextLink` return the same properties as selected in the initial delta query in the following ways:

- If the property has changed, the new value is included in the response. This includes properties being set to null value.
- If the property has not changed, the old value is included in the response.
- If the property has never been set before it will not be included in the response at all.


> **Note:** With this behavior, by looking at the response it is not possible to tell whether a property is changing or not. Also, the delta responses tend to be large because they contain all property values  - as shown in the [second example](#request-2) below.

#### Alternative: return only the changed properties

Adding an optional request header - `prefer:return=minimal` - results in the following behavior:

- If the property has changed, the new value is included in the response. This includes properties being set to null value.
- If the property has not changed, the property is not included in the response at all. (Different from the default behavior.)

> **Note:** The header can be added to a `deltaLink` request at any point in time in the delta cycle. The header only affects the set of properties included in the response and it does not affect how the delta query is executed. See the [third example](#request-3) below.

### Example

#### Request 1

The following is an example of the request. There is no `$select` parameter, so a default set of properties is tracked and returned.
<!-- {
  "blockType": "request",
  "name": "user_delta"
}-->

```http
GET https://graph.microsoft.com/beta/users/delta
```

#### Response 1

The following is an example of the response when using `deltaLink` obtained from the query initialization.

>**Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/beta/$metadata#users",
  "@odata.nextLink":"https://graph.microsoft.com/beta/users/delta?$skiptoken=pqwSUjGYvb3jQpbwVAwEL7yuI3dU1LecfkkfLPtnIjsXoYQp_dpA3cNJWc",
  "value": [
    {
      "businessPhones": [
          "businessPhones-value"
      ],
      "displayName": "displayName-value",
      "givenName": "givenName-value",
      "jobTitle": "jobTitle-value",
      "mail": "mail-value",
      "mobilePhone": "mobilePhone-value",
      "officeLocation": "officeLocation-value",
      "preferredLanguage": "preferredLanguage-value",
      "surname": "surname-value",
      "userPrincipalName": "userPrincipalName-value",
      "id": "id-value"
    }
  ]
}
```

#### Request 2

The next example shows the initial request selecting 3 properties for change tracking, with default response behavior:
<!-- {
  "blockType": "request",
  "name": "user_delta_select"
}-->

```http
GET https://graph.microsoft.com/beta/users/delta?$select=displayName,jobTitle,mobilePhone
```

#### Response 2

The following is an example of the response when using `deltaLink` obtained from the query initialization. Note that all 3 properties are included in the response and it is not known which ones have changed since the `deltaLink` was obtained.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/beta/$metadata#users",
  "@odata.nextLink":"https://graph.microsoft.com/beta/users/delta?$skiptoken=pqwSUjGYvb3jQpbwVAwEL7yuI3dU1LecfkkfLPtnIjsXoYQp_dpA3cNJWc",
  "value": [
    {
      "displayName": "displayName-value",
      "jobTitle": "jobTitle-value",
      "mobilePhone": null
    }
  ]
}
```

#### Request 3

The next example shows the initial request selecting 3 properties for change tracking, with alternative minimal response behavior:
<!-- {
  "blockType": "request",
  "name": "user_delta_minimal"
}-->

```http
GET https://graph.microsoft.com/beta/users/delta?$select=displayName,jobTitle,mobilePhone
Prefer: return=minimal
```

#### Response 3

The following is an example of the response when using `deltaLink` obtained from the query initialization. Note that the `mobilePhone` property is not included, which means it has not changed since the last delta query; `displayName` and `jobTitle` are included which means their values have changed.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/beta/$metadata#users",
  "@odata.nextLink":"https://graph.microsoft.com/beta/users/delta?$skiptoken=pqwSUjGYvb3jQpbwVAwEL7yuI3dU1LecfkkfLPtnIjsXoYQp_dpA3cNJWc",
  "value": [
    {
      "displayName": "displayName-value",
      "jobTitle": null
    }
  ]
}
```

- [Use delta query to track changes in Microsoft Graph data](/graph/delta-query-overview).
- [Get incremental changes for users](/graph/delta-query-users).

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "user: delta",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
