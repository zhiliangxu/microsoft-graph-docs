---
title: "Update group"
description: "Update the properties of a [group](../resources/group.md) object."
author: "dkershaw10"
localization_priority: Normal
ms.prod: "groups"
---

# Update group

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [group](../resources/group.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Group.ReadWrite.All, Directory.ReadWrite.All, Directory.AccessAsUser.All  |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Group.ReadWrite.All, Directory.ReadWrite.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
PATCH /groups/{id}
```

## Request headers

| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer {token}. Required. |

## Request body

In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property   | Type |Description|
|:---------------|:--------|:----------|
|allowExternalSenders|Boolean|Default is **false**. Indicates if people external to the organization can send messages to the group.|
|autoSubscribeNewMembers|Boolean|Default is **false**. Indicates if new members added to the group will be auto-subscribed to receive email notifications.|
|description|String|An optional description for the group. |
|displayName|String|The display name for the group. This property is required when a group is created and it cannot be cleared during updates. |
|groupTypes|String collection|Specifies the group type and its membership.  <br><br>If the collection contains **Unified** then the group is an Office 365 group; otherwise it's a security group.  <br><br>If the collection includes **DynamicMembership**, the group has dynamic membership; otherwise, membership is static. |
|mailEnabled|Boolean|Specifies whether the group is mail-enabled. |
|mailNickname|String|The mail alias for the group. This property must be specified when a group is created. |
|securityEnabled|Boolean|Specifies whether the group is a security group, including Office 365 groups. |
|visibility|String|Specifies the visibility of an Office 365 group. Possible values are: **Private**, **Public**, or empty (which is interpreted as **Public**).|

Because the **group** resource supports [extensions](/graph/extensibility-overview), you can use the `PATCH` operation to add, update, or delete your own app-specific data in custom properties of an extension in an existing **group** instance.


> **Note:**
>
> - You can update **autoSubscribeNewMembers** by specifying it in its own PATCH request, without including the other properties in the table above.
> - Only a subset of the group API pertaining to core group administration and management support application and delegated permissions. All other members of the group API, including updating  **autoSubscribeNewMembers**, support only delegated permissions. See [known issues](https://developer.microsoft.com/graph/docs/overview/release_notes#group-permission-scopes) for examples.
> - The rules for updating mail-enabled security groups in Microsoft Exchange Server can be complex; to learn more, see [Manage mail-enabled security groups in Exchange Server](https://docs.microsoft.com/en-us/Exchange/recipients/mail-enabled-security-groups?view=exchserver-2019).
 


## Response

If successful, this method returns a `204 No Content` response code.

## Example

#### Request

The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_group"
}-->

```http
PATCH https://graph.microsoft.com/beta/groups/{id}
Content-type: application/json
Content-length: 211

{
  "description": "description-value",
  "displayName": "displayName-value",
  "groupTypes": [
    "groupTypes-value"
  ],
  "mail": "mail-value",
  "mailEnabled": true,
  "mailNickname": "mailNickname-value"
}
```

#### Response

The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.group"
} -->

```http
HTTP/1.1 204 No Content
```

## See also

- [Add custom data to resources using extensions](/graph/extensibility-overview)
- [Add custom data to users using open extensions (preview)](/graph/extensibility-open-users)
- [Add custom data to groups using schema extensions (preview)](/graph/extensibility-schema-groups)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Update group",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
