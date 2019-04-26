# userRegistrationCount resource type
Provides the registration count and status for users in your tenant.

---
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
ms.date: 04/25/2019
---


## Properties
| Property     | Type        | Description |
|:-------------|:------------|:------------|
|registrationCount|Int64| Provides the registration count for your tenant|
|registrationStatus|String|Provides the registration status for each registration in your tenant. Possible values are: `registered`, `enabled`, `capable`, `mfaRegistered`, `unknownFutureValue`. Check out the [Enum values](#Enum-values-Details) section below.|

## Enum Values 

### registrationStatus Property
| Enum Name | Value | Description|
| :---------|:-------|:----------|
registered|	0| User is registered for self-service password reset.|
enabled|	1	| User is enabled for self-service password reset. |
capable|	2	| User is ready to perform Multi-Factor Authentication or self-service password reset. This is calculated based on registered and enabled status.|
mfaRegistered|	3	| User is registered for Multi-Factor Authentication.|




## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.userRegistrationCount"
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
  "description": "userRegistrationCount resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
