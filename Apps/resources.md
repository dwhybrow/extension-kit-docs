## Overview

In the **Resources** tab, you can configure how your app sends and retrieves data. You can create multiple resources and use the data from your resources in the components using Liquid JS (see [Liquid support](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/)) or in the app's logic (see [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/)).

Create a new resource by selecting the **Plus (+)** button on the left panel. Each resource is created with an editable name and a non-editable tag. The tag is used in Liquid JS to use the resource data within the components, for example `{{res1}}`.

![Resources area overview](https://docs-external.u4pp.com/extensions-kit/app-studio/images/resourcesoverview.png)

You can create the following types of resource:

-   [Plain object](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#plain-object)
-   [HTTP](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#http)
-   [ERPx and ERPCR API](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#erpx-and-erpcr-api)
-   [Flow](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#flow)

## Plain Object

**Plain object** resources are used for storing simple data sets.

### Configuration

The following table describes the fields in the **Configuration** tab.

|Field|Description|
|---|---|
|_Code editor_|Enter your object in JSON. Maximum 25 000 characters. ![Example Plain Object resource example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/plainobject.png)|

> Note: App Studio does not support referencing dynamic content in Liquid JS (templating) in **Plain object** resources.

## HTTP

**HTTP** resources are used to make HTTP requests. You can configure when the request is made using the **HTTP request** action. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#httprequest) for more details.

![HTTP Resource example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/resourceHTTP.png)

### Configuration

The following table describes the fields in the **Configuration** tab.

|Field|Description|
|---|---|
|_Url_|Enter an URL. Only HTTPS URLs are allowed.|
|_Method_|Select one of the available REST methods: `GET`, `POST`, `DELETE`, `PUT`, `PATCH`.|
|_Authentication type_|Select one of the available authentication types: `NONE`, `BASIC`, `BEARER`, `U4Ids` (Unit4 Identity Services).|
|_Credentials_|Select a credential form the dropdown. This field is only available when you select a `BASIC` or a `BEARER` authentication. See [App Studio credentials](https://docs-external.u4pp.com/extensions-kit/app-studio/credentials/) for more details on how to save your credentials.|
|_Response type_|Select the type of response expected from the HTTP request.|
|_JSON_|Standard response type for returning structured JSON data (default).|
|_File_|Use when the API returns a file. This allows storing and referencing the file in the app.|

### Content definition

Available for `POST`, `DELETE`, `PUT` and `PATCH` methods.

The following table describes the fields in the **Content definition** tab.

|Field|Description|
|---|---|
|_Body data type_|Select from the dropdown JSON or multipart/form-data to send a file.|
|_JSON_|Enter a JSON in the _Content_ field. ![JSON](https://docs-external.u4pp.com/extensions-kit/app-studio/images/JSONcontentdefinition.png)|
|_Form data_|Add the form data items by selecting the **\+ Add form data item** button and filling in the following fields:![Form data](https://docs-external.u4pp.com/extensions-kit/app-studio/images/formdata.png)|
|_Type_|Select the type from the dropdown: _Text_ or _File_.|
|_Key_|Enter the key name.|
|_Content_|For _Text_ enter a string, typically hardcoded or coming from a field (see [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#templating-dropdown)).
For _File_ enter or select the _Component ID_ of a [File uploader component](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/file-uploader/) that you have added to the **Canvas** or select any **HTTP** Resource with _Response type: file_ that you have configured.
![Content dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/content.png)|

> -   See [**File uploader**](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/file-uploader/#how-to-use-the-attached-files) to configure the use of files attached by the user.
>     
> -   See [**How to use a downloaded file in an API request**](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#how-to-use-a-downloaded-file-in-an-api-request) for more details.

### Templating schema

The table below describes the fields in the **Templating schema** tab.

|Field|Description|
|---|---|
|_Schema_|Enter a schema that allows you to retrieve data in a component using Liquid JS. See [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#templating-dropdown) for more details.![Templating schema](https://docs-external.u4pp.com/extensions-kit/app-studio/images/templatingschema.png)|
|_Generate by JSON_|Select to automatically generate the _Schema_ from a JSON.|

The following table describes the fields in the **Headers** tab.

|Field|Description|
|---|---|
|_Id_|Enter the attribute that you want to store.|
|_Value_|Enter the data for the attribute.|
|_\+ New header_|Select the button to add a new header.|

## ERPx and ERPCR API

**ERPx API** and **ERP CR API** resources are used to make HTTP requests to the available ERPx and ERP CR public APIs. You can configure when the request is made using the **HTTP request** action. See [logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#httprequest) for more details.

Depending on the product you are using, you will be able to select either the **ERPx API** resource or the **ERP CR API** resource.

> ⚠️ Warning: For the resource to work properly in the end-user app, the user must have access to the ERPx and ERP CR Public APIs and to the specific endpoints you have used. Go to the **Public API access (XAG005)** window to check your user's configuration.

![ERPx API resource example configuration](https://docs-external.u4pp.com/extensions-kit/app-studio/images/resourceserpxapi.png)

### Configuration

The following table describes the fields in the **Configuration** tab.

|Field|Description|
|---|---|
|_API endpoint_|Select from the drop-down one of the available endpoints of the ERPx and ERP CR APIs.|
|_Method_|Select one of the available REST methods: `GET`, `POST`, `DELETE`, `PUT`, `PATCH`. The available methods depend on the selected endpoint.|
|_API version_|Select the API version. The latest available version is selected by default.|

### Parameters

The available parameters depend on the endpoint chosen. They are organized in the following groups:

The following table describes the fields in the **Parameters** tab.

|Field|Description|
|---|---|
|_Path_|Fill in the fields to define the route of your request within the API.|
|_Query_|Fill in the fields to refine or filter the results.|

### Content definition

Available for `POST`, `DELETE`, `PUT` and `PATCH` methods.

The following table describes the fields in the **Content definition** tab.

|Field|Description|
|---|---|
|_Body data type_|Select from the dropdown JSON or multipart/form-data to send a file.|
|_JSON_|Enter a JSON in the _Content_ field or select the **Get sample** button to load a sample. ![JSON](https://docs-external.u4pp.com/extensions-kit/app-studio/images/JSONcontentdefinitionERPx2.png)|
|_Form data_|Add the form data items by selecting the **\+ Add form data item** button and filling in the following fields:![Form data](https://docs-external.u4pp.com/extensions-kit/app-studio/images/formdata.png)|
|_Type_|Select the type from the dropdown: _Text_ or _File_.|
|_Key_|Enter the key name.|
|_Content_|For _Text_ enter a string, typically hardcoded or coming from a field (see [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#templating-dropdown)).
For _File_ enter or select the _Component ID_ of a [File uploader component](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/file-uploader/) that you have added to the **Canvas** or select any **HTTP** Resource with _Response type: file_ that you have configured.
![Content dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/images/content.png)|

> -   See [**File uploader**](https://docs-external.u4pp.com/extensions-kit/app-studio/components/U4Components/file-uploader/#how-to-use-the-attached-files) to configure the use of files attached by the user.
>     
> -   See [**How to use a downloaded file in an API request**](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#how-to-use-a-downloaded-file-in-an-api-request) for more details.

### Templating schema

The following table describes the fields in the **Templating schema** tab.

|Field|Description|
|---|---|
|_Schema_|Enter a schema that allows you to retrieve data in a component using Liquid JS. See [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#templating-dropdown) for more details. The field is pre-filled with the complete schema for the selected _API endpoint_. ![Templating schema](https://docs-external.u4pp.com/extensions-kit/app-studio/images/templatingschemaerp.png)|
|_Reload schema_|Select to reset the schema.|
|_Generate by JSON_|Select to automatically generate the _Schema_ from a JSON.|

## Flow

**Flow** resources are used to integrate your app with a flow in Extension Kit. This allows you to obtain data from the flow, delegate complex logic or processes, or do heavy tasks in the background. You can configure when the flow is triggered using the **Trigger flow** action. See [logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#triggerflow) for more details. A maximum of ten flows are supported per app.

The flow must be configured using the [**App** trigger](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/app/) and the [**App result** action](https://docs-external.u4pp.com/extensions-kit/built-in-actions/app-result/).

> Note: This resource is only available in ERPx.

### Configuration

The following table describes the fields in the **Configuration** tab.

|Field|Description|
|---|---|
|_Flow_|Select a flow from the dropdown. Only flows created with the **App** trigger are available.|
|_Create new flow_|Select to go to _My flows_ and create a new flow using **App** trigger.|
|_Go to flow_|Select to go to _My flows_ and edit/view the selected flow in the _Flow_ dropdown.|

### Content definition

The following table describes the fields in the **Content definition** tab.

|Field|Description|
|---|---|
|_Content_|Enter the JSON defined in the **App** trigger.|

> Note: See [**File uploader**](https://docs-external.u4pp.com/extensions-kit/app-studio/components/file-uploader-ripple/#how-to-use-the-attached-files) to configure the use of files attached by the user.

### Templating schema

The following table describes the fields in the **Templating schema** tab.

|Field|Description|
|---|---|
|_Schema_|Enter a schema to retrieve data from the **App result** action in the flow. You can use it in a component using Liquid JS. See [Templating dropdown](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#templating-dropdown) for more details ![JSON](https://docs-external.u4pp.com/extensions-kit/app-studio/images/JSONEK2.png).|
|_Generate by JSON_|Select to automatically generate the _Schema_ using the **App result** action JSON.|

## How to use a downloaded file in an API request

When you retrieve a file using an **HTTP** resource you can use this file as input for another API request.

1.  Create an **HTTP** resource with _Response type: File_ to download a file.
2.  Create the **HTTP** or **ERPx API** resource where you want to use the file. For **HTTP** resource, configure the _Response type_ as _JSON_. You have several options to use the file:
    
    -   Form data: In the **Content Definition** section, in the _Body data type_ drop-down, select _Form data_.
        
        -   Use _File type_: In the _Type_ dropdown select _File_ and then select the **Resource** with the file from the _Content_ drop-down.
        
        ![Using downloaded file in another API request](https://docs-external.u4pp.com/extensions-kit/app-studio/images/file-resource2.png)
        
        -   Use _Text type_: In the _Type_ dropdown select _Text_ and then use Liquid JS to enter the file or select it using the **Plus (+)** button to open the **Templating** drop-down.
        
        ![Using downloaded file in another API request](https://docs-external.u4pp.com/extensions-kit/app-studio/images/file-resource-as-text2.png)
        
    -   JSON: In the **Content Definition** section, in the _Body data type_ drop-down, select _JSON_ and reference the file using templating.
        
    
    ![Using downloaded file in another API request](https://docs-external.u4pp.com/extensions-kit/app-studio/images/file-resource-as-json.png)
    

## Auto-execution of unused GET HTTP and ERPx/CR resources

If an **HTTP** resource with method `GET` is configured in an app but is not used in any **HTTP request** actions in the app logic, it will execute automatically in the following cases:

-   On app launch.
-   Each time a dependent field is updated (for example, **Text input**, **Dropdown**, **Checkbox** components), if the resource has any dependencies configured.

For **ERPx/CR API** resources with method `GET`, the auto-execution also happens when the resource is not used in any **HTTP request** action, it will execute automatically in the following cases:

-   On app launch if the resource has any field dependencies configured.
-   Each time a dependent field is updated (for example, **Text input**, **Dropdown**, **Checkbox** components), if the resource has any dependencies configured.

> ⚠️ Warning: This behavior is discouraged. Always use the **HTTP request** action in the app logic to explicitly trigger resources. Relying on auto-execution makes the app logic harder to understand and maintain.
