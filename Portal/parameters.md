# Tenant parameters

The **Parameters** page allows users with the **Owner** role to define and maintain specific parameters for the tenant. These parameters can be referred to in any action of any flow, so the preset values will be included at runtime.

## Add a new parameter

To add a new parameter, click on the **New parameter** button and a pop-up window appears with the values to be configured. The _Name_ field sets the parameter name that is used to reference it. The _Value_ field defines the standard value that is inserted in the flows. When you save the parameter it is added to the list of available parameters.

![Image 7: Create parameter](https://docs-external.u4pp.com/extensions-kit/images/portal/parameters-create-parameter.png)

## Sensitive data

When the **Sensitive data** button is activated, the parameter value is hidden after it is created.

![Image 8: Parameters](https://docs-external.u4pp.com/extensions-kit/images/portal/parameters-sensitive-data.png)

## Edit a parameter

You can edit parameter values at any time by clicking on the existing parameter to open a pop-up window displaying the current parameter's configuration. You can edit the _Value_ field even if the **Sensitive data** button is activated.

![Image 9: Parameters edit](https://docs-external.u4pp.com/extensions-kit/images/portal/parameters-edit.png)

## Usage

Once you have defined a parameter, it can be referenced by any action in the flow, either by using `{{parameters:'name'}}`, or by selecting it from the **Templating** drop-down using **Plus (+)** button on the right side of the field. Once selected, the parameter's reference is automatically added.

![Image 10: Parameters use](https://docs-external.u4pp.com/extensions-kit/images/portal/parameters-add.png)

## Input

```javascript
{
    "StopWith": "Success",
    "Summary": "'value'\n\nInclude 'value' in the middle of the message"
    }
```

## Delete a parameter

You delete a parameter by clicking the trash can icon on the right side of the list. This action cannot be undone.

![Image 11: Parameters](https://docs-external.u4pp.com/extensions-kit/images/portal/parameters-sensitive-data.png)
