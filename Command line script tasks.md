```
trigger: none

pool:
  vmImage: windows-latest

steps:
- task: CmdLine@2
  inputs:
    script: 'echo Esto es un command line'

- task: Bash@3
  inputs:
    targetType: 'inline'
    script: 'echo Esto es un bash'

- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: 'Write-Host "Esto es un powershell"'
```
  
