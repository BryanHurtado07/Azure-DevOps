```
trigger: none

pool:
  vmImage: windows-latest

steps:
- task: AzureCLI@2
  inputs:
    azureSubscription: 'hurtadoManualConnection'
    scriptType: 'ps'
    scriptLocation: 'inlineScript'
    inlineScript: |
      az webapp stop --name huratdo-netapp `
      --resource-group V-BHURTADO-RG
```
