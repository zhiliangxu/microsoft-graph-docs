---
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
ms.date: 04/25/2019
---
# credentialUserRegistrationCount resource type

Provides the summary of self-service password reset and Multi-Factor Authentication registration for a given tenant. This API provides the current state of how many users in your organization are registered for self-service password reset and Multi-Factor Authentication capabilities.


## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [Get credentialUserRegistrationCount](../api/credentialuserregistrationcount_get.md) | [credentialUserRegistrationCount](credentialuserregistrationcount.md) | Read properties and relationships of credentialUserRegistrationCount object. |


## Properties
| Property     | Type        | Description |
|:-------------|:------------|:------------|
|id|String| Read-only.|Unique Id of the activity.|
|totalUserCount|Int64|Provides the total user count in the tenant.|
|userRegistrationCounts|[userRegistrationCount](userregistrationcount.md) collection| Provides the # of registered Users count.|

## Relationships
None


## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.credentialUserRegistrationCount"
}-->

```json
  {
      "id" : "d3590ed6-52b3-4102-aeff-aad2292ab01234",
      "totalUserCount" : 23123,
      "userRegistrationCounts" :
      [
        { "userRegistrationStatus":"registered", "userRegistrationCount": 23423 },
        { "userRegistrationStatus":"enabled", "userRegistrationCount": 4234 },
        { "userRegistrationStatus":"capable", "userRegistrationCount": 323 },
        { "userRegistrationStatus":"mfaRegistered", "userRegistrationCount": 33 },
      ]
    }

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "credentialUserRegistrationCount resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
