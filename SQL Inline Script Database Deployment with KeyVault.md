```
trigger: none

pool:
  vmImage: windows-latest

steps:

- task: SqlAzureDacpacDeployment@1
  inputs:
    azureSubscription: 'HurtadoManualConnection'
    AuthenticationType: 'server'
    ServerName: 'bhurtadoserver.database.windows.net'
    DatabaseName: 'hurtadotest'
    SqlUsername: '$(SQLUser)'
    SqlPassword: '$(SQLPassword)'
    deployType: 'InlineSqlTask'
    SqlInline: 'SELECT * FROM STUDENT'
    IpDetectionMethod: 'AutoDetect'


- task: AzureKeyVault@2
  inputs:
    azureSubscription: 'HurtadoManualConnection'
    KeyVaultName: 'HurtadoKV'
    SecretsFilter: '*'
    RunAsPreJob: true
```
