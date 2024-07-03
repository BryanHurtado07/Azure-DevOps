```
trigger: none

pool:
  vmImage: ubuntu-latest

# sintaxis corta:
# variables:
#   system.debug: true 
#   apellido: 'Hurtado'


# sintaxis larga:
variables:
- group: TrainingMay
- name: system.debug
  value: true
- name: segundavariable
  value: segundovalor


steps:
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: |
      # Write your PowerShell commands here.
      
      Write-Host Nombre $(nombre) Apellido $(apellido)

- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: 'Get-ChildItem env:'
```
