---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var criteria = new SynchronizationJobRestartCriteria
{
	ResetScope = SynchronizationJobRestartScope.QuarantineState | SynchronizationJobRestartScope.Escrows | SynchronizationJobRestartScope.ConnectorDataStore
};

await graphClient.ServicePrincipals["{id}"].Synchronization.Jobs["{jobId}"]
	.Restart(criteria)
	.Request()
	.Header("Authorization","Bearer <token>")
	.PostAsync();

```