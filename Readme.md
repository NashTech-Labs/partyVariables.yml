## Pipeline Requirements

The setVariable pipeline requires the following parameters to be defined:
Paramaters:


| Name  | type | Default | Values | Opional/Required | Comments |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| appDeploymentTarget | string | | | Required | |
| key | string | | | Required | |
| enablepartyVariables | boolean | 'true' | 'true'/'false' | Required | |



  These parameters provide multiple use case options for the setvariables templates pipeline, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

### Direct use of a template

You can directly call a particular template as per the requirement. for example: to use setup and init only.

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: Github-endpoint/ADO.Pipelines.Templates
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'


  steps:

  - template: frameWork/common/setVariables/templates/partyVariables.yml
      parameters:
        appDeploymentTarget: ${{parameters.appDeploymentTarget}}
        key: ${{parameters.key}}

Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.

  ```
