To use query parameters in your App Studio app, you need to :

1.  Configure them in the **Query parameters** panel.
2.  Use these parameters in the Components or Resources.
3.  Use them in the URL of your app in one of the following scenarios:
    -   [**Standalone** apps](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-query-parameters/#standalone-app): The app is launched directly and the query parameters are passed via the URL.
    -   [**From the Portfolio Window in ERPx**](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-query-parameters/#from-the-portfolio-window-in-erpx): The app is opened from ERPx and the query parameters are set through contextual actions.
    -   [**Using an ERPx URL with query parameters**](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-query-parameters/#using-an-erpx-url-with-query-parameters): The app is accessed via a direct ERPx URL, including query parameters for pre-filtering data.

This will allow you to dynamically adjust content based on the parameters passed in the URL.

## 1\. Configure a query parameter:

To configure a query parameter in your App Studio app, follow these steps:

![Adding a Query Parameter](https://docs-external.u4pp.com/extensions-kit/app-studio/images/tutorialsimg/tut6-add-query-parameter.png)

1.  Go to the **Query parameters** panel in the **Canvas** main toolbar.
2.  In the **Manage query parameters** modal, select the **Add** button to add a row.
3.  Select the row and enter a name for your query parameter, for example, `project`.
4.  Select the **Close** button to save and close the modal.

> Note: See [Query parameters panel](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#main-toolbar) and [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details.

## 2\. Use query parameters in Components or Resources

You can use query parameters in both Components and Resources in your App Studio app.

### Components

Enter the query parameter using Liquid JS or use the [**Templating dropdown**](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) in the component property that you want to be prepopulated. For example, in a **Text input** component, you can set the _Default value_ property to:`{{queryParameters.project}}`.

### Resources

Enter your query parameter as a filter in a resource using Liquid JS or the [**Templating dropdown**](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) in the _Filter_ field inside the **Parameters** menu of the resource. For example, to filter the `projectId` property using your query parameter, you can set the filter to:`projectId eq '{{queryParameters.project}}`, then you can use that resource to prepopulate a component, for example a **Data grid**.

## 3\. Use query parameters in URL

### Standalone app

___

You can launch an app with prefiltered data appending the query parameter to the app URL like this:

**Example URL:**

`https://u4nextsandbox-renderer.azurewebsites.net/preview/cf94361a-3042-46fa-bbc3-953d0f8422bf?tenantId=b5cfb2be-56ba-48d3-839b-bed90d4e57bb&QUERYPARAMETER=VALUE`

Where:

-   `QUERYPARAMETER`: Is the name of the query parameter you created in App Studio. For example, `project`.
-   `VALUE`: Is the value to filter for. For example, `1000`.

For example, this URL:`https://u4nextsandbox-renderer.azurewebsites.net/preview/cf94361a-3042-46fa-bbc3-953d0f8422bf?tenantId=b5cfb2be-56ba-48d3-839b-bed90d4e57bb&project=1000` will open the app with the data filtered by `project=1000`.

### From the Portfolio Window in ERPx

___

To use query parameters from ERPx:

1.  Publish the app in ERPx. See [create a menu entry in ERPx](https://docs-external.u4pp.com/extensions-kit/app-studio/get-started/how-to-publish-app/#business-screen-app-create-a-menu-entry-in-erpx) for more details.
2.  In the **Contextual action setup** window, configure the new action and set the parameter value, for example, `1000`. You can use any available ERPx parameter.
3.  Open the **Portfolio** window and select the contextual action setup you created.
4.  Select a parameter to pass to the app.

> Note: The parameter value is fixed in ERPx, but you can use any ERPx parameter.

### Using an ERPx URL with query parameters

___

You can open ERPx with prefiltered data applied to the App Studio window using a direct link:

**Example URL:**

`https://eu01.erpx.unit4rd.com/?accessId=ASAPPMENUID&viewId=APPNAME&QUERYPARAM=VALUE`

Where:

-   `ASAPPMENUID`: Is the app menu ID. To find it, go to the app in the **Dashboard**, open the **App options** menu (three dots) and select **View info**.
-   `APPNAME`: Is usually `U4APP`.
-   `QUERYPARAM`: Is the query parameter you created in App Studio.
-   `VALUE`: Is the value to filter for.
