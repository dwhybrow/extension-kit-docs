# For Each

## Description

The **ForEach** action allows a Flow to iterate through a list of items, applying one or more actions for each item. The input for the ForEach action is a list of items, usually this input is provided by a HTTP request. Once the ForEach action is set in the flow, internal actions can be added clicking on the plus icon. Actions can be sorted using drag & drop functionality.

![Image 5: ForEach Flow Designer](https://docs-external.u4pp.com/images/built-in-actions/for-each-flow-designer.png)

## Internal references

Internal actions are those which are part of the ForEach. They will be applied to each item of the list. Those actions have access to special references:

*   **Current Iteration:** Index of the element within the list starting from one.
*   **Current Item:** Current element of the list. There is no restriction to this reference so it can have references to complex objects or collections (i.e: _{{step2:CurrentItem.complexProperty.ref}}_).
*   **Items:** The complete list of items. Using this reference is possible to access specific items of the list (i.e: _{{step2:Items[2].property}}_).

Moreover, internal actions can reference output results from other internal actions.

![Image 6: ForEach Flow Designer](https://docs-external.u4pp.com/images/built-in-actions/for-each-output.png)

## Output

As the For Each action breaks the normal execution flow, the **History** section has been updated to show a clearer view of the execution. ForEach actions are shown including the action's step itself together with the iteration and the substep sequence in the name (i.e: _Step2.Iteration3.Substep1_). Clicking on the header of a specific step will expand the step's information as usual.

![Image 7: ForEach Flow Designer](https://docs-external.u4pp.com/images/built-in-actions/for-each-flow-history.png)

### Nesting

The new naming convention for nested **ForEach** actions is `substepX_X`, where the second `X` represents the nesting level.

The only exception to this naming convention is the first nesting level, where the name used continues to be `substepX` to avoid breaking changes.

For example:

`substep1` represents the substep 1 of the nesting level number 1. `substep1_2` represents the substep 1 of the nesting level number 2. `substep3_4` represents the substep 3 of the nesting level number 4.

## Limitations

*   It is possible to nest **up to 5** loop actions (ForEach or Until actions) within each other. However, there are no limitations about maximum number of loop actions in a Flow.
*   It is not possible to reference an internal action output in actions outside the ForEach.
*   The input property **must** be in valid JSON Array format or the step will stop with a fail.
*   **Filters** and **Stop Execution** action inside a **For Each** stops the execution of the flow.
