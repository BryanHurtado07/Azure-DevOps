```
trigger: none

pool:
  vmImage: ubuntu-latest

steps:
- script: echo Hello, world!
  displayName: 'Run a one-line script'

- template: templates/plantilla.yml
```
