---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var contactFolder = await graphClient.Me.ContactFolders["{id}"]
	.Request()
	.GetAsync();

```