## Configure an app to use ERPx/CR API resources (U4Components)

> ⚠️ Warning: This tutorial was created with U4Components. You can follow it with App Studio Ripple, however the layout, component names and properties may differ.

This example uses the **ERPx API** resource. To use the **ERP CR** resource you can also follow the tutorial though the endpoints to select will differ accordingly.

This example shows how to configure an app where the user can:

-   Select a supplier from a dropdown.
-   See the ID of the selected supplier.
-   See, edit and update the name and country of the selected supplier.

![Suppliers app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutorialERXresource.png)

All the data is retrieved and updated using the **ERPx API** resource.

> ⚠️ Warning: For the **ERPx API** resource to work properly in the end-user app, the user must have access to the ERPx Public APIs and to the specific endpoints you have used. Go to the **Public API access (XAG005)** window to check your user's configuration.

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
    -   Four rows inside the container
    -   One column in the first and last row
    -   Two columns in the second and third row
        
        > Note: Use the **Layout view** switch and the **Layer** panel to help you.
        

![App in canvas](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/layoutsuppliersapp.png)

-   Drag and drop the following components inside the **Layout** components, as shown in the image:
    
    -   One **Text** component
    -   One **Filter select** component
    -   Two **Text input** components
    -   One **Select** component
    -   One **Button** component
    
    ![App in canvas with components](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/componentssupplierapp.png)
    

## Configure the Text component

In this example we configure the component as follows:

-   Select the **Text** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Text_: Enter the text: Suppliers.
    -   Open the **Styles** menu and configure:
        -   _Format_: Select _Title_ from the dropdown.

Go to the **Resources** tab next to canvas:

After setting our UI, let's configure our first resource to retrieve supplier data:

## Create the _Suppliers GET_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Suppliers- GET'
4.  Select **ERPx API** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section: - _API endpoint_: Open the dropdown and select `objects/suppliers` - _Method_: Open the dropdown and select _GET_.
        
    2.  **Parameters** section: - _orderBy_: Enter the text: supplierName.
        

Go to the **Logic flow** tab next to resources:

To trigger the resource when the app is launched, follow these steps:

1.  Drag the **On launch** event to the viewport.
2.  Drag the **HTTP Request** action to the viewport and connect it to the **On launch** event.
3.  Select **HTTP Request** action in the viewport to see the properties panel to the right.
4.  Open the **HTTP** dropdown.
5.  Select the resource, for this example _Suppliers GET(res1)_.
    
    ![Logic flow](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/suppliersgetresource.png)
    

Go back to the **Canvas** tab:

Now, we need to continue configuring some of our components.

## Configure the Filter select component

In this example we configure the component as follows:

