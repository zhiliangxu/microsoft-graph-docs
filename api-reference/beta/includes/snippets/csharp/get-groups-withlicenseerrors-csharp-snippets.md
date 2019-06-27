---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var groups = await graphClient.Groups
	.Request()
	.Filter("hasMembersWithLicenseErrors+eq+true,")
	.Select( e => new {
			 e.Id,
			 e.DisplayName 
			 })
	.GetAsync();

```