---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var myDecisions = await graphClient.AccessReviews["2b83cc42-09db-46f6-8c6e-16fec466a82d"].MyDecisions
	.Request()
	.GetAsync();

```