### Why ARM templates
- Its an automated way of deploying resource in azure
- Even the configurational changes to the existing resources can be done using arm templates. example: Configuring back-up on existing vm, configuring log anaystics to monitor the vm
- It is a native IaC tool for azure


#### Blank ARM Template
```json{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
  },
  "variables": {
  },
  "resources": [
  ],
  "outputs": {
  }
}
```
$schema defines the template we use to deploy resources

![templateSchema!](notes\images\templateSchema.png "template Schema")

If you see carefully the above JSON template,*parameters* , *variables*  and *outputs* are JSON Objects, while *resources* is JSON array.

A typical *parameter* would look as below
```json{
"adminUsername":{
    "type":"string",
    "minLength": 1,
    "metadata" : {
        "description":"Username for the VM"
    }
}
```

A typical *variables* would look as below
```json{
"variables":{
    "variable 1":"Value 1",
    "variable 2": 1
}
```

A *resource* component has below properties
- apiVersion (Mandatory)
- type (Mandatory)
- name (Mandatory)
- location
- tags
- dependsOn
- properties
- resources

```json{
    "resources:[{},
    {}]"
    }```


    `az group create -n LearnARM -l eastus`

    `az group deployment validate -g LearnARM --template-file "azure-deploy.json" --parameters "azure-deply.parameters.json" --verbose`

    `az group deployment create -g LearnARM -n arm3 --template-file "azure-deploy.json" --parameters "azure-deply.parameters.json" --verbose`