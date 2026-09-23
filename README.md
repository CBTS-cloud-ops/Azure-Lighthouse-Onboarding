1. Register Microsoft.ManagedServices in every subscription. Policy-triggered deployments do not register providers. Run once:
```powershell
   Get-AzSubscription | ForEach-Object {
     Set-AzContext -SubscriptionId $_.Id | Out-Null
     Register-AzResourceProvider -ProviderNamespace Microsoft.ManagedServices
   }
```
2. Send customer a [link](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FCBTS-cloud-ops%2FAzure-Lighthouse-Onboarding%2Frefs%2Fheads%2Fmain%2FdeployLighthousePolicy.json) to the deployment template
3. Send customer a customized copy of `deployLighthousePolicy.parameters.json`