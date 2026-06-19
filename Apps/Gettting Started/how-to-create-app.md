To create a new app:

-   Select the **Create new app** tile in the dashboard.
-   Fill in the **New app** modal:

|Field|Description|Required|
|---|---|---|
|_Name_|Enter a unique name for your app.|Yes|
|_Description_|Enter an optional description for the app.|No|
|_Type_|Select the type of app from the drop-down. **System** apps are only available for **System** tenants.|Yes|

-   Select the **Create** button to open your app in the **Canvas**.
-   Start editing it.

To import an existing app:

-   Select the **Import app** tile in the dashboard.
-   Fill in the **Import app** modal:

|Field|Description|Required|
|---|---|---|
|_Name_|Enter a unique name for your app.|Yes|
|_Description_|Enter an optional description for the app.|No|
|_Type_|Select the type of app from the drop-down. **System** apps are only available for **System** tenants.|Yes|

-   Select the **Upload file** button to open the browser and select the JSON file to upload.
-   Select the **Import** button to import the app and open it in the **Canvas**.

> Note: You can also import apps from the **Canvas** using the **Import** button inside the **Three dots** menu in the **Main** toolbar. This option only allows you to import apps that match the design system of the current app.

### Creating a multi-screen app

You can create apps with multiple screens and define the navigation and transition between each screen.

> Note: There is a maximum of five screens per app.

To add other screens to your app:

-   Select the **Pencil** icon in the **Screen** header, to open the **Edit apps screens** menu.

![Screen header](https://docs-external.u4pp.com/extensions-kit/app-studio/images/screenheader.png)

-   Add your screens in the **Edit app screens** menu. Their names appear in the **Screen** header of your app, for example:

![Screen headings](https://docs-external.u4pp.com/extensions-kit/app-studio/images/screenheadings.png)

When editing a screen, **Undo** and **Redo** commands apply to that screen. If an error occurs, it is highlighted on the corresponding screen in the **Canvas**.

#### Defining navigation

To define the navigation between the screens you need the **Button** component. You must: - Add a button to the screen. - Define an **On click** event with a **Change screen** action. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

![Logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/logicmapchange.png)

#### Deleting a screen

To delete a screen:

-   Select the **Pencil** icon to open the **Edit app screens** menu.
-   Select the **Trash** icon for the screen you want to delete. The main screen cannot be deleted.

![Edit app screens menu](https://docs-external.u4pp.com/extensions-kit/app-studio/images/deletescreen2.png)

> Note: Deleting a screen cannot be reverted and you must verify and update the navigation between the existing screens as required.
