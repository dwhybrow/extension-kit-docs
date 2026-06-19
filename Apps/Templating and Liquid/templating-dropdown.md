App Studio has a **Templating** drop-down to help you render content in different components using Liquid JS. Select the **Plus (+)** button to open the drop-down as shown in the image below.

![Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquidtemplate2.png)

> Note: The **Templating** drop-down has limited entries in some of the properties of the **Dropdown**, **Combobox**, **Radio group** and **Data grid** components. For example, in the **Combobox** component's _Display field_ property, only properties of the resource used in the _Options_ property are available. See component documentation for more details.

## 1\. Select title

App Studio's APPSTUDIO\_TITLES feature flag, supports predefined system titles. Titles for Standalone apps are displayed in the end-user’s browser language and in the established ERPx language for Business screen apps.

To add a title that you want to appear in the end-user app’s configured language, you can:

-   Option A: Write the title in the field if you know the Liquid JS formula.
    
-   Option B: Open the **Select title** modal to search for the title by following these steps:
    
    1.  Select the **Plus (+)** button to display the **Templating** drop-down.
    2.  Select the **Select title** button to open the modal.
    3.  Display the drop-down and choose the language you want to search in.
    4.  Search for the title. You can search by writing text or the title’s ID number.
    5.  Select the **Search** button.
    6.  Choose and select the desired result from the results window.
    7.  Edit the _Default value_. This text is shown in the end-user app if there is no translation for the targeted language. The field is pre-filled with your selection.
    8.  Open the _Parameters_ menu if available. Parameters are usually represented by `%s` or `"0"`, where the letter and number change. You can use Liquid JS to enter the parameter or select a value from the **Templating** drop-down by selecting the **Plus (+)** button. For example: `user.name` if you want the `"0"` parameter to be replaced with the user name.
    9.  Select **Apply**.

![Select title modal](https://docs-external.u4pp.com/extensions-kit/app-studio/images/selecttitle2.png)

> Note: The language in which you search for your title does not affect the output. The end-user sees the title in the language set in their browser or in ERPx/CR.

## 2\. User

The _User_ drop-down allows you to select data from the user authenticated through Unit4 Identity Services (IDS) to reference in Liquid JS. You can also enter the value directly in Liquid JS if you know the formula by typing `{{user.valueName}}`.

![User example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquiduser2.png)

## 3\. U4erp

The _u4erp_ drop-down entry allows you to retrieve the user ID and the company (_clientid_) for users who have logged in to ERPx/CR, and reference them in Liquid JS. You can also enter the value directly in Liquid JS if you know the formula by typing `{{u4erp.valueName}}`.

![U4erp example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquidu4uerp2.png)

> Note: The value will only be rendered in the end-user app for **Business screen** apps (ERPx/CR apps).

## 4\. Parameters

Standard Extension Kit parameters are supported in component properties. You can use Liquid JS to allow values used across apps and flows to be referenced as parameters.

The _Parameters_ drop-down allows you to select a parameter from the list of available ones. You can also reference the parameters directly using Liquid JS by typing `{{parameters.parameterName}}`. These properties are defined in the **Parameters** section in the Extension Kit main menu. See [Parameters](https://docs-external.u4pp.com/extensions-kit/guides/portal/tenant-parameters/) for more details.

![Component property parameters](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquidparameters2.png)

When you hover the cursor over a parameter its value is displayed. Sensitive parameters are displayed as locked and their values are not shown.

Parameters are resolved when rendering the app. If a parameter is not defined, an empty value is shown in the end-user app, and if the parameter is sensitive, it is not shown and the Liquid JS formula is displayed.

> Note: When you import an app, all parameters' references are also imported and you must verify that they are still valid in the imported app.

## 5\. Query parameters

The _Query parameters_ drop-down allows you to select the query parameters defined in the [**Query parameters** panel](https://docs-external.u4pp.com/extensions-kit/app-studio/canvas/#main-toolbar) in the **Canvas** main toolbar. You can also reference them directly using Liquid JS by typing `{{queryParameters.parameterName}}`.

Query parameters are used to pass data to the app when it is opened by adding them to the URL. For example, if you have a query parameter called `companyId`, you can pass it in the URL as follows: `https://u4nextqa-renderer.azurewebsites.net/d2867dfb-f3df-4906-9b1b-f2533c210aaf?tenantId=a21ca3bf-ee5d-4e7e-af82-a5aa8ba7ea32&companyId=EN`. See [using query parameters in App Studio tutorial](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-query-parameters/) for more details.

![Query parameters templating](https://docs-external.u4pp.com/extensions-kit/app-studio/images/queryparameters-templating.png)

## 6\. Fields

The _Fields_ drop-down allows you to select the data the user has entered in the components to reference in Liquid JS. You can also reference them directly using Liquid JS by typing `{{componentID.valueName}}`.

To search for the value you want, open the drop-down and search for the _Component ID_ drop-down. Open it and select _value_ which corresponds with the data the user has entered in the field.

![Fields example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquidfields.png)

Component fields that only allow you to select arrays work differently:

-   In the **Table** component you can choose between all rows, added rows, deleted rows or edited rows.
-   In the **Select** component, in the _Options_ field, only arrays, if any, are available.

![Options field example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquidoptionsfield2.png)

> Note: All the resources that you configure and have fields available to reference with Liquid JS, appear in the **Templating** drop-down, under the _User_ drop-down.

![Resources example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/liquidresources.png)
