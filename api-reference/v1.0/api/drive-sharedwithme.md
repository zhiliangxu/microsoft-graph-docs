---
author: JeremyKelley
ms.author: JeremyKelley
ms.date: 09/10/2017
title: List Files Shared With Me
localization_priority: Priority
ms.prod: "sharepoint"
---
# List items shared with the signed-in user

Retrieve a collection of [DriveItem](../resources/driveitem.md) resources that have been shared with the owner of the [Drive](../resources/drive.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All    |
|Delegated (personal Microsoft account) | Files.Read.All, Files.ReadWrite.All    |
|Application | Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All |

**Note:** while the /sharedWithMe request will succeed with Files.Read or Files.ReadWrite permissions, some properties may be missing.
Additionally, without one of the  **All** permissions, shared items returned from this API will not be accessible.

## HTTP request

<!-- { "blockType": "request", "name": "shared-with-me", "scopes": "files.read", "tags": "service.graph", "target": "action" } -->

```http
GET /me/drive/sharedWithMe
```

## Response

This returns a collection of [DriveItem](../resources/driveitem.md) resources which contain the DriveItem resources shared with the owner of the drive.
In this example, since the drive is the user's default drive, this returns items shared with the signed in user.

<!-- {"blockType": "response", "@odata.type": "Collection(microsoft.graph.driveItem)", "truncated": true} -->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "1312abc",
      "remoteItem": {
        "id": "1991210caf!192",
        "name": "March Proposal.docx",
        "file": { },
        "size": 19121,
        "parentReference": {
          "driveId": "1991210caf",
          "id": "1991210caf!104"
        }
      }
    },
    {
      "id": "1312def",
      "remoteItem": {
        "id": "1991210caf!1991",
        "name": "Team Roster.xlsx",
        "file": { },
        "size": 37619,
        "parentReference": {
          "driveId": "1991210caf",
          "id": "1991210caf!104"
        }
      }
    }
  ]
}
```
#### SDK sample code
# [C#](#tab/cs)
[!INCLUDE [sample-code](../includes/shared-with-me-Cs-snippets.md)]

# [Javascript](#tab/javascript)
[!INCLUDE [sample-code](../includes/shared-with-me-Javascript-snippets.md)]

# [Objective-C](#tab/objective-c)
[!INCLUDE [sample-code](../includes/shared-with-me-Objective-C-snippets.md)]
---

[!INCLUDE [sdk-documentation](../includes/snippets_sdk_documentation_link.md)]

## Remarks

DriveItems returned from the **sharedWithMe** action will always include the [**remoteItem**](../resources/remoteitem.md) facet which indicates they are items from a different drive.
To access the shared DriveItem resource, you will need to make a request using the information provided in **remoteItem** in the following format:

<!-- { "blockType": "ignored", "name": "drives-get-remoteitem" } -->

```http
GET /drives/{remoteItem-driveId}/items/{remoteItem-id}
```

<!-- {
  "type": "#page.annotation",
  "description": "List the items shared with the owner of a drive.",
  "keywords": "drive,onedrive.drive,default drive",
  "section": "documentation",
  "tocPath": "Sharing/Shared with me",
  "suppressions": [
    "Error: /api-reference/v1.0/api/drive-sharedwithme.md:\r\n      BookmarkMissing: '[#tab/objective-c](Objective-C)'. Did you mean: #objective-c (score: 4)",
    "Error: /api-reference/v1.0/api/drive-sharedwithme.md:\r\n      BookmarkMissing: '[#tab/cs](C#)'. Did you mean: #c (score: 5)",
    "Error: /api-reference/v1.0/api/drive-sharedwithme.md:\r\n      BookmarkMissing: '[#tab/javascript](Javascript)'. Did you mean: #javascript (score: 4)"
  ]
} -->
