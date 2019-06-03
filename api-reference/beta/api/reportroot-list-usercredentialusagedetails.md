---
title: "reportRoot: userCredentialUsageDetails"
description: "Provides the details of self-service password reset usage for a given tenant."
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
---

# List Credentials Usage Details 

Provides the details of self-service password reset usage for a given tenant. Details include user information, status of the reset, and the reason for failure.

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
GET /reports/userCredentialUsageDetails

```

## Optional query parameters

This method supports the [OData Query Parameters](http://graph.microsoft.io/docs/overview/query_parameters) to help customize the response.

| Name | Description | Example | Supported Operators |
| ---- | ----------- | ------- | ------------------- |
| period | Filter using the time period for which you need the usage data. | /reports/getCredentialUsageSummary(period='D30') /reports/getCredentialUsageSummary(period='d30')| D1, D7, D30. Period is case insensitive. |
| feature | Filter by the type of usage data you want (registration vs. reset). | /reports/getCredentialUsageSummary(period='D30') ?$filter=feature eq 'registration' | eq |

## Request headers

| Name | Description |
| ---- | ----------- |
| Authorization | Bearer {code} |

## Response

If successful, this method returns a `200 OK` response code and collection of [userCredentialUsageDetails](../resources/usercredentialusagedetails.md) objects in the response body.

## Example

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "get_usercredentialusagedetails"
}-->

```http
GET https://graph.microsoft.com/beta/reports/userCredentialUsageDetails
```

### Response

The following is an example of the response. The response object shown here may be truncated for brevity. All of the properties are returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.userCredentialUsageDetails",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 258

Content-Type: application/json
{
  "@odata.context":"https://graph.microsoft.com/beta/reports/$metadata#Collection(microsoft.graph.getUserCredentialUsageDetails)",
  "value":[
    {
      "id" : "d3590ed6-52b3-4102-aeff-aad2292ab01234",
      "feature":"registration",
      "userPrincipalName":"abc@cd.com",
      "userDisplayName": "abc",
      "isSuccess" : true,
      "authMethod": "email",
      "failureReason": "User contacted an admin after trying the email verification option",
      "eventDateTime" : "2019-04-01T00:00:00Z"
    },
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List userCredentialUsageDetails",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
