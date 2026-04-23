# HTTP Request

## Description

The **HTTP Request** action allows a flow to perform [HTTP actions](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods) on REST endpoints.

Additional information can be passed as header information such as [Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) and [MIME types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Complete_list_of_MIME_types), and as content containing the request body information.

After the request is executed, an [HTTP response status code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) is returned with the response content as a string. The **HTTP Request** action automatically supports compression/decompression using the gzip and deflate algorithms (see [Headers](https://docs-external.u4pp.com/extensions-kit/built-in-actions/http-request/#headers)).

![Image 1: REST Request](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-01.png)

## Usage

The **HTTP Request** action allows your application to integrate with external applications and services to, for example:

*   Extend the functionality of your application by leveraging external data, services, and resources.
*   Submit, update and retrieve data.
*   Orchestrate services and manage inter-service communication.
*   Trigger actions in other applications and systems, such as start a process, send automated notifications, or automate backups.

## Basic configuration

Basic configuration involves defining:

*   The authentication mechanism, if any, to be used when connecting with the remote server. You can configure the following types of authentication:

    *   **None:** No authentication needed.
    *   **Basic:** Basic authentication is a simple authentication scheme built into the HTTP protocol. The client sends HTTP requests with the _Authorization_ header, that contains base64-encoded username and password.

![Image 2: Basic Authentication](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-authorization-01.png)

    *   **Bearer:** Bearer authentication, also called token authentication, is an HTTP authentication scheme that involves security tokens called bearer tokens. The name _Bearer authentication_ can be understood as _give access to the bearer of this token._

![Image 3: Bearer Authentication](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-authorization-bearer.png)

*   The method to be used in the request. The following methods are currently supported:

    *   GET 
    *   HEAD 
    *   POST 
    *   PUT
    *   DELETE 
    *   OPTIONS 
    *   PATCH 

*   The URL of the remote server.

## Advanced configuration

Advanced configuration allows you to attach certificates and disable retry requests for the HTTP request.

![Image 4: Certificate drop-down](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-certificates.png)

### Certificates

You can attach a _Client Certificate_ in the **Advanced configuration** section, where a drop-down allows you to select one of the certificates added for this tenant.

The option to attach a _Remote Certificate_ is also available to provide added identity authentication on received data through a [mTLS protocol](https://www.cloudflare.com/learning/access-management/what-is-mutual-tls/). For more details about setting up certificates, see [Certificates](https://docs-external.u4pp.com/extensions-kit/guides/portal/certificates/).

> Note: You must provide a _Client Certificate_ before you can add a _Remote Certificate_ to the HTTP request.

### Disable Retry Requests

The **Disable Retry Requests** setting allows you to deactivate retry requests with only retries being sent for the error response _429 Too Many Requests_.

In some cases, when the external endpoint does not respond within the default timeout for the **HTTP Request** action of 100 seconds, a retry mechanism resends the request. In some situations this retry can result in the request being posted twice because the external endpoint is still handling the first request. The **Disable Retry Requests** setting is available to handle such situations.

#### General retry settings

The HTTP request uses default retry settings to ensure resilience and handle common transient errors effectively.

*   _408 - Request Timeout_
*   _429 - Too Many Requests_
*   _5XX - Server Error Responses_

The maximum number of retries set for each operation is 5.

The complete retry operation (within the retries and corresponding waiting times in between) will timeout after 9 minutes.

Each retry operation will timeout after 100 seconds.

| Retry setting | Description |
| --- | --- |
| Retry- After | The **Retry-After** header is a standard response HTTP header that indicates how long the user agent should wait before making another request. It is sent within statuses 503 (Service Unavailable), 429 (Too Many Requests) as detailed [Retry-After](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Retry-After). It is taken into account in the default retry pattern implementation. |
| 429 - Too Many Requests | When a status 429 - Too Many Requests response is returned by the HTTP request, the waiting time before retrying is: - Retry-After header value if received with a maximum time of thirty seconds - A random amount of time as per [this](https://www.awsarchitectureblog.com/2015/03/backoff.html) distribution. The random time is generated between 250 milliseconds and 30 seconds. |
| 503 - Service Unavailable | When a status 503 (Service Unavailable) is returned by the HTTP request, the waiting time before retrying is: - Retry-After header value if received (with a maximum time of one minute) - One minute wait if no Retry-After header is received |
| Any of the other status considered previously as transient | When a status 5XX (Server error) besides 503, or 408 (Request timeout) is returned by the HTTP request, the waiting time before retrying is: - A random amount of time as described in [Exponential Backoff And Jitter](https://www.awsarchitectureblog.com/2015/03/backoff.html) distribution. The random time is generated between 250 milliseconds and 30 seconds. |

## Content definition

The **Content definition** section is where you define the following:

*   Content type
*   Content of the request body
*   Header information

### Content type

The _Content Type_ drop-down list presents the most common content types, but if the content type you wish to use is not listed here, you can manually enter it.

The listed content types are:

| Content type | Description |
| --- | --- |
| JSON (application/json) | JSON formatted data using JSON's standard UTF-8 encoding. Note: If you do not want the content type to include the encoding information, then you must add a space after the `application/json` entry. ![Image 5: application/json with space](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/application-json-space.png) |
| JSON Patch (application/json-patch+json) | Used to define a JSON document format for expressing a sequence of operations to be applied to a JSON document. |
| XML (application/xml) | XML formatted data. |
| XML (text/xml) | XML formatted data. |
| Text (text/plain) | Plain text with no specific formatting. |
| x-www-form-urlencoded | The default content type for HTML forms. Form data is encoded as key-value pairs, similar to query parameters in the URL. |
| Multipart/form-data | Used for uploading files through HTML forms. |
| Binary (application/octet-stream) | A generic stream of binary data used for file uploads when the file type is unknown or not specified. |
| XML (application/soap+xml) | Used to signify that the body of the message contains a SOAP envelope formatted as XML. |

### Multipart/form-data content type support

The **HTTP Request** action supports the use of the **Multipart/form-data** content type to allow data to be uploaded using HTML forms.

![Image 6: Multipart/form-data drop-down](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-multipart-01.png)

Once you have selected the content type, a new **Form Data** section is displayed, where you configure the form data.

![Image 7: Multipart/form-data form list](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-multipart-02.png)

You can add and configure form data fields by selecting the **Add** button and adding the information in the pop-up window.

The following field types are available:

*   _Text_: The _Text_ form data value requires a **key** and **value** provided in the configuration.
*   _File_: The _File_ form data value requires a **key**, the file content **value** and a **filename**. The supported file content is plain text for text files (XML, CSV, JSON, etc.) and base64 encoding for binary files (PDF, PNG, etc.).

![Image 8: Multipart/form-data form text](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-multipart-03.png)![Image 9: Multipart/form-data form file](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/httpreq-multipart-04.png)

## Content

The **Content** section is where you define the body content of the HTTP request. This data can be of various types, such as JSON, XML, plain text, form data, or file uploads, depending on the content type.

The **Headers** section is where you define any HTTP request header information in addition to the _Content Type_ already defined. Header information is defined as key-value pairs, for example:

![Image 10: HTTP request headers](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/http-headers.png)

> Note: The _Accept-Encoding_ header is set internally by the **HTTP Request** action accepting compressed content with the gzip or deflate algorithm. Any other compression header value manually set by the user will not be taken into account.

## Input samples in JSON notation

### Authentication type: None

```
{
    'AuthenticationType': 'None'
    'Method': 'string',
    'Url': 'string',
    'ContentType': 'string',
    'Content': 'string',
    'Headers': {
        'key': 'value'
    }
}
```

### Authentication type: Basic

```
{
      'AuthenticationType': 'Basic',
      'Username': 'string',
      'Password': 'string',
      'Method': 'string',
      'Url': 'string',
      'ContentType': 'string',
      'Content': 'string',
      'Headers': {
        'key': 'value'
        }
    }
```

### Authentication type: Bearer

```
{
      'AuthenticationType': 'Bearer',
      'Token endpoint': 'string',
      'Client': 'string',
      'Client Secret': 'string',
      'Requested Scope': 'string',
      'Method': 'string',
      'Url': 'string',
      'ContentType': 'string',
      'Content': 'string',
      'Headers': {
        'key': 'value'
        }
    }
```

## Output sample

```
{
     'StatusCode': 200,
     'Headers': {
       'key': [
         'value'
        ]
    },
     'Response': 'string'
}
```
