---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const administrativeUnit = {
    displayName: "Seattle District Technical Schools",
    description: "Seattle district technical schools administration",
    visibility: "true"
};

let res = await client.api('/administrativeUnits')
	.version('beta')
	.post({administrativeUnit : administrativeUnit});

```