---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.AccessReviews["2b83cc42-09db-46f6-8c6e-16fec466a82d"].Reviewers["006111db-0810-4494-a6df-904d368bd81b"]
	.Request()
	.DeleteAsync();

```