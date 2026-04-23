# Export and import a flow

You can export and import flows to:

*   Reuse flows: Reuse of pre-built flows across different clients or environments. Once a flow is designed and tested, it can be exported and reused in similar scenarios, saving time and effort in recreating similar flows from scratch.
*   Collaboration: Easy export and import of flows enables sharing of flows.
*   Version control and backup: Exported flows can be versioned and stored as backups, and reimported if required, to roll back to a previous version.

## Export a flow

You can export a flow:

*   From the **Bottom** toolbar in the **Flow editor** selecting the **More** button.
*   From the **Three dots** menu in each **Flow card**.

Exporting a flow creates a JSON file with the flow definition and parameters, including each parameter’s sensitivity.

> Note: Sensitive data is not included in the resulting JSON file.

Example of an exported flow's JSON file:

```json
{
  "FlowDefinitions": [
    {
      "FlowId": "id",
      "FlowType": "Customer",
      "ProductId": "",
      "DeveloperId": "",
      "DeveloperName": "",
      "Version": 4,
      "Description": "export parameters",
      "UserId": "u4pp-sandbox-directory\\user",
      "Trigger": {
        "Type": "http-webhook",
        "Version": 2,
        "Config": {
          "Name": "123",
          "TenantId": null,
          "AuthenticationType": "None"
        }
      },
      "Actions": [
        {
          "Type": "stop",
          "Version": 1,
          "Filter": [],
          "Condition": [],
          "Input": {
            "Name": "name",
            "Properties": [
              {
                "Name": "StopWith",
                "Value": {
                  "Text": "Success"
                }
              },
              {
                "Name": "Summary",
                "Value": {
                  "Text": "{{parameters.test}}"
                }
              }
            ]
          }
        }
      ],
      "IsParked": false,
      "Status": "Active",
      "Configuration": {
        "IsSensitive": false
      }
    }
  ],
  "Parameters": [
    {
      "Name": "test",
      "Sensitive": false
    }
  ]
}
```

## Export a flow as an app

You can export a flow as an app:

*   From the **Bottom** toolbar in the **Flow editor** selecting the **More** button.
*   From the **Three dots** menu in each **Flow card**.

This function is tailored for creating **Marketplace** flows, it creates a JSON file with the flow definition and parameters, including each parameter’s sensitivity.

When you select the **Export as an app** button, the **Export as an app** modal appears with the following mandatory fields:

| Field | Description |
| --- | --- |
| _Product Id_ | A unique identifier of the **Marketplace** flows. This field can only contain lower-case letters, numbers, dashes and underscores. |
| _Developer Id_ | A unique identifier of the developer of the flow. This field can only contain lower-case letters, numbers, dashes and underscores. |
| _Developer name_ | The commercial name of the developer. This field that can accept any character. |

Select the **Export** button to export the flow as an app.

Example of an exported as an app flow's JSON file:

```json
{
  "FlowDefinitions": [
    {
      "FlowId": "6e847f5c-398c-4086-a478-632b0af954bf",
      "FlowType": "Marketplace",
      "ProductId": "u4mesh-product-id1_v1-1",
      "DeveloperId": "dev-id_123345_azerty",
      "DeveloperName": "Unit4 Industry Mesh (R & D)",
      "Version": 16,
      "Description": "[TEST CASE] JSON to XML",
      "UserId": "u4pp-sandbox-directory\\user",
      "Trigger": {
...
```

> Note: The difference between **Export** and **Export as an app** is these four fields in the header: `FlowType`, `ProductId`, `DeveloperId` and `DeveloperName`.

## Import a flow

To import a flow from a JSON file, select the **"Import"** button in the **Bottom** toolbar in the **Flow overview**:

> Note: The corresponding parameters are also created in the current tenant, with the sensitive setting as detailed in the file. If any parameter already exists in the current tenant, it is not overwritten.

To import a flow:

1.   Select the **Import** button to open the **Import flow** dialog.

2.   Drag or select the flow's JSON file.

> Note: if you are using an exported file, you should edit it to populate the sensitive fields that have been cleared in the exporting process.

1.   Select the **Save** button to open the flow in the **Flow editor**.

To enable the imported flow:

1.   Turn on the **Status** switch to enable the flow. The switch is blue when on.
2.   Follow the wizard steps, these will depend on the flow definition: 

![Image 3: Imported flow wizard](https://docs-external.u4pp.com/extensions-kit/images/portal/import-define-values-sftp.png)

*   Step 1: **Parameters**. 

The following list is displayed:

| Field | Description |
| --- | --- |
| _Name_ | The name of the parameter as defined in the imported flow. |
| _Value_ | The value assigned to the parameter. If the parameter did not exist previously in the tenant, you must assign a value. Click inside the _Value_ field to open the **Edit parameter** dialog. The **Sensitive data** switch is just informative, you must configure it the the **Parameters** menu if required. |

*   Step 2: **Certificates**. 

The following list is displayed:

| Field | Description |
| --- | --- |
| _Step description_ | The name of the step with a certificate of the imported flow. |
| _Label_ | The name of the label in the action of the imported flow. |
| _Value_ | The value assigned to the certificate. You can open the drop-down to edit it. If no corresponding certificate is available in the host client, then you must add it in the **Certificates** menu. |

*   Step 3: **SFPT connections**. 

The following list is displayed:

| Field | Description |
| --- | --- |
| _Step description_ | The name of the step with an SFTP connection of the imported flow. |
| _Label_ | The name of the label in the action of the imported flow. |
| _Value_ | The value assigned to the connection. You can open the drop-down to edit it. If no corresponding SFTP connection is available in the host client, then it must be defined in the **SFTP connections** menu. |

*   Step 4: **Authentication**. 

This step appears for imported flows with a **Webhook** trigger and a _Basic authentication_ type. The following list is displayed:

| Field | Description |
| --- | --- |
| _Step description_ | The name of the step with the Authentication setup. |
| _Label_ | The name of the label in the _Authentication_ method in the **Webhook** trigger of the imported flow. |
| _Value_ | The value assigned to the _Label_. |

> Note: If you disable a flow and reenable it, the data set in the previous activation is saved and can be changed in a later activation if required.
