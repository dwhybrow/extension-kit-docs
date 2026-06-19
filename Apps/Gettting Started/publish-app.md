## Versions

Any created app is stored as a draft and it is not assigned a version number until you publish it.

Version number 1 is assigned to an app when you publish it for the first time. Each time you publish it again the version number is incremented by one.

You can revert to a previously published version by publishing the version again from the **View all versions** window. See the [View published versions](https://docs-external.u4pp.com/extensions-kit/app-studio/get-started/how-to-publish-app/#view-published-versions) section for more details.

## Publish an app

You can publish your app as an **Standalone** app or a **Business screen** app.

> Note: For details on publishing a **System** app go to the **System** apps documentation.

### Standalone app

___

To publish your app, follow these steps:

1.In the **Dashboard**, open the **App options** menu (three dots) of your app and select **Publish**.

2.In the **Publish new version** modal, you see the following fields described in the table:

|Field|Description|
|---|---|
|_Version_|This field is auto populated and cannot be changed. It shows the next version number to be assigned to your app.|
|_Version label_|Enter a version label for your app.|
|_Description_|Enter a description for this version of your app.|
|_Create URL suffix_|Enter a unique URL suffix for your app. This suffix is appended to the base URL to create the full URL for your app.|
|_App URL_|This field is auto populated based on the URL suffix you enter. You can copy this URL to share your app with others.|

![Publishing an app](https://docs-external.u4pp.com/extensions-kit/app-studio/images/publish-new-version.png)

3.Select the **Publish** button and the **App successfully published** modal appears. You can follow the link to your app, copy the app's URL or create a **Business screen** app by selecting the **Create ERPx entry** button.

![App successfully published window](https://docs-external.u4pp.com/extensions-kit/app-studio/images/app-published.png)

___

To publish your app as a **Business screen** app, follow these steps:

1.  Follow steps one to three in the **Standalone app** section above. To be able to create a menu entry in ERPx, your app must be published as a **Standalone** app first.
    
2.  In the **Dashboard**, open the **App options** menu (three dots) and select **Create ERPx entry**. You can also select the **Create ERPx entry** button in the **App successfully published** modal as shown above.
    
3.  In the **ERPx menu entry creation** modal, fill in the following field:
    
    -   _ERPx window title_: Enter the title for the window in the ERPx menu.
4.  Select the **Create entry** button and the newly created menu item is placed under the **Your employment** in ERPx.
    
5.  Open ERPx and go to the **Menu access** window and grant the necessary access rights to your app.
    
    ![Grant menu access](https://docs-external.u4pp.com/extensions-kit/app-studio/images/erpx-menu-access.png)
    
6.  If you want to move the menu item from **Your employment** to another place in the main menu, open the **Custom menu items** window and move the menu item to the desired place in the main menu. See [how to change an app location in ERPx](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-move-app-from-menu/) for more details.
    

## Modify a published app

You can modify an already published app without unpublishing it as follows:

1.  Open the app in the **Canvas**.
2.  Make your edits as required.
3.  Select **Publish** to publish your draft and give it a version number and replace the current published version.

> Note: If you select **Save draft** in a published app and close it without publishing, the changes remain as draft until you publish it.

## View published versions

To view the published versions of your app:

1.  Go to the **Dashboard**.
2.  Open the **App options** menu (three dots).
3.  Select **View all versions** to open the **Versions** window.

![View app versions](https://docs-external.u4pp.com/extensions-kit/app-studio/images/view-versions-window.png)

In this window you can see:

-   The **Versions** list with the following columns described in the table:

|Column|Description|
|---|---|
|_Version number_|The version number assigned to the app. A **Currently published** badge is displayed next to the version number of the currently published version.|
|_Label_|The version label given to the app when it was published.|
|_Description_|The description given to the app when it was published.|
|_Date_|The date when the version was published.|
|_Author_|The name of the user who created the app.|
|_Preview_|Select the _Eye_ icon to preview the app version. A modal opens where you can import to canvas or view the app full screen.|

-   The **Bottom toolbar** with the following buttons:
    
    -   **Delete version**: This deletes the selected version and cannot be undone. You cannot delete the current live published version, you must unpublish it first. You cannot delete all versions of an app.
    -   **Edit version details**: Select to change the version label and description.
    -   **Export**: Export the selected version as a JSON file. This JSON file can then be imported to the **Canvas** as a new app or shared with others. You can also export your app directly from the dashboard using the **App options** menu (three dots).
    
    ![Export from dashboard](https://docs-external.u4pp.com/extensions-kit/app-studio/images/exportdashboard2.png)
    
    -   **Publish/Unpublish**: When you select a published app the **Unpublish** button is available, select to unpublish. When you select an unpublished app the **Publish** button is available to unpublish the current version and replace it with the selected version.
    -   **Import to canvas**: Import the selected version to the **Canvas** for editing. This will overwrite the current unpublished draft version if one exists.
