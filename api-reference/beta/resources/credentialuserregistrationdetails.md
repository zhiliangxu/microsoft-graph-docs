---
title: "credentialUserRegistrationDetails"
description: "Provides the details of self-service password reset and multi-factor authentication (MFA) registration for a given tenant."
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
---

# credentialUserRegistrationDetails resource type

Provides the details of self-service password reset and multi-factor authentication (MFA) registration for a given tenant. This API provides the registration usage for all registered users for self-service password reset and MFA capabilities. Details include user information, status of registration, and the authentication method used.

## Methods

| Method | Return Type | Description |
| ------ | ----------- | ----------- |
| [Get credentialUserRegistrationDetails](../api/reportroot-list-credentialuserregistrationdetails.md) | credentialUserRegistrationDetails | Read properties and relationships of credentialUserRegistrationDetails object. |

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| authMethods | String | Provides the authentication method used by the user when performing a password reset or MFA. Possible values are: `email`, `mobileSMS`, `mobilePhone`, `officePhone`, `securityQuestion`, `appNotification`, `appNotificationCode`, `unknownFutureValue`. See the [Enum value details](#enum-values) below. |
| id | String | Read-only | Unique Id for the activity. |
| isCapable | Boolean | Indicates whether the user is ready to perform self-service password reset or MFA. |
| isEnabled | Boolean | Indiciates whether the user enabled to perform self-service password reset.|
| isRegistered | Boolean | Indicates whether the user is registered or not. |
| userDisplayName | String | Provides the user name of the corresponding user. |
| userPrincipalName | String | Provides the user principal name of the corresponding user. |

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
| appPassword | Can only be used for MFA. |
| fido | Can only be registered through combined security info registration. |
| alternateMobilePhone | |
| mobilePhoneAndSMS | |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.credentialUserRegistrationDetails"
}-->

```json

 
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
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "credentialUserRegistrationDetails resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
