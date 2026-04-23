# Sensitive flows

A sensitive flow is a type of flow which information might be considered confidential or sensitive. For that reason, the input and output data generated during the flow execution is not stored internally on Extension Kit.

A flow can be marked as sensitive during its creation or even if it already exists. On the other hand, an existing sensitive flow can be modified to be non sensitive, from that moment, it will behave as a normal flow. The sensitive configuration can be updated on the **Overview** section of a flow:

![Image 4: Sensitive flow - Configuration](https://docs-external.u4pp.com/extensions-kit/images/portal/sensitive-flow-configuration.png)

> NOTE: When an existing flow is marked as sensitive the behavior will be applied to the next flow execution.

[Marketplace flows](https://docs-external.u4pp.com/extensions-kit/guides/portal/marketplace-flows/) are always considered sensitive flows, so it is not possible to modify the configuration.

Because this configuration can be changed between flow executions, each Flow History summary line is marked with a special tag when it is sensitive.

![Image 5: Sensitive flow - Summary line](https://docs-external.u4pp.com/extensions-kit/images/portal/sensitive-flow-summary-line.png)
