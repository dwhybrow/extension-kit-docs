# Unit4 Ava push text

The **Unit4 Ava push text** action can be used to send personal notifications when something happens.

It sends a text to Ava using the provided _Unit4Id_. The _Unit4 Id_ and the current _Tenant_ must be the ones the target user uses to log in with Ava.

> Note: The _TenantId_ is part of the configuration, but it does not need to be provided and will not be displayed unless the user is logged into the U4EK Administration Portal with the Admin tenant.

## Action input

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Unit4 ID_ | Enter the Unit4 ID. You can enter the value, or use the [**Unit4Id resolver** action](https://docs-external.u4pp.com/extensions-kit/built-in-actions/u4id-resolver/) to retrieve it as in the example shown in the image. | Yes |
| _Notification text_ | Enter the desired text or use templating. It supports markdown and emoji notation `😊`. | Yes |

![Image 4: Ava push text](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/avapushtext-input.png)

## Action output

| **Property** | **Description** |
| --- | --- |
| _Succeeded_ | Shows the status of the action. |

![Image 5: Ava push text output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/avapushtext-output.png)
