---
title: "Get signIn"
description: "Retrieve a specific Azure AD user sign-in event for your tenant."
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
---

# Get signIn

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a specific Azure AD user sign-in event for your tenant. Sign-ins that are interactive in nature (where a username/password is passed as part of authorization token) and successful federated sign-ins are currently included in the sign-in logs.


## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | AuditLog.Read.All |
|Delegated (personal Microsoft account) | Not supported   |
|Application | AuditLog.Read.All | 

In addition, apps must be [properly registered](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-prerequisites-azure-portal) to Azure AD.

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
GET /auditLogs/signIns/{id}
```

## Optional query parameters

This method supports OData query parameters to help customize the response. For details about how to use these parameters, see [OData query parameters](/graph/query_parameters).

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization  | Bearer {code}|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and [signIn](../resources/signin.md) object in the response body.

## Example

### Request

Here is an example of the request.

<!-- {
  "blockType": "request",
  "name": "get_signin"
}-->
```http
GET https://graph.microsoft.com/beta/auditLogs/signIns/{id}
```

### Response

Here is an example of the response. 

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.signIn"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 211
```

```json
{
	"@odata.context": "https://graph.microsoft.com/beta/$metadata#auditLogs/signIns",
	"value": [{
		"id": "id",
		"createdDateTime": "2018-01-09T21:17:21.5077253Z",
		"userDisplayName": "Jamie Doe",
		"userPrincipalName": "jdoe@contoso.com",
		"userId": "bbb3b4b5-e6e6-f7f5-f7f5-090805040302",
		"appId": "d3590ed6-52b3-4102-aeff-aad2292ab01c",
		"appDisplayName": "Azure",
		"ipAddress": "127.0.0.1",
		"status": {
			"errorCode": 0,
			"failureReason": null,
			"additionalDetails": "SignIn Success & CA Success"
		},
		"clientAppUsed": null,
		"deviceDetail": {
			"deviceId": "34390ed6-52b3-4102-aeff-aad2292abac3",
			"displayName": "DeviceName",
			"operatingSystem": "Windows 10",
			"browser": "Rich Client v3.14.1592.7",
			"isCompliant": true,
			"isManaged": true,
			"trustType": ""
		},
		"location": {
			"city": "Redmond",
			"state": "WA",
			"countryOrRegion": "USA",
			"geoCoordinates": {
				"altitude": 41.589,
				"latitude": 41.589,
				"longitude": -93.6151
			}
		},
		"mfaDetail": {
			"mfaAuthMethod": "Phone Auth",
			"mfaAuthDetail": null
		},
		"correlationId": "17c47d3c-593d-4d08-ac20-813892b87e42",
		"conditionalAccessApplied": true,
		"conditionalAccessPolicies": [{
			"id": "26490ed6-52b3-4102-aeff-aad2292abacf",
			"displayName": "capPolicy",
			"enforcedAccessControls": ["MFA", "TOU"],
			"enforcedSessionControls": ["CloudAppSecurity"],
			"result": "success"
		}],
		"isRisky": false,
		"riskLevel": "low"
	}]
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get signIn",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
