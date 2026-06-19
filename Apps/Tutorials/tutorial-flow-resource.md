> ⚠️ Warning: This tutorial was created with U4Components. You can follow it with App Studio Ripple, however the layout, component names and properties may differ.

This example shows how to configure an app where the user can:

-   Enter an email.
-   Trigger a flow using a button.
-   See the user's ID corresponding to the email (flow's output).

![Button component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/buttontriggerflow.png)

## Configure the flow

To configure a flow that can be triggered from App Studio, follow these steps:

1.  Select My flows entry from the Extension Kit's portal left menu.
2.  Select the **New flow** button.
3.  Select the **App** trigger from the right Trigger menu, and configure:
    -   _Input Schema_: For this example, use the **Generate by JSON** button and enter this JSON: `{"email":""}`. This generates the following schema for the expected input:
        
        ![JSON app trigger](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/JSONapptrigger.png)
4.  Add the first action by selecting the **Action** step from the flow's roadmap and choose the **Unit4id Resolver** action from the right Action menu. Configure:
    -   _Email_: Select the **Plus (+)** button and choose the desired output from the trigger. For this example`{step0.Body.email}`.
5.  Add the second action by selecting the **Add new action** button from the flow's roadmap and choose the **App Result** action from the right menu. Configure:
    -   _Result with_: Display the right dropdown and select _success_.
        
        > Note: You can also use the **Add filter** option from the flow's roadmap to return failure or success depending on the action's output.
        
    -   _Content_: Enter a JSON with the action's output that you want to send to your app. For this example `{"unit4Id":"{step1.unit4Id}"}`.
        
        > Note: You can use the **Plus (+)** button to help you navigate through the different steps and outputs of your flow.
        
6.  Name your flow by using the **Pencil** icon above the flow's roadmap. For this example: 'Get Unit 4 ID'.
7.  Select the **Save flow** button.

![Get id flow](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/getidflow.png)

> Note: You can also create the flow using the **Create flow** button in the **Flow** resource in App Studio.

## Configure the app

To start:

1.  Select **My Apps** from the Extension Kit main menu.
2.  Select the **Create new app** button and name your app.
3.  Select the **Create** button.

![Create an app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/createapp2.png)

### Configure the resource

Go to the **Resources** tab and configure your resource:

![Resources](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/resourcesflow.png)

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the new resource on the left panel.
3.  Select the **Pencil** icon to change the name to 'Get Id'.
4.  Select **Flow** from the **Type** menu on the right and configure:
    
    1.  **Configuration** section:
        
        -   _Flow_: Open the dropdown and select the flow previously created flow. For this example: 'Get Unit 4 ID'.
    2.  **Content definition** section:
        
        -   _Content_: Enter a JSON that defines the information you want to send to the flow. In this case we are sending the user's email so we enter this JSON: `{"email":"{{usersemail.value}}"}`. You can use the **Plus (+)** button to help you navigate through your component's outputs.
        
        ![plus button](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/plusbutton.png)
        
    3.  **Templating schema** section:
        
        -   _Schema_: Select the **Generate by JSON** button and copy the JSON used in the _Content_ property of the **App result** action of the previously configured flow, to obtain the correct schema. For this example:`{"unit4Id":"{{step1.unit4Id}}"}`
    
    ![Generate by JSON](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/generatebyJSON.png)
    

### Configure the components

Go to the **Canvas** tab and design your app:

-   Drag and drop the **Layout** components to the canvas. In this example we added:
    -   One container
    -   Three rows inside the container
    -   One column in each row
        
        > Note: Use the **Layout view** switch and the **Layer** panel to help you.
        

![App in canvas](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/layoutcomponentstutflow.png)

-   Drag and drop the following components:
    -   One **Text input** component
    -   One **Text** component
    -   One **Button** component

![App in canvas with components](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/componentstutflow.png)

#### Configure the Text input component

In this example we configure the component for the user to enter an email, as follows:

-   Select the **Text input** component in the canvas and go to the **Properties** panel.
-   Open the **Main** menu and configure:
    
    -   _Component ID_: Select the **Edit** button and enter 'usersemail', then select the **Save** button.
    -   _Label_: Enter 'Email'.

#### Configure the Text component

In this example we configure the component to display the user's ID, as follows:

-   Select the **Text** component in the canvas and go to the **Properties** panel.
-   Open the **Main** menu and configure:
    
    -   _Text_: Enter 'This is you user ID:' and to show the user ID after the colon, follow these steps:
        
        1.  Select the **Plus (+)** button.
        2.  Select your resource, for this example: _Get Id_, and open the menu.
            
            > ⚠️ Warning: If the resource does not appear in the dropdown, go to [Configure the resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-trigger-a-flow-from-AS/#configure-the-resource) section in this tutorial and come back to this step.
            
        3.  Select the data you want to display. In this example: _unit4Id_.
            
            ![Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/textcomponenttutflow2.png)
            
        4.  This is the final result for this example: 'This is your user ID: `{res1.unit4Id}`'
            

#### Configure the Button component

In this example we configure the component as follows:

-   Select the **Button** component in the canvas and go to the **Properties** panel.
-   Open the **Main** menu and configure:
    -   _Text_: Enter the text: Get ID.
-   Open the **Logic map** tab in the bottom-right corner and configure:
    
    -   Drag the **On click** event to the viewport.
    -   Drag the **Trigger flow** action to the viewport and connect it to the **On click** event.
    -   Select **Trigger flow** action in the viewport to see the properties panel to the right.
    -   Display the **Flow** dropdown.
    -   Select the resource, for this example, _Get Id_.
        
        > ⚠️ Warning: If the resource does not appear in the dropdown, go to [Configure the resource](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-U4C-trigger-a-flow-from-AS/#configure-the-resource) section in this tutorial and come back to this step.
        
        ![Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/logicmaptutflow2.png)
        

You can see the final result in the following image:

![App in canvas](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/useridapp.png)

> Note: See [Components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/components-overview/) and [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/) for more details.

Finally, after configuring the flow, the app and the resource, select the **Save draft** button and preview you app.
