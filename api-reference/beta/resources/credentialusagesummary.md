---
title: "credentialUsageSummary"
description: "Provides the summary of self-service password reset usage for a given tenant."
author: dkershaw
localization_priority: Normal
ms.prod: microsoft-identity-platform
---

# credentialUsageSummary resource type

Provides the summary of self-service password reset usage for a given tenant. This API provides the current state of how many users in your organization are using self-service password reset capabilities.

## Methods

| Method | Return Type | Description |
| ------ | ----------- | ----------- |
| [Get credentialUsageSummary](../api/reportroot-list-credentialusagesummary.md) | credentialUsageSummary | Read properties and relationships of the credentialUsageSummary object. |

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| authMethod | string | Provides the authentication method available for registration or used by end users during password resets or registrations. Possible values are: `email`, `mobileSMS`, `mobilePhone`, `officePhone`, `securityQuestion`, `appNotification`, `appNotificationCode`. See the [Enum values](#enum-values) section below. |
| failureActivityCount | Int64 | Provides the count of failed resets or registration data. |
| feature | string | Provides either the registration data or reset data. By default, both are shown. Possible values are: `registration`, `reset`. See the [Enum values](#enum-values) section below. |
| id | String | Read-only. | Unique Id of the activity. |
| successfulActivityCount | Int64 | Provides the count of successful registrations or resets. |

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
| fido | Can only be registered through combined security info registration. |
| alternateMobilePhone | |
| mobilePhoneAndSMS | |

### Feature Property

| Enum Name | Description |
| --------- | ----------- |

| registration | Indicates registration usage data. |
| reset | Indicates reset usage data. |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.credentialUsageSummary"
}-->

```json
{
  "id" : "d3590ed6-52b3-4102-aeff-aad2292ab01234",
  "feature":"registration",
  "successfulActivityCount":"12345",
  "failureActivityCount": "123",
  "authMethod": "email"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "credentialUsageSummary resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
