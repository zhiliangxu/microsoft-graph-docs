---
title: "Start sync after uploading files to an educationSynchronizationProfile"
description: "Verify the files uploaded to a specific school data synchronization profile in the tenant. If the verification is successful, synchronization will start on the profile. Otherwise, the response will contain errors and warnings. If the response contains errors, the synchronization will not start. If the response contains only warnings, synchronization will start."
localization_priority: Normal
author: "mmast-msft"
ms.prod: "education"
---

# Start sync after uploading files to an educationSynchronizationProfile

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Verify the files uploaded to a specific school data [synchronization profile](../resources/educationsynchronizationprofile.md) in the tenant. If the verification is successful, synchronization will start on the profile. Otherwise, the response will contain errors and warnings. If the response contains errors, the synchronization will not start. If the response contains only warnings, synchronization will start.

> **Note:** Use this method only when the data provider is of type [educationcsvdataprovider](../resources/educationcsvdataprovider.md). Also, the profile's state property needs to be provisioned before it can be started. Poll the profile object to check its state property.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type | Permissions |
|:-----------|:----------|
| Delegated (work or school account) | EduAdministration.ReadWrite |
|Delegated (personal Microsoft account|Not supported.|
|Application|Not supported.|

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /synchronizationProfiles/{id}/start
```

## Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer {token}. Required.  |

## Request body
Do not supply a request body for this method.
## Response
If successful, this method returns a `200 OK` response code. If unsuccessful, it returns a `400 Bad Request`. The response contains a collection of [educationFileSynchronizationVerificationMessage](../resources/educationfilesynchronizationverificationmessage.md) objects as part of the response body if any errors or warnings were found.

## Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "post_educationSynchronizationProfile_start"
}-->
```http
POST https://graph.microsoft.com/beta/education/synchronizationProfiles/{id}/start
```

##### Response
Here is an example of the response. 

>**Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationFileSynchronizationVerificationMessage",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 2105

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#education/Collection(microsoft.graph.verificationMessage)",
    "value": [
        {
            "type": "Error",
            "fileName": "section.csv",
            "description": "5 row(s) have missing data for the field - SIS ID"
        },
        {
            "type": "Error",
            "fileName": "section.csv",
            "description": "5 row(s) have an invalid format for the field - SIS ID"
        },
        {
            "type": "Warning",
            "fileName": "student.csv",
            "description": "3 duplicates found in column SIS ID which requires values to be Unique."
        },
        {
            "type": "Warning",
            "fileName": "student.csv",
            "description": "3 duplicates found in column Username which requires values to be Unique."
        },
        {
            "type": "Error",
            "fileName": "studentenrollment.csv",
            "description": "125 row(s) have referenced data not found in source. Field - Section SIS ID"
        },
        {
            "type": "Error",
            "fileName": "studentenrollment.csv",
            "description": "35 row(s) have referenced data not found in source. Field - SIS ID"
        },
        {
            "type": "Warning",
            "fileName": "teacher.csv",
            "description": "3 duplicates found in column SIS ID which requires values to be Unique."
        },
        {
            "type": "Warning",
            "fileName": "teacher.csv",
            "description": "3 duplicates found in column Username which requires values to be Unique."
        },
        {
            "type": "Error",
            "fileName": "teacherroster.csv",
            "description": "10 row(s) have referenced data not found in source. Field - Section SIS ID"
        },
        {
            "type": "Error",
            "fileName": "teacherroster.csv",
            "description": "91 row(s) have referenced data not found in source. Field - SIS ID"
        }
    ]
}
```
#### SDK sample code
# [Javascript](#tab/javascript)
[!INCLUDE [sample-code](../includes/post_educationSynchronizationProfile_start-Javascript-snippets.md)]

# [C#](#tab/cs)
[!INCLUDE [sample-code](../includes/post_educationSynchronizationProfile_start-Cs-snippets.md)]

# [Objective-C](#tab/objective-c)
[!INCLUDE [sample-code](../includes/post_educationSynchronizationProfile_start-Objective-C-snippets.md)]
---

[!INCLUDE [sdk-documentation](../includes/snippets_sdk_documentation_link.md)]
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79 
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Example",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
    "Error: /api-reference/beta/api/educationsynchronizationprofile-start.md:\r\n      BookmarkMissing: '[#tab/objective-c](Objective-C)'. Did you mean: #objective-c (score: 4)",
    "Error: /api-reference/beta/api/educationsynchronizationprofile-start.md:\r\n      BookmarkMissing: '[#tab/cs](C#)'. Did you mean: #c (score: 5)",
    "Error: /api-reference/beta/api/educationsynchronizationprofile-start.md:\r\n      BookmarkMissing: '[#tab/javascript](Javascript)'. Did you mean: #javascript (score: 4)"
  ]
}-->
