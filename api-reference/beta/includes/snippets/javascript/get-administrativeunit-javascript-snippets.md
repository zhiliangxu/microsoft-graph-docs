---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let res = await client.api('/education/schools/2961761D-8094-4183-A9F6-8E36E966C7D9/administrativeUnit')
	.version('beta')
	.get();

```