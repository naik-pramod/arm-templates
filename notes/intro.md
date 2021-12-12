### Why ARM templates
- Its an automated way of deploying resource in azure
- Even the configurational changes to the existing resources can be done using arm templates. example: Configuring back-up on existing vm, configuring log anaystics to monitor the vm


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

If you see carefully the above JSON template,*parameters* , *variables*  and *outputs* are JSON Objects, while *resources* is JSON array.

A typicall parameter would look as below
```json "adminUsername":{
    "type":"string",
    "minLength": 1,
    "metadata" : {
        "description":"Username for the VM"
    }
}
```