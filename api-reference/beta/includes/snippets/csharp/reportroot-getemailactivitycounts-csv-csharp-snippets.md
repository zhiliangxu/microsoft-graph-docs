---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var getEmailActivityCounts = await graphClient.Reports.GetEmailActivityCounts('D7')
	.Request()
	.GetAsync();

```