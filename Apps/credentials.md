## Overview

You can access the credentials section from:

-   The dashboard: Select the **Three dots** menu and choose credentials.
-   The app editor: Select the avatar on the Main toolbar and choose credentials.

![Credentials menu option](https://docs-external.u4pp.com/extensions-kit/app-studio/images/credentials.png)

In this section you can configure your **Credentials** to:

### Regular or System credentials

**System credentials** are created by Unit4 developers and cannot be modified by other App Studio users.

When you select System in the _Type_ properties drop-down, a new property field appears: _Id_. This field will be automatically filled in by the system with a unique Id identifier for your credentials once you have finished the process.

You must be logged in with a System tenant to create **System credentials**. Non-System tenants can only view and use **System credentials**.

> Note: To be a System tenant, feature flag APPSTUDIO\_SYSTEM must be enabled.

### Basic and Bearer credentials

You can configure **Credentials** for Basic and Bearer authentication types in the [Resources](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/) tab of App Studio.

> Note: For an **HTTP** resource, the authentication type and credential type must be the same. For example, in an **HTTP** resource with Basic authentication type, only Basic credential types are available.

![Credentials area overview](https://docs-external.u4pp.com/extensions-kit/app-studio/images/credentialsoverview2.png)

## New credential - Basic

You can create and edit multiple credentials for your app. To create a Basic credential:

-   Select the **\+ Add new** button.
-   Two properties are selected by default:
    -   _Type_ Regular. If you change it to System, the _Id_ field will appear.
    -   _Authentication type_ Basic.
-   Enter the required properties:
    -   _Name_ for the credential.
    -   _Username_
    -   _Password_

![New credential type basic](https://docs-external.u4pp.com/extensions-kit/app-studio/images/basic-credentials.png)

## New credential - Bearer

You can create and edit multiple credentials for your app. To create a Bearer credential:

-   Select the **\+ Add new** button.
-   Two properties are selected by default:
    -   _Type_ Regular. If you change it to System, the _Id_ field will appear.
    -   _Authentication type_ Basic. Change to Bearer.
-   Enter the properties:
    -   _Name_ for the credential. Required.
    -   _Grant type_. Required. _Client-credentials_ _Grant type_ is selected by default. Use _User-impersonation_ _Grant type_ when you need to keep the user ID, but you need to add new scopes to call the API.
    -   _Token endpoint_. Required.
    -   _Client Id_. Required.
    -   _Client secret_. Required.
    -   _Scope_. Optional.

![New credential type bearer](https://docs-external.u4pp.com/extensions-kit/app-studio/images/bearer-credentials.png)

## Use of parameters and services in credentials

You can use parameters in the following fields when creating a credential:

-   _Username_
-   _Password_
-   _Token endpoint_
-   _Client Id_
-   _Client secret_
-   _Scope_

To use a parameter, you can:

-   Enter the parameter manually using the format: `{{parameters.parameterName}}`.
-   Display the **Templating** dropdown by selecting the **Plus (+)** button and choosing the desired parameter from the options.

You can also use services in the _Token endpoint_ field to retrieve the URL for the U4IDS authority service of the logged in tenant. Display the **Templating** dropdown by selecting the **Plus (+)** button and choose the authority option nested under services>u4ids.

> IMPORTANT: You cannot use Liquid JS operations in any of the credential's fields.

![Parameters in credentials](https://docs-external.u4pp.com/extensions-kit/app-studio/images/parameters-services-credentials.png)

## Edit and deleting a credential

To edit a credential, select the **Edit** button and then save or cancel your changes.

To permanently delete a credential, select the three dots menu and then **Delete**.

> Note: Apps using these credentials that are edited or deleted may stop working. Review the correct behaviour of your app when you edit or delete a credential being used by one or more resources.

![Edit credentials](https://docs-external.u4pp.com/extensions-kit/app-studio/images/credentails-editdelete2.png)
