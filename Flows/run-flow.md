# Run a flow manually

The **Run** button allows you to manually run your flow in cases where you want to trigger the flow immediately. For example, you may want to run the flow outside the regular triggered flow execution, or without relying on an external tool such as Postman or a Message Hub trigger event, or for testing purposes during flow development.

![Image 7: Run button](https://docs-external.u4pp.com/extensions-kit/images/portal/run-flow-button.png)

The **Run** button is only visible in enabled flows and logged tenants for users with Contributor or Owner roles.

When you click the **Run** button, you are prompted to configure the Run Now Parameters for the flow trigger:

*   Webhook: Body, Headers and Query
*   Message Hub trigger: Properties, Body and Content type
*   Scheduler: No input, just the **Run** button

![Image 8: WebHook run parameters](https://docs-external.u4pp.com/extensions-kit/images/portal/run-flow-webhook.png)![Image 9: MH run parameters](https://docs-external.u4pp.com/extensions-kit/images/portal/run-flow-messagehub.png)![Image 10: Scheduler run parameters](https://docs-external.u4pp.com/extensions-kit/images/portal/run-flow-scheduler.png)

Note that that the authentication configuration of the Webhook is not part of the run-now execution (user-password or certificates).

Once you click the **Run** button, you are prompted to save any changes and the flow is then run with the configured parameters.

## Flow history

The flow history shows when the flow was manually triggered as shown in the example below:

![Image 11: Run flow histroy](https://docs-external.u4pp.com/extensions-kit/images/portal/run-flow-history.png)
