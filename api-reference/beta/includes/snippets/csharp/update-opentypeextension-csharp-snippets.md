---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var extension = new Extension
{
	ExtensionName = "Com.Contoso.Estimate",
	CompanyName = "Contoso",
	ExpirationDate = "2016-07-30T11:00:00Z",
	DealValue = 1010100,
	TopPicks = new List<String>()
	{
		"Employees only",
		"Add spouse or guest",
		"Add family"
	}
};

await graphClient.Groups["37df2ff0-0de0-4c33-8aee-75289364aef6"].Threads["AAQkADJizZJpEWwqDHsEpV_KA=="].Posts["AAMkADJiUg96QZUkA-ICwMubAADDEd7UAAA="].Extensions["Microsoft.OutlookServices.OpenTypeExtension.Com.Contoso.Estimate"]
	.Request()
	.UpdateAsync(extension);

```