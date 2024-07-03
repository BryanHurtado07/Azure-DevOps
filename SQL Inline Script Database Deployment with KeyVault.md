```
trigger: none

pool:
  vmImage: windows-latest

steps:

# Deploy an Azure SQL Database using DACPAC or run scripts using SQLCMD.
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

# Download Azure Key Vault secrets.
- task: AzureKeyVault@2
  inputs:
    azureSubscription: 'HurtadoManualConnection'    # string. Alias: ConnectedServiceName. Required. Azure subscription.
    KeyVaultName: 'HurtadoKV'                       # string. Required. Key vault. 
    SecretsFilter: '*'                              # string. Required. Secrets filter. Default: *.
    RunAsPreJob: true                               # boolean. Make secrets available to whole job. Default: false.
```
