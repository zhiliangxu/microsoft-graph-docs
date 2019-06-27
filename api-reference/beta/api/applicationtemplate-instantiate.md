---
title: "applicationTemplate: instantiate"
description: "Use this API to create a new applicationTemplate"
localization_priority: Normal
author: "luleonpla"
ms.prod: "microsoft-identity-platform"
doc_type: "apiPageType"
---

# applicationTemplate: instantiate

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Add an instance of an application from the Azure AD application gallery into your directory.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Directory.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Application.ReadWrite.All|

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /applicationTemplates/{id}/instantiate
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {code} |

## Request body

In the request body, provide a JSON object with the following parameters.

| Parameter    | Type        | Description |
|:-------------|:------------|:------------|
|displayName|String|Custom name of the application|

## Response

If successful, this method returns a `201 OK` response code and a new [applicationServicePrincipal](../resources/applicationserviceprincipal.md) object in the response body.

## Examples

The following example shows how to call this API.

### Request

The following is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "applicationtemplate_instantiate"
}-->

```http
POST https://graph.microsoft.com/beta/applicationTemplates/{id}/instantiate
Content-type: application/json

{
  "displayName": "My custom name"
}
```
# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/applicationtemplate-instantiate-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Javascript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/applicationtemplate-instantiate-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/applicationtemplate-instantiate-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### Response

The following is an example of the response.

> [!NOTE]
> The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.applicationServicePrincipal"
} -->

```http
HTTP/1.1 201 OK
Content-type: application/json

{
   "servicePrincipal": {
	  "accountEnabled": true,
	  "addIns": [
	    {
	      "id": "id-value",
	      "type": "type-value",
	      "properties": [
		{
		  "key": "key-value",
		  "value": "value-value"
		}
	      ]
	    }
	  ],
	  "appDisplayName": "appDisplayName-value",
	  "appId": "appId-value",
	  "appOwnerOrganizationId": "appOwnerOrganizationId-value",
	  "appRoleAssignmentRequired": true
   },
   "application": {
	  "api": {
	    "acceptedAccessTokenVersion": 1,
	    "publishedPermissionScopes": [
	      {
		"adminConsentDescription": "adminConsentDescription-value",
		"adminConsentDisplayName": "adminConsentDisplayName-value",
		"id": "id-value",
		"isEnabled": true,
		"type": "type-value",
		"userConsentDescription": "userConsentDescription-value",
		"userConsentDisplayName": "userConsentDisplayName-value",
		"value": "value-value"
	      }
	    ]
	  },
	  "allowPublicClient": true,
	  "applicationAliases": [
	    "applicationAliases-value"
	  ],
	  "createdDateTime": "datetime-value",
	  "installedClients": {
	    "redirectUrls": [
	      "redirectUrls-value"
	    ]
	  }
   }
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "applicationTemplate: instantiate",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
