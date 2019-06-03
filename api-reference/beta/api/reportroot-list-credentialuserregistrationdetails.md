---
title: "reportRoot: credentialUserRegistrationDetails"
description: "Provides the details of self-service password reset and multi-factor authentication (MFA) registration for a given tenant."
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
---

# Credentials Registration Details

Provides the details of self-service password reset and multi-factor authentication (MFA) registration for a given tenant. This API provides the registration usage for all registered users for self-service password reset and MFA capabilities. Details include user information, status of registration, and the authentication method used.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](../../../concepts/permissions_reference.md).

| Permission type | Permissions (from least to most privileged) |
| --------------- | ------------------------------------------- |
| Delegated (work or school account) | Reports.Read.All |
| Delegated (personal Microsoft account) | Not supported |
| Application | Reports.Read.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /reports/credentialUserRegistrationDetails
```

## Optional query parameters

This method supports the [OData Query Parameters](http://graph.microsoft.io/docs/overview/query_parameters) to help customize the response.

| Name | Description | Example | Supported Operators |
| ---- | ----------- | ------- | ------------------- |
| userDisplayName | Filter by UserName. | /reports/userCredentialUsageDetails?$filter=userDisplayName eq 'ABCD'| eq, startswith(), orderby, Supports case insensitive. |
| userPrincipalName | Filter by User Principal Name. | /reports/userCredentialUsageDetails?$filter=userPrincipalNameeq 'ABCD' | eq, startswith(), orderby, Supports case insensitive. |
| authMethods | Filter by the authentication methods using during registration. | /reports/userCredentialUsageDetails?$filter=authMethods/any(t:t eq 'email') | eq |
| isRegistered | Filter for users who have registered for SSPR. | /reports/userCredentialUsageDetails?$filter=isRegisteredeq true| eq, orderby |
| isEnabled | Filter for users who have been enabled for SPPR. | /reports/userCredentialUsageDetails?$filter=isEnabledeq true| eq, orderby |
| isCapable | Filter for users who are ready to perform password reset or MFA. | /reports/userCredentialUsageDetails?$filter=isCapable eq true| eq, orderby |
| isMfaRegistered | Filter for users who are registered for MFA. | /reports/userCredentialUsageDetails?$filter=isMfaRegistered eq true | eq, orderby |

## Request headers

| Name | Description |
| ---- | ----------- |
| Authorization | Bearer {code} |

## Response

If successful, this method returns a `200 OK` response code and collection of [credentialUserRegistrationDetails](../resources/credentialuserregistrationdetails.md) objects in the response body.

## Example

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "get_credentialuserregistrationdetails"
}-->

```http
GET https://graph.microsoft.com/beta/reports/credentialUserRegistrationDetails
```

### Response

The following is an example of the response. The response object shown here may be truncated for brevity. All of the properties are returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.credentialUserRegistrationDetails",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
  "@odata.context":"https://graph.microsoft.com/beta/reports/$metadata#Collection(microsoft.graph.credentialUserRegistrationDetails)",
  "value":[
    {
      "id" : "d3590ed6-52b3-4102-aeff-aad2292ab01234",
      "userPrincipalName":"abc@cd.com",
      "userDisplayName": "abc",
      "authMethods": {"email", "mobileSMS"},
      "isRegistered" : false,
      "isEnabled" : true,
      "isCapable" : false,
      "isMfaRegistered" : true
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List credentialUserRegistrationDetails",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
