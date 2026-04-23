# Webhook

The **Webhook** trigger allows an HTTP request to initiate a flow defined in the Extension Kit (U4EK) Portal.

In a typical scenario, this trigger is used to allow a workflow defined somewhere else to continue execution in a U4EK flow. See [Appendix A: LogicApps](https://docs-external.u4pp.com/extensions-kit/appendix/logicapps/) for more details.

## Trigger input

![Image 1: Webhook v2](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/webhookv2-input2.png)

### Basic configuration

| **Field** | **Description** |  |  | **Required** |
| --- | --- | --- | --- | --- |
| _Name_ | Enter a unique name for the trigger. |  |  | Yes |
| _Authentication_ | Select one of the available authentication methods. |  |  | Yes |
|  | _None_ | Select if you do not want to secure your endpoint. |  | No |
|  | _Basic_ | Select to use a user and password. When calling this endpoint, an authentication header must be provided as described in the IETF document [The 'Basic' HTTP Authentication Scheme](https://tools.ietf.org/html/rfc7617). |  | No |
|  |  | _User name_ | Enter the user name. | Yes |
|  |  | _Password_ | Enter the password. | Yes |
|  | _U4IDS (connected)_ | Select to use Unit4 Identity Services (U4IDS). When calling this endpoint, a token, obtained from U4IDS, must be sent in the authorisation header. |  | No |
|  |  | _Claim rules_ | Select the **Add** button to request certain claims to be present in the token. | Yes |
|  |  | _Id_ | Enter the identifier of the claim. | Yes |
|  |  | _Value_ | Enter the value of the claim. You can use macros such as `{{triggerId}}` and `{{tenant}}`, and they will automatically be replaced with their actual values. | Yes |
|  | _Azure active directory_ | Select to use Azure active directory. When calling this endpoint, a token, obtained from Azure active directory, must be sent in the authorisation header. |  | No |
|  |  | _Claim rules_ | Select the **Add** button to request certain claims to be present in the token. | Yes |
|  |  | _Id_ | Enter the identifier of the claim. | Yes |
|  |  | _Value_ | Enter the value of the _Id_. | Yes |

### Request body configuration

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Content type_ | Select the type of payload for your **Webhook** trigger from the drop-down. | No |
| _Input schema_ | Enter a schema to be shown in the trigger's configuration. Only available for JSON _Content type_. | No |
| _Generate by JSON_ | Select to automatically generate the schema from a JSON. Only available for JSON _Content type_. | No |

### Primary response configuration

Customise the response from the trigger by configuring the response to `POST` requests. If no configuration is made, the Webhook responds with a _204 - No Content_ code.

| **Field** | **Description** |  | **Required** |
| --- | --- | --- | --- |
| _Status code_ | Select the code for the response. By default, the response is _204 - No Content_. |  | No |
| _Headers_ | Select the **Add** button to include custom headers. |  | No |
|  | _Id_ | Enter the identifier for the header. | Yes |
|  | _Value_ | Enter the value od the _Id_. | Yes |
| _Content type_ | Select the type of body response. |  | No |
| _Content_ | Enter a custom body response. |  | No |

### Secondary endpoint configuration

The **Webhook** trigger supports both primary and secondary response configurations, but only `POST` requests trigger the flow. In this menu choose to trigger the flow with a different method. You can configure this method in the **Secondary response configuration** menu.

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Secondary endpoint triggers the flow_ | Select the checkbox to enable requests to the secondary endpoint to trigger the flow. | No |

### Secondary response configuration

Add `OPTIONS`, `GET` and `PUT` methods to the **Webhook** trigger response. Although you can configure them to trigger the flow (see **Secondary endpoint configuration** section), they are meant to be used for validating subscription systems such as [Event Grid](https://docs.microsoft.com/en-us/azure/event-grid/webhook-event-delivery#endpoint-validation-with-cloudevents-v10).

| **Field** | **Description** |  | **Required** |
| --- | --- | --- | --- |
| _Method_ | Select one of the supported methods from the drop-down. If the **Webhook** is called with a method that is not configured, the response will be _405 - Method not allowed_. |  | No |
| _Status code_ | Select the code for the response. By default, the response is _204 - No Content_. |  | No |
| _Headers_ | Select the **Add** button to include custom headers. |  | No |
|  | _Id_ | Enter the identifier for the header. | Yes |
|  | _Value_ | Enter the value od the _Id_. | Yes |
| _Content type_ | Select the type of body response. |  | No |
| _Content_ | Enter a custom body response. |  | No |

### Advanced configuration - Mutual TLS

Mutual TLS, also known as mTLS or 2-way SSL, is a technique for two-way authentication. mTLS ensures that the parties at each end of a connection are who they claim to be. The information within their respective TLS certificates provides additional verification.

> Note: Flows triggered with expired certificates, certificates whose validity has not yet started, or certificates that do not match the **Webhook** setup will not run.

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Client certificate_ | Select the certificate from the drop-down. You need to create the certificate in the **Certificates** menu in the Extension Kit portal dashboard. See [Certificates](https://docs-external.u4pp.com/extensions-kit/guides/portal/certificates/) for more details. | No |

> ⚠️ Warning: Incoming **Webhook** calls must have their _Certificate_ and respective _Private key_. The _Private key_ is not saved or stored and does not reach the Extension Kit area. It is only used to guarantee the ownership of the matching inbound certificate during the process.

### Templating system

The **Webhook** trigger supports templating to build a custom response. Supported templates are:

*   _Query_: The following expression `{{step0.request.query[QueryKey]}}` will be replaced by the value of the query parameter, if present, in the incoming request.

*   _Header_: The following expression `{{step0.request.header[Header]}}` will be replaced by the value of the header, if present, in the incoming request.

*   _Body_: The following expression `{{step0.request.body.propertyPath}}` will be replaced by the value of the payload, if present, in the incoming request. It supports simple and deep properties and array values.

#### Example: Subscribe an Extension Kit flow to an Event Grid

Custom response together with the templating system can be used to validate event source subscriptions. It means that an Extension Kit flow can be subscribed to a event source so it will be triggered when new events occur in the source.

You can use the following configuration to subscribe a flow to an Event Grid with Cloud Event Schema v1.0.

![Image 2: Webhook Event Grid subscription](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/webhook-example-subscription.png)

## Trigger output

| **Property** | **Description** |
| --- | --- |
| _Body_ | Shows the body data of the response. An empty object means there is no business data in this response. |
| _Headers_ | Shows the headers of the response. Includes standard HTTP headers and system-specific headers. |
| _Queries_ | Shows the provided queries. An empty object means no query string parameters were provided in the request. |

![Image 3: Webhook output](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/webhookv2-output.png)

After saving a flow that uses the **Webhook** trigger, the system generates extra data. You can find them in the **Overview** section of the flow, located at the bottom of the **Flow's roadmap**.

> Note: The extra data takes some time to be generated and displayed in the **Overview** section.

The following extra data is generated:

*   _Address_: The URL to trigger the flow. The endpoint to which the data needs to be pushed by the external application.
*   _Metadata address_: Provides an endpoint that returns the metadata in Swagger or OpenAPI format. For example, this metadata address can be used when using the Logic app's _Http plus Swagger_ connector.
*   _Trigger ID_: Unique ID number generated by Extension Kit to identify the trigger.

![Image 4: Webhook config](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/webhookv2-extradata2.png)

> Note: The generated extra data _Address_, _Metadata address_ and _Trigger ID_ remain static and do not change if the flow is disabled or the **Webhook** trigger is updated. When the flow is disabled, the extra data is not visible.

## Known issue

When posting a request where the _Body_ is a JSON with a property that has a slash symbol (/) for an escape character like in this example:

`"timezone": "Europe\/Paris"`

The escape character \ is removed altering the payload.

### Workaround

1.   Choose _Text_ as a _Content-Type_ in the **Request body configuration** section.
2.   Encode the _Body_ using base 64 and decode it using the **Run code** action before using it for sha256 digest, like in the following example:

```
{%- assign payloadSignature = step0.Headers["X-Yousign-Signature-256"] -%}
{%- assign payload = step0.Body | string.strip_newlines | string.replace '": ' '":' | string.base64_encode -%}
```
