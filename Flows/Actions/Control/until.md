# Until

## Description

The **Until** action allows a Flow to iterate through a list of actions. The input for the Until action is:

*   A number with the maximum iterations allowed. This quantity has an internal restriction up to 1000 iterations. If this field is not set, the default value will be 1000. 
*   A stop condition. A set of filters that determines if the until action should continue to run. A detailed guide about the filters can be found [here](https://docs-external.u4pp.com/guides/portal/filters-and-conditions/).

Once the Until action is set in the flow, you can add internal actions by clicking on the plus icon. Actions can be sorted using drag & drop functionality.

![Image 4: Until Flow Designer](https://docs-external.u4pp.com/images/built-in-actions/until/until-flow-designer.png)

## Internal references

Internal actions are those which are part of the Until action and they are executed sequentially. These actions have access to reference output results from other internal actions.

![Image 5: Until Flow Designer](https://docs-external.u4pp.com/images/built-in-actions/until/until-output.png)

## Output

No output is provided.

### Nesting

The naming convention for nested **Until** actions is `substepX_X`, where the second `X` represents the nesting level.

The only exception to this naming convention is the first nesting level, where the name used continues to be `substepX` to avoid breaking changes.

For example:

*   `substep1` represents the substep 1 of the nesting level number 1.
*   `substep1_2` represents the substep 1 of the nesting level number 2.
*   `substep3_4` represents the substep 3 of the nesting level number 4.

## Limitations

*   It is possible to nest **up to 5** loop actions (ForEach or Until actions) within each other. However, there are no limitations about the maximum number of loop actions in a Flow.
*   It is not possible to reference an internal action output in actions outside the Until action.
*   Currently there is no possibility to pick data from the last iteration of Until action in templating help. However it is possible reference the last iteration results using `substepX.Y`, being `substepX` the nesting level and `Y` the property that we want to reference.
