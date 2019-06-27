---
title: "user: exportPersonalData"
description: "Submits a data policy operation request, made by a Company Administrator to export an organizational user's data."
localization_priority: Normal
author: "dkershaw10"
ms.prod: "microsoft-identity-platform"
---

# user: exportPersonalData

Submit a data policy operation request from a company administrator or an application to export an organizational user's data.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) |  User.Export.All, User.Read.All  |
|Delegated (personal Microsoft account) |  Not applicable  |
|Application | User.Export.All, User.Read.All |

>**Note:** The export can only be performed by a company administrator when delegated permissions are used.

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /users/{id}/exportPersonalData

```
## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer {token}|

## Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|storageLocation|String|This is a shared access signature (SAS) URL to an Azure Storage account, to where data should be exported.|

## Response
If successful, this method returns a `202 Accepted` response code. It does not return anything in the response body. The response contains the following response headers.

| Name       | Description|
|:---------------|:----------|
| Location  | URL to check on the status of the request. |
| Retry-After  | Time period in seconds. Request maker should wait this long after submitting a request to check for the status. |

## Example
##### Request
<!-- {
  "blockType": "request",
  "name": "user_exportpersonaldata"
}-->
```http
POST https://graph.microsoft.com/v1.0/users/{id}/exportPersonalData
Content-type: application/json
Content-length: 48

{
  "storageLocation": "storageLocation-value"
}
```
##### Response

```http
{
  Location: https://graph.microsoft.com/v1.0/dataPolicyOperations/d007e3da-cd9b-4b02-8d66-422403c53e3f
  Retry-After: 60
}
```
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.none"
} -->
```http
HTTP/1.1 202 Accepted
```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "user: exportPersonalData",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
