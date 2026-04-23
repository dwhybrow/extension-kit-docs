# Email

## Description

The **Email** action allows to send an email.

## Usage

This action allows to send an email from a no-reply Extension Kit address.

![Image 5: Email Action](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/email-action-screen.png)

The _To email_, _Subject_ and _Body_ properties are mandatory to send an email. The _Reply to_ property of the input is not mandatory but allows to set an email address to reply. The _Body format_ property will always be set to 'Text' by default. It defines how the email sender will consider the text included in the _Body_ field.

This action supports the use of the parameters in all of this fields but Body Format.

In the output there are two properties: _Succeeded_, to let us know if the email was sent successfuly and _Answer_ with more descriptive information.

## Validations

### To email field

It will accept:

*   a single email address: e.g. "receiver@unit4.com"
*   a list of email addresses separated by semicolon (";"): e.g. "receiver1@unit4.com; receiver2@unit4.com". The use of any other separator is not allowed.

In case a templating reference is included, the validity check will be performed at runtime, when it is resolved.

The email will only be sent if _at least one_ of the recipient addresses in the list is correct. The email will be sent to the correct recipients, and the action will then be considered succeeded. Information will be included in the history detailing the recipients that were not correct.

If none of the email addresses is correct, the email won't be sent, and the action will be reported as failed.

### Reply to field

It will only accept a valid email address.

In case a templating reference is included in any of them, the check will be performed at runtime, when it is resolved.

The email will only be sent if, when populated, the Reply to field email address is correct. If not, the action will be reported as failed.

## Html editor

When Html option is selected from the _Body format_ field, the html code will be properly highlighted.

The editor will also check that the html in the body is correct, showing a descriptive message if not.

![Image 6: Email Action](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/email-action-screen_editor1.png)

An autocomplete feature is available when clicking Ctrl + space.

![Image 7: Email Action](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/email-action-screen_editor2.png)

### Input

```javascript
{
    'From': 'string',
    'FromDescription': 'string',
    'To': 'string',
    'Subject': 'string',
    'Body format': 'string',
    'Body': 'string'
}
```

### Output

```javascript
{
    'Succeeded': boolean,
    'Answer': 'string'
}
```
