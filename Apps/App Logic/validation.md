Validation in App Studio ensures that users provide correct and complete information before submitting data. By defining validation rules on input components, you can prevent errors, improve data quality, and provide clear feedback to users about what's expected.

To set up validation rules, use:

-   [**Validation** menu](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#validation-menu): Define validation rules directly in components using their validation properties.
-   [**Triggering validation**](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#triggering-validation): Use the **Field validation** action to check all validation rules before sending data.

The **Validation** menu is available in some components to allow you to define validation rules in your app.

![Validation properties](https://docs-external.u4pp.com/extensions-kit/app-studio/images/validation-ripple.png)

The following table shows the validation properties for each component.

|Properties|Components|
|---|---|
|[_Optional field_](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#optional-field)|Drawing area, Dropdown, Combobox, File uploader, Radio, Text area and Text input|
|[_Choose common pattern_](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#choose-common-pattern)|Text input
Note: Only for _Text, Phone number, Email, URL, Password_ and _Search_ _Types_.|
|[_Additional validations_](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#additional-validations)|File uploader, Radio, Text area and Text input|

### Optional field

By default, all components are required in all instances. You can use [Liquid templating](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/) to add a rule to specify when the component should be required. If the user fails to fill in the component, a default message is displayed. You can also, enter your own message.

You can turn on the _Optional field_ property to make the component optional.

The following table describes the properties available to add rules for required fields:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Add rule_|Add rules in Liquid JS to specify when the component is required. If no rules are set, the component will be required in all instances.|No|
|_Message_|Enter a message to be displayed if the user does not fill in the input. A default message is otherwise shown.|No|

### Choose common pattern

Select a validation pattern from the _Choose common pattern_ drop-down menu to define the expected input data type for your field. See [Available common patterns](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#available-common-patterns) for more details.

If the user input does not match the selected pattern, the component automatically displays a default validation message.

> Note: if overlapping validation conditions occur, then the hierarchy is: **Required** > **Common pattern** > **Error** > **Warning** > **Informative**.

**Available common patterns**

The following table lists the available common pattern options and the defined regular expressions for them:

|Pattern|Description|Validation regular expression|
|---|---|---|
|None|Does not match any string and is used when no pattern is required.|`None`|
|Number (negative and decimals)|Matches any valid number, including negative numbers and decimals.|`'^-?\d+((\.|
|Digit|Matches any positive integer, that is, numbers without decimals or negatives.|`'^\d+$'`|
|Word (only alphanumeric)|Matches any word that contains only alphanumeric characters, that is, letters and numbers.|`'^[A-Za-z0-9ñÑçÇáéíóúÁÉÍÓÚüÜ]+$'`|
|Word (special characters allowed)|Matches any word that contains alphanumeric characters as well as certain special characters such as periods, commas, and semicolons.|`"^[A-Za-z0-9ñÑçÇáéíóúÁÉÍÓÚüÜ\.,;:!?()_\x22'%\-]+$"`|
|Text|Matches any string that contains alphanumeric characters, spaces and certain special characters such as periods, commas, and semicolons.|`"^[A-Za-z0-9ñÑçÇáéíóúÁÉÍÓÚüÜ\.,;:!?()\x22'%\-\s]+$"`|
|Letter|Matches any single letter (uppercase or lowercase) as well as certain letters in Spanish, such as ñ, á, é, í, ó, and ú.
Note: if you need to have a pattern rule for other characters, for example Nordic characters, then you can do this by creating an additional validation pattern using Liquid JS templating in the _Error rule_ property.|`'^[A-Za-zñÑçÇáéíóúÁÉÍÓÚüÜ]$'`|
|Email|Matches any valid email address.|`'^[^\s@]+@([\^\s@.,]+\.)+[^\s@.,]{2,}$'`|
|URL|Matches any valid URL, including protocols such as http, https, ftp, mailto, etc.|`'^((?:http|
|Date: mm/dd/yyyy|Matches any date in the format MM/DD/YYYY (month/day/year) where MM is the month in two digits (01-12), DD is the day in two digits (01-31), and YYYY is the year in four digits (for example 2022).|`'^(0[1-9]|
|Date: dd/mm/yyyy|Matches dates in the format DD/MM/YYYY, where DD is the day (01-31), MM is the month (01-12), and YYYY is the year (for example 2022). .|`'^(0[1-9]|
|Time 12H: HH:MM AM/PM|Matches times in 12-hour format, with an optional space and either "AM" or "PM" at the end. The pattern matches if the hour value is either "00", "12", or a value between 1-11 (with or without a leading zero), and the minute value is between 00-59. The optional space and AM/PM values are matched using regular expression alternation.|`'^((00|
|Time 24H: HH:MM:SS|Matches times in 24-hour format, with hours in the range 00-23 and minutes and seconds in the range 00-59. The pattern uses grouping and repetition to ensure that the minute and second values each consist of two digits.|`'^(2[0-3]|
|Strong password|Matches strong passwords that meet the following criteria:
\- is at least 8 characters long.
\- contains at least one uppercase letter.
\- contains at least one lowercase letter.
\- contains at least one digit.
\- contains at least one special character from the given set.
The pattern uses positive lookahead assertions to check for the presence of each required character type, and a character class to match any of the allowed special characters.|`"\^(?=._[A-Z])(?=._[a-z])(?=._\d)(?=._[!?@#$%^&_()\-+\\\/.,:;\x22'{ }\[\]<>~])[A-Za-z0-9ñÑçÇáéíóúÁÉÍÓÚüÜ!?@#$%^&_()-+\\\/.,:;\x22'{ }\[\]<>~]{8,}$"`|
|IPv4|Matches valid IPv4 addresses that consist of four decimal numbers separated by periods. Each decimal number must be in the range 0-255, with the exception that leading zeroes are not allowed (for example, 01). The pattern uses alternation to match any of the four possible formats for a decimal number, that is, a single digit, two digits starting with 1, two digits starting with 2-9, or three digits starting with 1.|`'^(?:25[0-5]|
|IPv6|Matches valid IPv6 addresses that consist of up to eight groups of four hexadecimal digits separated by colons. The pattern uses grouping and repetition to match each group, with an optional space between groups. The pattern allows for leading zeroes and both uppercase and lowercase hexadecimal digits.|`'^(?:[A-Fa-f0-9]){0,4}(?: ?:? ?(?:[A-Fa-f0-9]){0,4}){0,7}$'`|

> Note: Only for _Text, Phone number, Email, URL, Password_ and _Search_ _Types_.

#### Example: Validating a numeric input with Digit pattern

___

When using the **Text input** component with the _Type_ property set to `Number`, the HTML5 `<input type="number">` allows exponential notation (for example, `2e4`), negative numbers, and floating-point numbers according to browser implementation. To restrict input to digits only and validate against characters like exponential notation:

1.  In the **Styles** menu, set _Type_ to `Text`.
2.  In the **Validation** menu, select _Choose common pattern_ as `Digit`.
3.  If the user enters invalid input such as `2e4`, an error message is displayed.
4.  Use the **Field validation** action in the **Logic map** to prevent sending requests when the input is invalid. See [Field validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-validation) for more details.

> Note: Only the properties relevant to the example are explained. See the [**Text input** component](https://docs-external.u4pp.com/extensions-kit/app-studio/components/text-input-ripple/) for more details.

### Additional Validations

For components that allow additional validations, you can add rules using [Liquid templating](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/).

|**Property**|**Description**|**Required**|
|---|---|---|
|_Additional validations_|Select any or all checkboxes to add validations.|No|
|_Error_|Select the checkbox to add a red error style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the error validation is shown.|Yes|
|_Error message_|Enter a message to be displayed if the user fills in the input incorrectly.|Yes|
|_Warning_|Select the checkbox to add an orange warning style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the warning validation is shown.|Yes|
|_Warning message_|Enter a message to give the user advice on how to better fill in the input.|Yes|
|_Positive_|Select the checkbox to add a green positive style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the positive validation is shown.|Yes|
|_Positive message_|Enter a message to tell the user that the input has been correctly filled in.|Yes|

> Note: if overlapping validation conditions occur, then the hierarchy is: **Required** > **Common pattern** > **Error** > **Warning** > **Informative**.

## Triggering validation

To perform validation before sending data, you must use the **Field validation** action than can be configured in a **Button** component.

When the **Field validation** action is executed, it checks all validation rules defined on the selected input components (required fields, common patterns and additional validations). If any validation fails, the corresponding error messages are displayed and the data submission is prevented.

For more information on configuring the Field validation action, see [Field validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-validation).

### Example: Validating date input before sending data

To validate a **Text input** component with a date format before sending data using the **Field validation** action, follow these steps:

**Step 1: Configure the Text input component**

1.  Add a **Text input** component to your **Canvas**.
2.  In the **Main** menu:
3.  Set _Component ID_ to `dateInput` (or any unique identifier).
4.  Set _Label_ to `Enter date`.
5.  Set _Placeholder_ to `MM/DD/YYYY`.
6.  In the **Styles** menu:
7.  Set _Type_ to `Text`.
8.  In the **Validation** menu:
9.  Keep the _Optional field_ switch turned off to make the field required.
10.  From the _Choose common pattern_ drop-down, select `Date: mm/dd/yyyy`.
11.  Optionally, add a custom _Message_ such as "Please enter a valid date in MM/DD/YYYY format".

**Step 2: Add a Button component**

1.  Add a **Button** component to your **Canvas**.
2.  In the **Main** menu:
3.  Set _Component ID_ to `submitButton`.
4.  Set _Label_ to `Submit`.

**Step 3: Configure the Field validation action**

1.  Select the **Button** component.
2.  In the bottom-right corner, open the **Logic map** tab.
3.  In the **Logic drawer** on the left, locate the **On click** event and the **Field validation** action and drag them to the viewport.
4.  Connect the **On click** event output port to the **Field validation** action input port.
5.  Select the **Field validation** action node to configure its properties in the panel to the right:
6.  In _Description_, optionally enter "Validate date input".
7.  In _Fields_, select the _Component ID_ of the field you want to validate from the drop-down list. For this example, select `dateInput`.

**Step 4: Add the HTTP Request action**

1.  Drag an **HTTP Request** action from the **Actions** section and drop it into the viewport.
2.  Connect the green output port of the **Field validation** action to the **HTTP Request** action input port.
3.  Configure the **HTTP Request** action:
4.  Select your configured HTTP resource that sends the data.
5.  Configure any additional properties as needed.

**Step 5: Optional - Add error handling**

1.  Drag a **Toast** action to the viewport.
2.  Connect the red output port of the **Field validation** action to the **Toast** action input port.
3.  Configure the **Toast** action:
4.  Set _Variant_ to `Negative`.
5.  Set _Title_ to "Validation failed".
6.  Set _Message_ to "Please correct the date format before submitting".

**Result:**

When the user selects the **Submit** button:

-   If the date input is valid (matches the MM/DD/YYYY format), the green output port is triggered and the HTTP request is sent.
-   If the date input is invalid or empty, the red output port is triggered, the error message is displayed on the component, and the HTTP request is not sent.

> Note: Only the properties relevant to the example are explained. See [Field validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-validation) and [HTTP Request](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#http-request) for complete property details.
