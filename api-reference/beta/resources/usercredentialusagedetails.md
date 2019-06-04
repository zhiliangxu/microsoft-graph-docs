---
title: "userCredentialUsageDetails"
description: "Provides the details of self-service password reset usage for a given tenant."
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
---

# userCredentialUsageDetails resource type

Provides the details of self-service password reset usage for a given tenant. Details include user information, status of the reset, and the reason for failure.

## Methods

| Method | Return Type | Description |
| ------ | ----------- | ----------- |
| [Get userCredentialUsageDetails](../api/usercredentialusagedetails_get.md) | [userCredentialUsageDetails](usercredentialusagedetails.md) | Provides the usage details on self-service password reset for the last 30 days. |


## Properties

| Property | Type | Description | 
| -------- | ---- | ----------- |
| authMethod | string | Provides the authentication method used by the user when performing a password reset or multi-factor authentication. Possible values are: `email`, `mobileSMS`, `mobilePhone`, `officePhone`, `securityQuestion`, `appNotification`, `appNotificationCode`, `unknownFutureValue`. See the [Enum values](#enum-values) section below. |
| failureReason | String | Provides the failure reason for the corresponding reset. |
| feature | string | Possible values are: `registration`, `reset`, `unknownFutureValue`. See the [Enum values](#Enum-values-Details) section below. |
| id | String | Read-only | Unique Id of the activity. |
| isSuccess | Boolean | Indicates success or failure. |
| userDisplayName | String | User name of the user performing the reset. |
| userPrincipalName | String | User Principal Name of the user performing the reset. |

## Enum values

### Auth Method Property

| Enum Name | Description |
| --------- | ----------- |
| email | |
| mobileSMS | |
| mobilePhone | |
| officePhone | |
| securityQuestion | Can only be used for self-service password reset. |
| appNotification | |
| appNotificationCode | |
| appNotificationAndCode | |
| appPassword | Can only be used for multi-factor authentication. |
| fido | Can only be registered through combined security information registration. |
| alternateMobilePhone | |
| mobilePhoneAndSMS | |


### Feature Property

| Enum Name | Description |
| --------- | ----------- |
| registration | Indicates registration usage data. |
| reset| Indicates reset usage data. |

## Relationships

None.

## JSON representation


The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.userCredentialUsageDetails"
}-->

```json
  {
      "id" : "d3590ed6-52b3-4102-aeff-aad2292ab01234",
      "feature":"registration",
      "userPrincipalName":"abc@cd.com",
      "userDisplayName": "abc",
      "isSuccess" : true,
      "authMethod": "email",
      "failureReason": "User contacted an admin after trying the email verification option",
      "eventDateTime" : "2019-04-01T00:00:00Z"
  }

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "userCredentialUsageDetails resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
