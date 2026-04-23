# Optimize flow memory

The optimization of flow memory improves how Extension Kit manages large inputs and outputs. Optimizations will be applied to Liquid templating to improve flow memory consumption.

To activate this feature, turn on the **Optimize Flow Memory** switch in the **Preview features** menu inside the **Overview** section of the flow. It is recommended when the flow uses a large input and reaches the allowed memory limit.

> ⚠️Note: The internal implementation is changed, so there may be breaking changes in how the templating is evaluated, causing the behaviour of the templating to vary compared to having the switch disabled.

![Image 3: Optimize Flow Memory - Configuration](https://docs-external.u4pp.com/extensions-kit/images/portal/optimize-flow-memory-configuration.png)
