---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var attachment = new Attachment
{
	Name = "menu.txt",
	ContentBytes = "base64bWFjIGFuZCBjaGVlc2UgdG9kYXk="
};

await graphClient.Me.Events["AAMkAGI1AAAt9AHjAAA="].Attachments
	.Request()
	.AddAsync(attachment);

```