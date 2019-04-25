# credentialUsageSummary resource type
Provides the summary of self-service password reset usage for a given tenant. This API provides the current state of how many users in your organization are using self-service password reset capabilities.
---
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
ms.date: 04/25/2019
---
## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [Get credentialUsageSummary](../api/credentialusagesummary_get.md) | [credentialUsageSummary](credentialusagesummary.md) | Read properties and relationships of credentialUsageSummary object. |


## Properties
| Property     | Type        | Description |
|:-------------|:------------|:------------|
|authMethod|string| Provides the authentication method available for registration or used by end users during password resets or registrations. Possible values are: `email`, `mobileSMS`, `mobilePhone`, `officePhone`, `securityQuestion`, `appNotification`, `appNotificationCode`.Check out the [Enum values](#Enum-values-Details) section below.|
|failureActivityCount|Int64| Provides the count of failed resets or registration data.|
|feature|string| Povides either the registration data or reset data. By default, both will be shown. Possible values are: `registration`, `reset`. Check out the [Enum values](#Enum-values-Details) section below.|
|id|String| Read-only.|Unique Id of the activity.|
|successfulActivityCount|Int64|Provides the count of successful registrations or resets.|

## Enum values Details
### Auth Method Property
| Enum Name | Value | Description
| :---------|:-------|:----------
email	|0	
mobileSMS	|1	
mobilePhone|2	
officePhone	|3	
securityQuestion|4	|can only be used for self-service password reset	
appNotification	|5	
appNotificationCode|	6	
appNotificationAndCode|	7	
appPassword	|8	|can only be used for Multi-Factor Authentication
fido	|9	|can only be registered through combined security info registration
alternateMobilePhone	|10
mobilePhoneAndSMS	|11

### Feature Property
| Enum Name | Value | Description
| :---------|:-------|:----------
registration|0| Indicates registration usage data
reset|1| Indicates reset usage data

## Relationships
None


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
      "id" : "d3590ed6-52b3-4102-aeff-aad2292ab01234"
      "feature":"registration",
      "successfulActivityCount":"12345",
      "failureActivityCount": "123",
      "authMethod": "email",
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
