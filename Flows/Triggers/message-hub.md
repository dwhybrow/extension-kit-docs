# Message Hub Event

## Description

The **Message Hub Event** trigger allows a flow to be initiated when a particular event is published on the [Unit4 Message Hub](https://docs-external.u4pp.com/extensions-kit/glossary/message-hub/) by a specified source system. The triggering event on the Message Hub can be a generic event type, or an Enterprise document.

## Usage

### Configuration

The example below shows the **Message Hub Event** trigger configured to listen to events for the _Project_ document version _1.0_ published by the _u4bw_ source system.

![Image 3: Message Hub Event Config](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/mh-events-config.png)

### Input

The image above shows the input parameters required to configure the **Message Hub Event** trigger. The following parameters are required:

*   A valid source system name
*   The message type (generic event vs Enterprise document)
*   The event or document name
*   The version

> Note: If the message type is **Event** and the event (name/version combination) does not exist, it is created when the flow is saved.

For a list of available Enterprise document types and versions, see [Unit4 Ontology](https://ontology-latest.u4pp.com/enterprise-documents).

> Note: The trigger only receives events from the tenant where the flow is installed.

For the **u4bw** and **u4erp** source systems, when **Document** is selected as the _Message Type_, only the two most recent Enterprise document versions are displayed to prevent the selection of obsolete versions. If an older version was previously selected, a _Deprecated_ warning will appear, indicating that the selected Enterprise document version is no longer supported.

For the **Event** message type and other source systems, all existing versions are displayed.

### Output

The output is the content of the event message. Typically this is an Enterprise document that matches the given event type.
