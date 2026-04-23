# Unit4 Ava question

The **Unit4 Ava question** action is used to send a question to a specific user through Unit4 Ava. It sends the question to Ava using the provided _Unit4Id_. The _Unit4 Id_ and the current _Tenant_ must be the ones the target user uses to log in with Ava.

> Note: The _TenantId_ is part of the configuration, but it does not need to be provided and will not be displayed unless the user is logged into the U4EK Administration Portal with the Admin tenant.

Multiple **Ava question** actions can be combined in a flow. Together with the [**Ava push text** action](https://docs-external.u4pp.com/extensions-kit/built-in-actions/da-push-text/) can be used to create an advanced conversation flow.

## Action input

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Unit4 ID_ | Enter the Unit4 ID. You can enter the value, or use the [**Unit4Id resolver** action](https://docs-external.u4pp.com/extensions-kit/built-in-actions/u4id-resolver/) to retrieve it as in the example shown in the image. | Yes |
| _Question_ | Enter the question you want to send. | Yes |
| _Expected answer data type_ | Select the data type from the dropdown. Ava will make sure that the answer conforms to the expected data type. | Yes |
| _Confirmation message_ | Enter a message that will be part of the conversation in Ava. | No |

![Image 4: Ava question](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/avaquestion-input.png)

## Action output

| **Property** | **Description** |
| --- | --- |
| _Answer_ | The response the user provides in Ava chatbot. |
| _Status_ | The final status of the question in Ava: cancelled, completed or expired (timed out). |

![Image 5: Ava question output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/avaquestion-output.png)
