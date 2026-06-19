> ⚠️ Warning: This tutorial was created with U4Components. You can follow it with App Studio Ripple, however the layout, component names and properties may differ.

This example uses the **ERPx API** resource. To use the **ERP CR** resource you can also follow the tutorial though the endpoints to select will differ accordingly.

This example shows how to configure an app where the user can:

-   See the suppliers on a table.
-   See the language of the supplier.
-   Edit a supplier's language selecting a new one from a dropdown.

![Suppliers app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-suppliers.png)

To start:

1.  Select **My Apps** from the Extension Kit portal main menu.
2.  Select the **Create new app** button and name your app.
3.  Select the **Create** button.

![Create an app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/createapp2.png)

## Configure the app layout

> ❗IMPORTANT: The components and resources have dependencies between them. To configure this app, you must go from the **Canvas** tab to the **Resources** tab and the **Logic flow** tab frequently.

![Resources](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-tabs.png)

Go to the **Canvas** tab:

-   Drag and drop the **Layout** components to the canvas. In this example we added the following components in this order:
    
    -   One container
    -   Two rows inside the container
    -   One column in each row

> Note: Use the **Layout view** switch and the **Layer** panel to help you.

![App in canvas](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-canvascomponents.png)

-   Drag and drop the following components inside the **Layout** components as shown in the image:
    
    -   One **Text** component
    -   One **Divider** component
    -   One **Table** component
    
    ![App in canvas with components](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-canvascomponents2.png)
    

## Configure the Text component

In this example we configure the component as follows:

-   Select the **Text** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Text_: Enter the text: Suppliers.
    -   Open the **Styles** menu and configure:
        -   _Format_: Select _Title_ from the dropdown.

> Note: The **Divider** component requires no configuration.

Go to the **Resources** tab next to canvas:

After setting our UI, let's configure our resources to retrieve data:

## Create the _Suppliers_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Suppliers'.
4.  Select **ERPx API** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section: - _API endpoint_: Open the dropdown and select `objects/suppliers` - _Method_: Open the dropdown and select _GET_.
        
    2.  **Parameters** section: - _orderBy_: Enter the text: supplierName.
        

Go to the **Logic flow** tab next to resources:

To trigger the resource when the app is launched, follow these steps:

1.  Drag the **On launch** event to the viewport.
2.  Drag the **HTTP Request** action to the viewport and connect it to the **On launch** event.
3.  Select **HTTP Request** action in the viewport to see the properties panel to the right.
4.  Open the **HTTP** dropdown.
5.  Select the resource, for this example _Suppliers (res1)_.
    
    ![Logic flow](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-res1.png)
    

Go back to the **Resources** tab:

## Create the _Languages_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Languages'.
4.  Select **ERPx API** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section:
        
        -   _API endpoint_: Open the dropdown and select `objects/languages`
        -   _Method_: Open the dropdown and select _GET_.

Go to the **Logic flow** tab next to resources:

To trigger the resource when the app is launched, follow these steps:

1.  Drag the **HTTP Request** action to the viewport and connect it to the **On launch** event.
2.  Select **HTTP Request** action in the viewport to see the properties panel to the right.
3.  Open the **HTTP** dropdown.
4.  Select the resource, for this example _Languages (res2)_.
    
    ![Logic flow](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-res2.png)
    

In the following image you can see the **Resource** tab with all the resources configured.

![Resources](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-resources.png)

Go back to the **Canvas** tab:

Now, we need to finish configuring our components.

## Configure the Table component

In this example we configure the component as follows:

-   Select the **Table** component in the canvas and go to the **Properties** panel.
    
    -   Open the **Main** menu and configure:
        
        -   _Table data_: Enter `{{res1}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the [_Suppliers_ resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-configure-table-value-list/#create-the-suppliers-resource).
        
        ![Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut3-templatingdropdown.png)
        
        -   _Allow editing_: Select the checkbox to allow editing in the table. _Value list data type_ will not work if you do not select this checkbox.
    -   Open the **Columns** menu and configure:
        
        -   Open **Column 1** and configure:
            
            -   _Title_: Enter the text: Suppliers.
            -   _Column data_: Enter `{{supplierName}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _supplierName_ property.
            -   _Width_: Open the dropdown and select _Stretch_.
            -   _Read only_: Select the checkbox to avoid editing in the column.
        -   Open **Column 2** and configure:
            
            -   _Title_: Enter the text: Languages.
            -   _Column data_: Enter `{{languageCode}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _languageCode_ property.
            -   _Width_: Open the dropdown and select _Stretch_.
            -   _Datatype_: Open the dropdown and select _Value list_.
            -   _Options_: Enter `{{res2}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the [_Languages_ resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-configure-table-value-list/#create-the-languages-resource).
            -   _Value field_: Enter `{{language}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _language_ property.
            -   _Display field_: Enter `{{description}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _description_ property.
        -   Open **Column 3**, scroll down and select the **Delete** button.
            

> Note: See [**Table** component](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/components/table.md) for more details.

You can see the final result in the following image:

![App in canvas](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg//tut3-appincanvas.png)

> Note: See [Components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/components-overview/) and [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

Finally, after configuring the components and the resources, select the **Save draft** button and preview your app.

-   For how to add a button to update the supplier with the user's edits see [Configure ERPx API resources](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-configure-table-value-list/tutorial-ERPx-resource.md#configure-the-button-component)
