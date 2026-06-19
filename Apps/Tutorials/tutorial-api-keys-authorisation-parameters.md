## Configure an HTTP resource to use API key authentication with parameters

This tutorial explains how to authenticate **HTTP** resources in App Studio using API keys stored as parameters.

In App Studio, **API key** authentication is handled manually, depending on how the target API expects the key to be sent. You can store the **API key** as a parameter and inject it into:

1.  A **query parameter**: [API key as a query parameter](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-api-keys-authorisation-parameters/#scenario-1-api-key-as-a-query-parameter).
2.  An **Authorization header** (Bearer token): [API key as an Authorization: Bearer header](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-api-keys-authorisation-parameters/#scenario-2-api-key-as-an-authorization-bearer-header).
3.  A **custom HTTP header**: [API key as a custom HTTP header](https://docs-external.u4pp.com/extensions-kit/app-studio/tutorials/tutorial-api-keys-authorisation-parameters/#scenario-3-api-key-as-a-custom-http-header).

> ⚠️ Warning: API keys are sensitive data. Always store them as **Extension Kit (EK) parameters marked as sensitive** to prevent them from being exposed in logs or the UI.

## Step 1: Create a sensitive API key parameter

Before configuring the **HTTP** resource, store your **API key** securely as a parameter.

Go to the **Parameters** menu in the Extension Kit portal:

1.  Select the **New parameter** button.
2.  Enter a name for the parameter in the _Name_ field, for example: `test_api_key`.
3.  Paste the **API key** value in the _Value_ field.
4.  Turn on the **Sensitive data** switch.
5.  Select the **Save** button.

> Note: Once created, the parameter can be referenced anywhere in your app using Liquid JS: `{{parameters.test_api_key}}`. Use the **Plus (+)** button to display the **Templating** dropdown and navigate to **parameters > test\_api\_key** to insert it.

___

## Scenario 1: API key as a query parameter

Use this scenario when the API expects the key appended to the URL as a query string, for example: `https://api.example.com/data?api_key=YOUR_KEY`.

Go to the **Resources** tab:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the newly created resource in the same panel.
3.  Select the **HTTP** _Type_ on the right panel.
4.  Select the **Pencil** icon to change the name, for example: 'My API - GET'.
5.  Configure:
    
6.  **Configuration** section:
    
    -   _Url_: Enter the base URL of your API endpoint with the query parameter appended, for example: `https://api.example.com/data?api_key={{parameters.test_api_key}}`.
    -   _Method_: Open the dropdown and select _GET_.
    -   _Authentication type_: Open the dropdown and select _NONE_.

___

Use this scenario when the API expects the key in the `Authorization` header in the format: `Authorization: Bearer YOUR_KEY`.

Go to the **Resources** tab:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the newly created resource in the same panel.
3.  Select the **HTTP** _Type_ on the right panel.
4.  Select the **Pencil** icon to change the name, for example: 'My API - BEARER'.
5.  Configure:
    
6.  **Configuration** section:
    
    -   _Url_: Enter the URL of your API endpoint.
    -   _Method_: Open the dropdown and select _GET_.
    -   _Authentication type_: Open the dropdown and select _NONE_.
7.  **Headers** section:
    
    -   _Key_: Enter `Authorization`.
    -   _Value_: Enter `Bearer {{parameters.test_api_key}}` or use the **Plus (+)** button to display the **Templating** dropdown and navigate to **parameters > test\_api\_key** and prepend the text `Bearer`.

___

Use this scenario when the API expects the key in a custom header, for example: `X-API-Key: YOUR_KEY`.

Go to the **Resources** tab:

1.  Select the **Plus (+)** button on top of the left panel to create a new resource.
2.  Select the newly created resource in the same panel.
3.  Select the **HTTP** _Type_ on the right panel.
4.  Select the **Pencil** icon to change the name, for example: 'My API - Custom header'.
5.  Configure:
    
6.  **Configuration** section:
    
    -   _Url_: Enter the URL of your API endpoint.
    -   _Method_: Open the dropdown and select _GET_.
    -   _Authentication type_: Open the dropdown and select _NONE_.
7.  **Headers** section:
    
    -   _Key_: Enter the custom header name expected by the API, for example: `X-API-Key`.
    -   _Value_: Enter `{{parameters.test_api_key}}` or use the **Plus (+)** button to display the **Templating** dropdown and navigate to **parameters > test\_api\_key**.

> Note: The exact header name depends on the API you are calling. Check the API documentation to confirm the expected header name.