-   Select the **Filter select** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        
        -   _Component ID_: Select the **Edit** button and enter 'supplierfilter' and select the **Save** button.
        -   _Label_: Enter the text: Select a supplier.
        -   _Options_: Enter `{{res1}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the [_Supplier GET_ resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#create-the-suppliers-get-resource).
        
        ![Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutfilterselectres.png)
        
        -   _Value field_: Enter `{{supplierId}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _supplierId_ property.
        -   _Display field_: Enter `{{supplierName}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _supplierName_ property.

Go back to the **Resources** tab:

Let's create our second and third resources.

## Create the _Suppliers GET-ID_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Suppliers GET-ID'
4.  Select **ERPx API** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section: - _API endpoint_: Open the dropdown and select `suppliers/{supplierId}` - _Method_: Open the dropdown and select _GET_.
        
    2.  **Parameters** section: - _supplierId_: Enter `{{supplierfilter.value}}` or use the **Plus (+)** button to display the **Templating** dropdown to navigate to the value of the [**supplierfilter** component](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#configure-the-filter-select-component) like this: **Plus(+) button --> fields --> supplierfilter --> value.**
        
        ![Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/superfiltervalue.png)
        

> Note: **ERPx API** resources that use the _GET_ method and have dependencies (Liquid JS in URL, parameters, headers) do not need to be configured in the **Logic map** or the **Logic flow**. The call is made through use of the component that is referenced.

## Create the _Countries_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Countries'
4.  Select **ERPx API** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section: - _API endpoint_: Open the dropdown and select `objects/countries` - _Method_: Open the dropdown and select _GET_.
        
    2.  **Parameters** section: - _filter_: Enter the text: language eq 'EN'. - _orderBy_: Enter the text: countryName.
        

Go to the **Logic flow** tab next to resources:

To trigger the resource when the app is launched, follow these steps:

1.  Drag the **HTTP Request** action to the viewport and connect it to the **On launch** event.
2.  Select **HTTP Request** action in the viewport to see the properties panel to the right.
3.  Open the **HTTP** dropdown.
4.  Select the resource, for this example _Countries (res3)_.
    
    ![Logic flow](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/countriesresource.png)
    

Go back to the **Canvas** tab:

Let's continue with some more components.

## Configure the Text input component

In this example we configure the components as follows:

### Configure the Supplier ID text input

-   Select the first **Text input** component to use for the supplier ID in the canvas and go to the **Properties** panel.
    
    -   Open the **Main** menu and configure:
        
        -   _Component ID_: Select the **Edit** button and enter 'supplierId' and select the **Save** button.
        -   _Label_: Enter the text: Supplier Id.
        -   _Default value_: Enter `{{supplierfilter.value}}` or use or use the **Plus (+)** button to display the **Templating** dropdown, open the _fields_ menu, look for the **supplierfilter** component, open it and select _value_.
        
        ![Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/supplieridtextinput.png)
        
        > Note: We have configured the value of this component to be the _supplier Id_ when configuring the [**Filter select** component](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#configure-the-filter-select-component).
        
    -   Open the **Interactions** menu and configure:
        
        -   Select the _Read only_ checkbox.

### Configure the Supplier name text input

-   Select the second **Text input** component to use for the supplier name in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Component ID_: Select the **Edit** button and enter 'suppliername' and select the **Save** button.
        -   _Label_: Enter the text: Supplier name.
        -   _Default value_: Enter `{{res2.supplierName}}` or use the **Plus (+)** button to display the **Templating** dropdown to open the [_Supplier GET-ID_ resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#create-the-suppliers-get-id-resource) and select the _supplierName_ property.

## Configure the Select component

In this example we configure the components as follows:

-   Select the **Select** component in the canvas and go to the **Properties** panel.
    -   Open the **Main** menu and configure:
        -   _Component ID_: Select the **Edit** button and enter 'countries' and select the **Save** button.
        -   _Label_: Enter the text: Country.
        -   _Options_: Enter `{{res3}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the [_Countries_ resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#create-the-countries-resource).
        -   _Value field_: Enter `{{countryCode}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _countryCode_ property.
        -   _Display field_: Enter `{{countryName}}` or use the **Plus (+)** button to display the **Templating** dropdown to select the _countryName_ property.
        -   _Default value_: Enter `{{res2.countryCode}}` or use the **Plus (+)** button to display the **Templating** dropdown to find the [_Supplier GET-ID_ resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#create-the-suppliers-get-id-resource) and select the _countryCode_ property.

Go back to the **Resources** tab:

Now, we will configure the last resource for our app.

## Create the _Update supplier_ resource

To configure the resource, follow these steps:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Update suppliers'.
4.  Select **ERPx API** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section:
        
        -   _API endpoint_: Open the dropdown and select `suppliers/{suppliersId}`
        -   _Method_: Open the dropdown and select _PATCH_.
    2.  **Parameters** section:
        
        -   _supplierId_: Enter `{{res2.supplierId}}` or use the **Plus (+)** button to display the **Templating** dropdown to open the _Suppliers GET ID_ resource and to navigate to the _supplierId_ property.
    3.  **Content definition** section:
        
        -   _Body Data Type_: Select _JSON_ from dropdown.
        -   _Content_: Enter the JSON. For this example, you can copy and paste the JSON below.
            
            > Note: You can enter _value_ property with Liquid JS or using the **Plus (+)** button to display the **Templating** dropdown to navigate to the component's value through the _fields_ menu.
            
        
        `[{"op": "replace","path": "/supplierName", "value": "{suppliername.value}" }, { "op": "replace","path": "/countryCode","value": "{countries.value}" }]`
        

> Note: This resource is triggered in the **Logic map** in the **Button** component. See [Button component](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#configure-the-button-component).

In the following image you can see the **Resource** tab with all the ERPx resources.

![Resources](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tutorialsresources.png)

Go back to the **Canvas** tab:

Let's configure our last component.

## Configure the Button component

In this example we configure the components as follows:

-   Select the **Button** component in the canvas and go to the **Properties** panel.
    
    -   Open the **Main** menu and configure:
        
        -   _Text_: Enter the text: Update.
    -   Open the **Styles** menu and configure:
        
        -   _Icon_: Select the _Save_ icon from the dropdown.
    -   Open the **Logic map** tab in the bottom-right corner and configure:
        
        -   Drag the **On click** event to the viewport.
        -   Drag the **HTTP request** action to the viewport and connect it to the **On click** event.
        -   Select **HTTP request** action in the viewport to see the properties panel to the right.
        -   Open the **HTTP** dropdown.
        -   Select the resource, for this example, [_Update supplier (res4)_](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-ERPx-resource/#create-the-update-supplier-resource).
        -   Drag the **Modal** action to the viewport and connect it to the **HTTP request** _Green check_ handle.
            -   Configure all the required properties for the **Modal** action. For this example: A one button success type modal.
        -   Drag the **Toast** action to the viewport and connect it to de **HTTP request** _Red cross_ handle.
            -   Configure all the required properties for the **Toast** action. For this example: An error type modal.
        
        ![Logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/logicmapsuppliers.png)
        

You can see the final result in the following image:

![App in canvas](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/suppliersappcanvas.png)

> Note: See [Components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/components-overview/) and [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

Finally, after configuring the components and the resources, select the **Save draft** button and preview you app.
