---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var worksheets = await graphClient.Me.Drive.Items["{id}"].Workbook.Worksheets
	.Request()
	.GetAsync();

```