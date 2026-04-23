# Event Grid Publish

## Description

**Event Grid Publish** enables to send events through Azure Event Grid. It supports Event Grid Topics configured with Event Grid Schema and Cloud Event Schema v1.0.

## Usage

**Event Grid Publish** can be used to publish any information in a Event Grid.

Input fields in the action will change depending on the Event Schema selected. The event fields _Event type_, _Subject_ and _Event version_ can be configured by the flow designer.

A timestamp will be included in the event field _Event time_ containing time at which the event has been sent using the UTC format.

![Image 3: Event Grid Publish](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/event-grid-publish-configuration.png)

## Limitations

*   The event content is limited to 64KB, in case the event exceeed that limit the action will finish with an error and the event won't be sent. The recommendation is to store previously the data in a intermediate storage and send the event with a reference to the location where it the data has been stored. The subscription client would need to handle that reference and retrieve the information from the storage.
*   Content types supported are: plain text, xml and json.
*   Schema _Custom input Schema_ is not supported.
