---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let res = await client.api('/directoryObjects/delta')
	.version('beta')
	.filter('isOf('Microsoft.Graph.User')+or+isOf('Microsoft.Graph.Group')')
	.get();

```