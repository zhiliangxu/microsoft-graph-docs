---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let res = await client.api('/directoryroles/{id}/members/{id}/$ref')
	.version('beta')
	.delete();

```