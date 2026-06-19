The **File uploader** component allows the users of your app to upload files as attachments.

The user can:

-   Attach one or more files to the app either by selecting the button on the component to open a documentation navigation browser or by dropping files into the component.
    
-   See the file name and the format once they have uploaded a file.
    
-   Clear the files to be uploaded.
    

![File uploader with file](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/fileuploaderbehaviourripple.png)

> Note: You can use the files uploaded by the user in an **HTTP Request** action or in an Extension Kit flow. See [how to use the attached files](https://docs-external.u4pp.com/extensions-kit/app-studio/components/file-uploader-ripple/#how-to-use-the-attached-files) for more details.

## Example

You can use the **File uploader** component to attach a logo and update a customer in ERPx/CR. In this example:

-   Users can attach a .png to a previously selected customer using the **File uploader** component.
    
-   Users can upload the .png to the customer in ERPx/CR using a **Button** component.
    

![File uploader component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/fileuploaderusageripple.png)

> Note: The **File uploader** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **File uploader** properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the text you want to be displayed above the component.|Yes|
|_Description_|Add a description for the component. This is displayed under the _Label_.|No|
|_Restrict file formats_|Enter the allowed file extension(s) separated by commas (e.g. .pdf, doc). To allow all formats, leave empty.|No|
|_Maximum total size (MB)_|Enter the maximum size allowed for the sum of all the attached files. The minimum value is 1 MB, and the maximum allowed by App Studio is 60 MB.|Yes|
|_Minimum files_|Enter the minimum number of accepted files.|Yes|
|_Maximum files_|Enter the maximum number of accepted files. Ten is the maximum.|Yes|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_List placement_|Select the desired position for the list of uploaded files from the drop-down menu.|No|

> Note: The _Align_ property in **Columns** is set to _Stretch_ by default, so the component will take all the available width. To change that, set the _Align_ property to _Left_, _Center_ or _Right_.

### Validation properties

The following table describes the validation properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Optional field_|Turn on to make the component optional. By default, the component is required.|No|
|_Add rule_|Add rules in Liquid JS to specify when the component is required. If no rules are set, the component will be required in all instances.|No|
|_Message_|Enter a message to be displayed if the user does not fill in the input. A default message is otherwise shown.|No|
|_Additional validations_|Select any or all checkboxes to add validations.|No|
|_Error_|Select the checkbox to add a red error style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the error validation is shown.|Yes|
|_Error message_|Enter a message to be displayed if the user fills in the input incorrectly.|Yes|
|_Warning_|Select the checkbox to add an orange warning style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the warning validation is shown.|Yes|
|_Warning message_|Enter a message to give the user advice on how to better fill in the input.|Yes|
|_Positive_|Select the checkbox to add a green positive style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the positive validation is shown.|Yes|
|_Positive message_|Enter a message to tell the user that the input has been correctly filled in.|Yes|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.

To perform validation before submitting data you must use the **Field validation** action in the **Logic drawer**. See relevant documentation for more details:

-   [Field validation action](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-validations-action).
-   [Validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/) and the [Example: Validating date input before sending data](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#example-validating-date-input-before-sending-data) section for step-by-step guidance.

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Hidden rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|
|_Disabled_|Select the checkbox to disable the component in the end-user app.|No|
|_Disabled rule_|You can set rules to disable the component using Liquid JS. If no rules are set, the component will be disabled in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text that allows assistive technology to attach a label to the component.|No|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|

## Events

The **File uploader** component supports the **On update** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

![File uploader logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/onupdatefileuploader3ripple.png)

## How to use the attached files

To use the files attached by the users you must configure them in the [**Resources**](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/) tab.

Inside the _Content definition_ section of the resource you can:

1.  Enter the Liquid JS formula inside your JSON by hand, for example, `{{fileUploader1.files[0].content}}` .
    
2.  Select the **Plus (+)** button to display the **Liquid templating** drop-down:
    
    -   Open the _Fields_ drop-down.
    -   Open the **File uploader** you need. For example, `fileUploader1`.
        -   To use all files: Select `All files`.
        -   To use specific properties of the file: Open the file you want to use. For example, `[0] File 1`. Select the property or properties you want to use depending of the API you are using:
            -   `name`
            -   `contentType`
            -   `content`

![File uploader Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/images/fileuploaderfiles.png)

> Note: The file position in the array is randomly assigned. To have control over which specific file you are selecting it is recommended to use different **File uploaders**. All files are encoded in Base64.
