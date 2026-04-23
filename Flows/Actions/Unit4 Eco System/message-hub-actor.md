# Message Hub Actor

## Description

The **Message Hub Actor** action allows a flow to call any pre-existing Actor that is available on the same message hub as the Extension Kit deployment.

## Usage

This action allows a command to be sent to any existing Actor and for the reply from that Actor to be returned to the flow. The flow can then continue based on the content of that reply. As such this is an action that could be used at any point in a flow.

![Image 3: Message hub actor](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/msghub-actor-01.png)

The _Command_ property of the input to the action (that encapsulates Properties, Body and ContentType) is the command that will be sent to the Actor, the content of this will vary depending on the Actor being called, please refer to the specific Actor's documentation for more information.

To ensure that a flow does not wait indefinitely for a reply from the Actor being called, a timeout can be set. This is achieved using the _TimeoutInSeconds_ property of the input to the action. When set to -1 the action will wait the maximum period of time possible (currently 86400 seconds), or it can be set to a value between 60 and 86400 seconds to wait for a reply. The _TimeoutExpired_ property of the action's output will be _true_ if a timeout occurred.

The _IsSuccessful_ property of the output of the action can be queried to determine whether the call to the Actor was successful, and further information will be contained in the _Message_ property in the case of an unsuccessful call.

The _Reply_ property of the output from the action contains the actual reply message returned from the Actor being called. The content of this will vary depending on the Actor being called, please refer to the specific Actor's documentation for more information.

### Input

```javascript
{
    'SourceSystem': 'string',
    'ActorAppId': 'string',
    'TenantId': 'string',
    'TimeoutInSeconds': 'int',
    'Command': {
        'Body': 'string',
        'ContentType': 'string',
        'Properties': {
            'key': 'value'
        }
    }
}
```

### Output

```javascript
{
    'IsSuccessful': true,
    'TimeoutExpired': false,
    'Message': 'string',
    'Reply':{
        'Body': 'string',
        'ContentType': 'string',
        'TimeoutExpired': false,
        'Message': 'string',
        'Properties': {
            'key': 'value'
        }
    }
}
```
