# Service limits

## General flow limits

The following table shows the limits that apply to the overall flow configuration and execution.

| Name | Limit | Comments |
| :--- | :--- | :--- |
| Flow state maximum size | 80 Megabits | Flow state: sum of all the inputs and outputs of a flow. |
| Maximum number of actions per flow | 8 000 actions in five minutes per flow | If the limit is exceeded, the flow is disabled but it can be manually enabled after one minute. Note: This does not apply to Marketplace flows. |

## Iteration and loop limits

The following table shows the limits that apply to loops and iterations within flows.

| Name | Limit | Comments |
| :--- | :--- | :--- |
| Maximum number of iterations using the **For each** action | 1000 | The limit of the number of iterations may vary according to the size of each iteration. |
| Maximum number of iterations in a liquid loop | 10 000 | This count includes all iterations, including nested loops. The flow will be stopped if the limit is reached. |

## Data size limits

The following table shows the limits that apply to data storage and input sizes.

| Name | Limit | Comments |
| :--- | :--- | :--- |
| Parameters maximum number of characters | 10 000 characters | Trying to input or reference data bigger than these limits will take only the first 10 000 characters. |
| Variables maximum size | 25 KB | Trying to input or reference data bigger than these limits will take only the first 25 Kb. |
| Webhook maximum input size | 25 Megabytes | If the input is bigger, 413 error (Request Entity Too Large) is returned. |

## Execution and timeout limits

The following table shows the limits that apply to action execution duration and timeouts.

| Name | Limit | Comments |
| :--- | :--- | :--- |
| Action maximum duration | 10 minutes / 5 retries | The maximum run time for an action is determined by the setup of two different variables on its Azure function: Timeout and maximum number of retries. |
| HTTP request maximum timeout | 100 seconds |  |

> Note: The **Unit4 Ava** action is excluded since it is intended to manage asynchronous responses from an external service that needs it to hibernate until it is called again to continue the execution.

## Communication limits

The following table shows the limits that apply to email and external communication actions.

| Name | Limit | Comments |
| :--- | :--- | :--- |
| Email sender action limit per month | 2 500 000 emails | The limit is shared within all the tenants of your region |

## Action-specific limits

The following sections show the limits that apply to specific actions and their unique constraints.

### Run code action

The following table shows the limits that apply to the **Run code** action:

| Limit | Value | Description |
| --- | --- | --- |
| Maximum allowed depth of recursion | 100 | This means that recursive scripts will only be allowed to execute 100 levels of depth. |
| Script execution | 600s (10 min) | Otherwise, the execution will fail with a timed-out result. |
| Maximum size allowed for arrays | 10M elements |  |
| Maximum number of statements | 500M | This includes variable declarations, conditional blocks, loops, function calls and such. |
