---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var directoryObject = await graphClient.DirectoryObjects["delta"]
	.Request()
	.Filter("isOf('Microsoft.Graph.User')+or+isOf('Microsoft.Graph.Group')")
	.GetAsync();

```