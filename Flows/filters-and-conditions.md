# Filters and conditions

Filters and conditions allow users to control the execution of a Flow, based on data from previous actions.

![Image 10: Add filters and conditions](https://docs-external.u4pp.com/images/portal/add-filter-and-conditions.png)

> To add a filter or a condition, simply click Add _filter_ or _condition_ respectively and add the filters/conditions you want.

In the _parameter_ field, existing in both filters and conditions, values from earlier steps in the Flow or tenant specific [parameter values](https://docs-external.u4pp.com/extensions-kit/guides/tenant-parameters/) can be selected.

![Image 11: Add flow, filter editor](https://docs-external.u4pp.com/images/portal/add-flow-filter-editor.png)

## Filters

**Filters stop the entire flow** if the condition defined in them is not matched.

Example: If your Flow is relevant only for female employees, you could add this filter:

![Image 12: Filter example](https://docs-external.u4pp.com/images/portal/add-flow-filter-example.png)

If the value referenced by _{{ step0.Body.gender }}_ is not equal to "Female", then the Flow will stop its execution. You can check messages in _History_ for more detailed information. For example:

![Image 13: Filter output](https://docs-external.u4pp.com/images/portal/add-flow-filter-output.png)

> Note that `step0` represents your trigger and _{{ step0.Body.gender }}_ comes from the data coming through the Flow. This will only make sense if the data from the trigger actually have a property called "gender" inside its body.

## Conditions

**A condition only stops the subsequent action** if the condition is not matched.

Example: If you want to skip an action when a user is not a specific one, you can add a condition similar to:

![Image 14: Condition example](https://docs-external.u4pp.com/images/portal/add-flow-condition-example.png)

When a condition is not met, the _History_ is updated:

![Image 15: Condition output](https://docs-external.u4pp.com/images/portal/add-flow-condition-output.png)

## Grouping with and/or logical operators

Filters and conditions support single level grouping, AND/OR, and NOT logical operators. Two or more adjacent checked ungrouped filter rows can be grouped:

![Image 16: Grouping filters](https://docs-external.u4pp.com/images/portal/flow-and-or-with-grouping.png)

Both individual filter operations and groups can be negated:

![Image 17: filter-negation](https://docs-external.u4pp.com/images/portal/flow-negation.png)

## Additional examples

Check out [this page](https://docs-external.u4pp.com/tutorials/filter-examples/) for more filter examples.

## Operations Cheatsheet

Here you can find a quick reference of the intended usage for the available _operations_.

| Operation | Use |
| --- | --- |
| Contains | **OR** operation. Checks if **any** word from _parameter_ (separated by a semicolon) is present in _Value_ |
| ContainsAll | **AND** operation. Checks if **all** words from _parameter_ (separated by semicolons) are present in _Value_ |
| EqualsTo | Compares for **strict equality**_parameter_ versus _value_ |
| GreaterThanOrEqualTo | Checks if the number for _parameter_ is **larger than** or **equal to** the number in _value_ |
| HasValue | "True" if the _parameter_**contains a value**, "False" if it is null |
| IsEmpty | Returns a _boolean value_ indicating whether a variable has been **initialized** |
| LikeRegEx | Checks if _parameter_ meets a [**RegularExpression**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) (RegEx) pattern in _value_ (e.g., _^female_, matches any _parameter_ that begins with _female_) |
| LowerThanOrEqualTo | Checks if the number for _parameter_ is **lower than** or **equal to** the number in _value_ |
| NotEqualsTo | Returns "True" if the _parameter_**does not have the same value** of _value_; otherwise, it return "False" |
