---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var index = 3;

var values = new List<Json>()
{
	new Json
	{
	}
};

await graphClient.Me.Drive.Items["{id}"].Workbook.Tables["{id|name}"].Columns
	.Add(index,values,name)
	.Request()
	.PostAsync();

```