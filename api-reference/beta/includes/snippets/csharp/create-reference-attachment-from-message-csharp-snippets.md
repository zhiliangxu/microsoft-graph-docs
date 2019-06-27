---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var attachment = new Attachment
{
	Name = "Personal pictures",
	SourceUrl = "https://contoso.com/personal/mario_contoso_net/Documents/Pics",
	ProviderType = "oneDriveConsumer",
	Permission = "Edit",
	IsFolder = "True"
};

await graphClient.Me.Messages["AAMkAGE1M88AADUv0uFAAA="].Attachments
	.Request()
	.AddAsync(attachment);

```