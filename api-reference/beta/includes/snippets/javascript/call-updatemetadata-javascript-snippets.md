---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const CommsOperation = {
  metadata: "metadata-value",
  clientContext: "clientContext-value"
};

let res = await client.api('/app/calls/{id}/updateMetadata')
	.version('beta')
	.post(CommsOperation);

```