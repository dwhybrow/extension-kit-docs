# Run code

The **Run code** action allows you to execute a JavaScript script. Most of the operations are allowed to perform complex operations and data transformations in a simple way.

> Note: Importing libraries, dealing with files, blobs and proxies, using `constructor`, `fetch` or `eval` and doing HTTP requests is not allowed.

The **Run code** action can also be used for specific cryptography requirements by using tools from the Forge library. For more details, see [Run Code action using Forge cryptography library](https://docs-external.u4pp.com/extensions-kit/built-in-actions/run-code-using-forge/).

## Action input

![Image 6: Run Code input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/runcode-input.png)

The following table describes the fields in the **Run code** action input:

| **Field** | **Description** |  | **Required** |
| --- | --- | --- | --- |
| _Inputs_ | Provide data by using the **Add** button to provide as many _Id_ and _Value_ properties as needed. Use the **Minus icon** button to delete added pairs. |  | No |
|  | _ID_ | Enter a name for the variable. | Yes |
|  | _Value_ | Enter or select from the **Suggestions** drop-down a value for the variable. You can use Liquid. | Yes |
| _Code_ | Enter the JavaScript script you want to run. |  | Yes |

> Note: _Inputs_ are declared as global variables and they can be overridden in the code.

### Test action

To test the action without triggering the complete flow, follow these steps:

*   Select the **Test action** button to open the **Test action** dialog. If you have added any _Inputs_, the _Id_ and _Value_ pairs will appear here.

![Image 7: Run Code test action input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/testaction-input.png)

*   Select the **Test** button to execute the script and see the output.

![Image 8: Run Code test action output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/testaction-output.png)

## Action output

![Image 9: Run Code output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/runcode-output.png)

The following table describes the properties in the **Run code** action output:

| **Property** | **Description** |
| --- | --- |
| _Logs_ | Shows any logged elements in the code. |
| _DurationInMs_ | Shows how many milliseconds the code took to execute. |
| _MemoryConsumedMb_ | Shows the memory consumed. |
| _Result_ | Shows the returned value. |

## Action limits

See [Service limits](https://docs-external.u4pp.com/extensions-kit/architecture/service-limits/#run-code-action) for details about the limits that apply to the **Run code** action.
