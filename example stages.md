```
trigger: none

pool:
  vmImage: ubuntu-latest

stages:
- stage: DEV
  jobs:
  - job: Job1Dev
    steps:
    - script: echo Hello, world!
      displayName: 'Run a one-line script'

    - script: |
        echo Add other tasks to build, test, and deploy your project.
        echo See https://aka.ms/yaml
      displayName: 'Run a multi-line script'

- stage: PROD
  jobs:
    - job: Job2Prod
      steps:
      - script: echo Hello, world!
        displayName: 'Run a one-line script'

      - script: |
          echo Add other tasks to build, test, and deploy your project.
          echo See https://aka.ms/yaml
        displayName: 'Run a multi-line script'
```
