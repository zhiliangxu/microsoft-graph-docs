---
title: "Create User"
description: "Use this API to create a new User."
author: "dkershaw10"
localization_priority: Priority
ms.prod: "microsoft-identity-platform"
---

# Create User

Create a new [user](../resources/user.md).
The request body contains the user to create. At a minimum, you must specify the required properties for the user. You can optionally specify any other writable properties.

>[!NOTE]
>To create external users, use the [invitation API](invitation-post.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | User.ReadWrite.All, Directory.ReadWrite.All, Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | User.ReadWrite.All, Directory.ReadWrite.All |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /users
```

## Request headers

| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |
| Content-Type  | application/json  |

## Request body

In the request body, supply a JSON representation of [user](../resources/user.md) object.

The following table shows the properties that are required when you create a user.

| Parameter | Type | Description|
|:---------------|:--------|:----------|
|accountEnabled |boolean |true if the account is enabled; otherwise, false.|
|displayName |string |The name to display in the address book for the user.|
|onPremisesImmutableId |string |Only needs to be specified when creating a new user account if you are using a federated domain for the user's userPrincipalName (UPN) property.|
|mailNickname |string |The mail alias for the user.|
|passwordProfile|[PasswordProfile](../resources/passwordprofile.md) |The password profile for the user.|
|userPrincipalName |string |The user principal name (someuser@contoso.com).|

Because the **user** resource supports [extensions](/graph/extensibility-overview), you can use the `POST` operation and add custom properties with your own data to the user instance while creating it.

>[!NOTE]
>Federated users created using this API will be forced to sign-in every 12 hours by default.  For more information on how to change this, see [Exceptions for token lifetimes](https://docs.microsoft.com/azure/active-directory/develop/active-directory-configurable-token-lifetimes#exceptions).

## Response

If successful, this method returns `201 Created` response code and [user](../resources/user.md) object in the response body.

## Example

##### Request

Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "create_user_from_users"
}-->

```http
POST https://graph.microsoft.com/v1.0/users
Content-type: application/json

{
  "accountEnabled": true,
  "displayName": "displayName-value",
  "mailNickname": "mailNickname-value",
  "userPrincipalName": "upn-value@tenant-value.onmicrosoft.com",
  "passwordProfile" : {
    "forceChangePasswordNextSignIn": true,
    "password": "password-value"
  }
}
```

In the request body, supply a JSON representation of [user](../resources/user.md) object.

##### Response

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "id": "id-value",
    "businessPhones": [],
    "displayName": "displayName-value",
    "givenName": null,
    "jobTitle": null,
    "mail": null,
    "mobilePhone": null,
    "officeLocation": null,
    "preferredLanguage": null,
    "surname": null,
    "userPrincipalName": "upn-value@tenant-value.onmicrosoft.com"
}
```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Create User",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
