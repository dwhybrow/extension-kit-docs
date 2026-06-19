A **System** app is an internal development app created in App Studio (AS). They allow Unit4 developers to create tailored apps for one or many end-users. They are a safe way to ensure that the created app is under Unit4's control, ensuring compliance with development guidelines, maintaining security and providing streamlined support for these custom features.

They can be both **Business screen** and **Standalone** apps that can provide extensions for ERPx/CR functionality, add new windows to enhance the ERPx/CR core or create specific features for customers.

**System apps** are identified in the Dashboard with a Unit4 logo in the top left corner.

![System apps on dashboard](https://docs-external.u4pp.com/extensions-kit/app-studio/images/system-app-dashboard.png)

## System app restrictions

**App Studio** users cannot:

-   Access the **Editor**.
-   Unpublish the app (tenant admin owner only).
-   Export the app.
-   Duplicate the app.
-   Edit the app's **App info** menu entry.

**System** apps can only be edited by **System** tenants, which are exclusively accessible to Unit4 R&D.

## How to activate your System app

To activate your **System** app:

1.  Go to your dashboard.
2.  Go to the **System** app you want to activate.
3.  Open the **Three dots** menu.
4.  Select Publish.
5.  Follow the wizard steps:
    -   Version: Fill in the required fields and see your app URL.
    -   Parameters: Add any parameters required by your app.
    -   Credentials: See all the credentials required by your app.
    -   Flows: See all the flows required by your app. Only **Marketplace** flows can be used in **System** apps.

> Note: The needed flows and credentials must be deployed and enabled in your tenant. If any flows or credentials are missing, contact Unit4.

![Wizard](https://docs-external.u4pp.com/extensions-kit/app-studio/images/system-apps-wizard.png)
