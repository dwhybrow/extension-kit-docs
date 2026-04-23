# Flow overview

When you log in the Extension Kit portal, you land in **My flows** flow overview. It contains the following elements:

1.   Main toolbar: [Basic search](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-overview/#basic-search) and [Multi-criteria flow filter](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-overview/#multi-criteria-flow-filter).
2.   Flows list: [Sort by](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-overview/#sort-by) and [flow cards](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-overview/#flow-card).
3.   Bottom toolbar: [New flow](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-overview/#new-flow) and [import](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-overview/#import). 

![Image 4: Flow overview](https://docs-external.u4pp.com/extensions-kit/images/portal/flow-overview.png)

## 1. Main toolbar

### Basic search

Select the **Lens icon** button and type in your search.

### Multi-criteria flow filter

Select the **Filter icon** button to open the **Multi-criteria flow filter** dialog. You have the following menus:

**Flow**

Select the **Chevron** button to display the following filtering fields:

| Field | Description |
| --- | --- |
| Flow name | Enter as many key words as you need and press ENTER on your keyboard to add more criteria. Select the **All**, **Any** or **None** radio buttons to refine the search. |
| Tenant | Enter or select the tenant to filter the flows. Turn on the **Not** switch to exclude that criteria from the results. |
| Flow id | Enter the flow id you are searching for. Turn on the **Not** switch to exclude that criteria from the results. |
| Flow status | Select the flow status. |
| Trigger type | Select the **Trigger** type to filter the flows. Turn on the **Not** switch to exclude that criteria from the results. |

**Tags**

Select the **Chevron** button to filter using tags:

| Field | Description |
| --- | --- |
| Tags | Enter a tag and press ENTER on your keyboard to add more tags. You can add up to ten tags. Select the **All**, **Any** or **None** radio buttons to refine the search. |

**Advanced filters**

Select the **Chevron** button to display the following filtering fields:

| Field | Description |
| --- | --- |
| Last change greater or equal to | Choose a date to look for flows modified in that date or after. |
| Last change less or greater to | Choose a date to look for flows modified in that date or before. |
|  | Select dates in both fields to create a range. If you choose a date in the _Last change less or equal to_ field that happens before the date that you chose in the _Last change greater or equal to_ field, flows within the range will be excluded from the result. For example, 4/07/2025 OR 04/02/2025 returns all flows except the ones between the 04/03/25 – 04/06/25. |
| Created by | Enter the name of the user who created the flow. Turn on the **Not** switch to exclude that criteria from the results. |
| Last changed by | Enter the name of the user who last made changes. Turn on the **Not** switch to exclude that criteria from the results. |
| Product ID | Enter the ID of the product (**Marketplace** flows). Turn on the **Not** switch to exclude that criteria from the results. |
| Developer ID | Enter the ID of the developer (**Marketplace** flows). Turn on the **Not** switch to exclude that criteria from the results. |
| Developer name | Enter the developer's name (**Marketplace** flows). Turn on the **Not** switch to exclude that criteria from the results. |

> Note: When you enter free text, flows containing that text will be shown, not only flows with the exact text.

Once you have introduced all the desired inputs, you can:

*   Select the **Filter** button to see the **Flows list** with your results. 
*   Select the **Clear** button to delete all your input in the modal. 

> Note: You can also see and remove your filter criteria next to the **Sort by** drop-down in the **Flows list**.

## 2. Flows list

The Flow overview shows the **Flow list** which can show one of the following lists:

*   All the non-parked flows of the tenant being administered. 
*   All flows for all tenants if you logged in as the system tenant.
*   All flows that fulfil the search or filter criteria.

### Sort by

Use the **Sort by** drop-down to order the **Flow list** according to name or date. It can be use together with the Basic search and the Multi-criteria flow filter.

### Flow card

You can see each flow card containing the following information.

![Image 5: Flow overview](https://docs-external.u4pp.com/extensions-kit/images/portal/flow-information-2.png)

1.   The **History** bar chart if the flow has been run. Hover over the bars to see more information about the runs.
2.   An icon with the **Trigger** type (except for **Marketplace** flows).
3.   Flow's name.
4.   Marketplace badge with the developer's name (**Marketplace** flows) or custom tags.
5.   Last changes date, tenant (only admin) and tenant id (only admin).
6.   Warnings.
7.   Status of the flow: When active the switch is blue and when disabled the switch and card are grey. You can use the switch to change the status.
8.   The **Three dots** menu, to:
    *   Access the flow history.
    *   Clone the flow.
    *   Export the flow.
    *   Export the flow as an app.
    *   Delete the flow.
> Note: You can also perform these actions in the **Flow editor** of each flow.

## 3. Bottom toolbar

### New flow

Select the **New flow** button on the left corner to open the **Flow editor** and create a new flow. See [create a flow](https://docs-external.u4pp.com/extensions-kit/guides/portal/create-a-flow/) for more details.

### Import

Select the **Import** button on the left corner to import a flow. See [import a flow](https://docs-external.u4pp.com/extensions-kit/guides/portal/import-export-v2/#import-a-flow) for more details.
