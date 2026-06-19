The **Data grid** component is used to present your data in table format. It supports:

-   Viewing and filtering presented data.
-   Editing data.
-   Adding and deleting rows.
-   Importing and exporting data.

## Example

You can use the **Data grid** component to create an app that shows a list of your customers. In this example:

-   Users can edit the Country code column.
-   Users can filter data.
-   Users can add rows.
-   Users can import or export the data in Excel.

![Data grid component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/data-grid-ripple.png)

> Note: The **Data grid** component follows the [WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Data grid** properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Grid data_|Enter an array with the grid data (you can use templating) or enter the resource that returns the data for the grid. You can select the **Plus (+)** button to display a drop-down with the available arrays or enter the text using Liquid JS. For example `{{res1}}`
Note: You must edit the _Resource_ in the **Resources** tab.|No|
|_Allow editing_|Select the checkbox to make the grid editable. If selected, the end-user app presents:
A **Plus (+)** button to add rows.
A **Delete** button to deleted the rows.
A **Three dots** menu with the **Reset** action.|No|
|_Disable adding rows_|Select the checkbox to disable the **Plus (+)** button. The user of the app will not be able to add rows.|No|
|_Disable deleting rows_|Select the checkbox to disable the **Delete** button. The user of the app will not be able to delete rows.|No|
|_Selection mode_|Select whether to allow single row or multiple row selection from the drop-down.|No|
|_Enable data import_|Select the checkbox to enable data to be imported into the grid from an Excel file. If selected, the **Import** option is added to the end-user app's **Three dots** menu.|No|
|_Skip first header row_|Select the checkbox and when importing data, the first row of the Excel file is treated as the header and not imported.|No|
|_Enable data export_|Select the checkbox to enable data to be exported from the grid as an Excel file. If selected, the **Export** option is added to the end-user app's **Three dots** menu.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|Property|Description|Required|
|---|---|---|
|Pagination|Select the checkbox to enable pagination and show it in a row at the bottom of the grid.|No|
|Rows per view|Choose the number of rows displayed without having to scroll. Only visible when _Pagination_ is not selected.|No|
|Items per page|Choose the number of items displayed per page. Only visible when _Pagination_ is selected.|No|
|Show filter row|Select the checkbox to activate the filter functionality. A filter row is displayed to allow filtering on the various columns.|No|

### Columns properties

The following table describes the columns properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Column ID_|Enter a unique name for the column. This unique identifier is used to reference the component in Liquid JS. Liquid JS arrays start at `0`.|Yes|
|_Title_|Enter the column title.|No|
|_Dynamic calculation_|Select to display the result of Liquid JS operations between columns. Only non-dynamic columns can be referenced.|No|
|_Formula_|Enter the Liquid JS operation. You can use the **Templating** drop-down to select the values for the formula. See [**Liquid support**](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#data-grid-component) for examples on how to configure a **Dynamic** column. Only visible when **Dynamic calculation** checkbox is selected.|No|
|_Column data_|Choose the _Table data_ field that you want to display data from. You can choose an option from the **Plus (+)** button or write the text using Liquid JS in the text editor. For example `{{name}}`|No|
|_Default value_|Enter the value that is displayed in this column when you add a new row. You can either create it from other columns in the table (using Liquid JS syntax) or enter a fixed value.|No|
|_Width_|Choose the width of the column.|No|
|_Datatype_|Choose what kind of data that is displayed in the column.|Yes|
|_Decimals_|Only available when _Number datatype_ is selected. Enter how many decimals are allowed.|
|_Options_|Only available when _Value list datatype_ is selected. Enter the resource to return the data for the select, these will be the drop-down options. You can choose the array from the drop-down displayed when selecting the Plus (+) button (only arrays will be available) or type it in using Liquid JS. For example `{{res2.countries}}`.|Yes|
|_Value field_|Only available when _Value list datatype_ is selected. This is the real data associated with the options. Import a value using Liquid JS from the previously imported array in Options, for example, `{{code}}`.|Yes|
|_Display field_|Only available when _Value list datatype_ is selected. This is what is visible to the user. Import a value using Liquid JS from the previously imported array in Options, for example, `{{name}}`.|Yes|
|_Hidden_|Select the checkbox to hide the column. You can set rules to hide the column using Liquid JS. See [add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.|No|
|_Read only_|Select the checkbox to set the column to read only. You can set rules to allow editing using Liquid JS. The checkbox is only available when _Allow editing_ checkbox is selected in the **Main** menu. See [add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.|No|
|_Disable filter_|Select the checkbox to disable filtering in this column.|No|
|_Disable move_|Select the checkbox to lock the column in place.|No|
|_Disable resize_|Select the checkbox to set a fixed width for the column and disable resizing.|No|
|_Disable sort_|Select the checkbox to prevent sorting within this column.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.
