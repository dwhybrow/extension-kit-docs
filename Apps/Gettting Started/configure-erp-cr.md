## How to activate App Studio for a new ERP CR tenant

Here is a quick guide to activate Unit4 App Studio (AS) for an ERP CR tenant.

## Prerequisites

Before activating App Studio for a new ERP CR tenant, ensure the following requirements are met:

-   **IDS authentication**: Unit4 Identity Services (U4IDS) login must be enabled for the ERP CR tenant.
-   **Extension Kit (U4EK) availability**: Extension Kit must be available for the target tenant.
-   **Common Parameters configuration**: The ERP CR instance must have the following variables configured in the **Common parameters (TAG023)** window:
-   `DISCO_URI`: The Discovery Service URI for the environment.
-   `IDS_AUTHORITY`: The U4IDS authority URL for authentication.

## Activation

Follow these steps to activate App Studio for a new ERP CR tenant:

### 1\. Request App Studio activation

If App Studio is not yet activated for your ERP CR tenant, contact your system administrator to request activation.

### 2\. Configure the created client in ERP CR

To configure the client in ERP CR:

-   Go to **System administration > System setup > Web service accounts (TAG200)**
-   Add the client by selecting the **Add** button, and fill in the fields as shown in the table:

|Field|Description|
|---|---|
|Authorization type|Select _OAuth 2.0 Client Credentials Flow_ from the dropdown.|
|Name|_IdsImpersonationServiceAccount_|
|ID|_app-studio-u4bw-user-impersonation_|
|Description|_App Studio user impersonation client_|
|Secret|Enter the secret provided for your tenant.|

### 3\. Verify App Studio accessibility

To confirm accessibility:

-   Check that Extension Kit is available in the relevant environment or tenant within Disco.
-   If Extension Kit is missing, AS will not be accessible.

> ❗Important: ERP CR users who want to use AS must always log in through IDS.
