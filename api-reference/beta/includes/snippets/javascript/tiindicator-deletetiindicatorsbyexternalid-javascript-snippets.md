---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const ResultInfo = {
  value: [
    "externalId-value1",
    "externalId-value2"
  ]
};

let res = await client.api('/security/tiIndicators/deleteTiIndicatorsByExternalId')
	.version('beta')
	.post(ResultInfo);

```