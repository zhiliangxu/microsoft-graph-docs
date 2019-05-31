---
title: "List agreements"
description: "Retrieve a list of agreement objects."
localization_priority: Normal
---

# List agreements

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a list of [agreement](../resources/agreement.md) objects.
## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type                        | Permissions (from least to most privileged)              |
|:--------------------------------------|:---------------------------------------------------------|
|Delegated (work or school account)     | Agreement.Read.All |
|Delegated (personal Microsoft account) | Not supported. |
|Application                            | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /agreements
```

## Optional query parameters
This method supports the below list of query parameters to help customize the response.  


| Name         | Value      | Description |
|:-------------|:------------|:------------|
|[$select](https://docs.microsoft.com/en-us/graph/query-parameters#select-parameter)|string|Comma-separated list of properties to include in the response.|
|[$count](https://docs.microsoft.com/en-us/graph/query-parameters#count-parameter)|none|The count of related entities can be requested by specifying the $count query option.|
|[$filter](https://docs.microsoft.com/en-us/graph/query-parameters#filter-parameter)|string|Filter string that lets you filter the response based on a set of criteria.|
|[$orderby](https://docs.microsoft.com/en-us/graph/query-parameters#orderby-parameter)|string|Comma-separated list of properties that are used to sort the order of items in the response collection.|

For more information on the supported parameters, see [OData Query Parameters](https://developer.microsoft.com/graph/docs/concepts/query_parameters).


## Request headers
| Name         | Type        | Description |
|:-------------|:------------|:------------|
| Authorization | string | Bearer \{token\}. Required. |

## Request body
Do not supply a request body for this method.
## Response
If successful, this method returns a `200 OK` response code and collection of [agreement](../resources/agreement.md) objects in the response body.
## Example
##### Request
<!-- {
  "blockType": "request",
  "name": "get_agreements"
}-->
```http
GET https://graph.microsoft.com/beta/agreements
```
##### Response
>**Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.agreement",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 146

{
  "value": [
    {
      "displayName": "displayName-value",
      "isViewingBeforeAcceptanceRequired": true,
      "id": "id-value"
    }
  ]
}
```
#### SDK sample code
# [C#](#tab/cs)
[!INCLUDE [sample-code](../includes/get_agreements-Cs-snippets.md)]

# [Javascript](#tab/javascript)
[!INCLUDE [sample-code](../includes/get_agreements-Javascript-snippets.md)]

---

[!INCLUDE [sdk-documentation](../includes/snippets_sdk_documentation_link.md)]

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "List agreements",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
    "Error: /api-reference/beta/api/agreement-list.md:\r\n      BookmarkMissing: '[#tab/cs](C#)'. Did you mean: #c (score: 5)",
    "Error: /api-reference/beta/api/agreement-list.md:\r\n      BookmarkMissing: '[#tab/javascript](Javascript)'. Did you mean: #javascript (score: 4)"
  ]
}
-->
