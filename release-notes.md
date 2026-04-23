# Release Notes — Extension Kit

> Source: https://docs-external.u4pp.com/extensions-kit/release-notes-external/

## v251.8.1

### Improvements

- **Extension Kit:** Internal technical improvements.

---

## v251.8.0

### New Features

- **Extension Kit:** Clone and Export flow options available from the Three dots menu on the Flow card.
- **App Studio:** New Import app button allows users to import apps directly from the dashboard.

### Improvements

- **Extension Kit:** Flow history maintains position when navigating between windows.
- **Extension Kit:** New Flow description field when creating a flow.
- **Extension Kit:** Users are now alerted when an error occurs with the orchestrator during flow triggering.
- **App Studio:** Reset action now allows users to select which components and resources to reset.

### Fixes

- **Extension Kit:** Static IP configuration no longer missing from flow configuration in flow history.
- **Extension Kit:** Flows containing Generate JWT or PGP Decrypt actions can be imported without errors.
- **Extension Kit:** Validation added to prevent saving flows with invalid Scheduled event trigger configurations.
- **Extension Kit:** Flow activation improved for flows with a large number of parameters.
- **Extension Kit:** Calculating the absolute value of large negative numbers no longer results in errors.
- **App Studio:** ERPx API resource no longer returns empty responses after making requests.

### Known Issues

- **App Studio:** Reset action does not reset Combobox and Dropdown components as expected when there is no empty option or default value set.
  - **Workaround:** Create an empty Plain object resource (e.g. `[{"customerId":"","customerName":""}]`) and reference it in the component Options field using `{{res1.customers | concat:res2}}`.

---

## v251.7.0

### New Features

- **Extension Kit:** New Monitoring tab for high-level visibility into flow health, insights, and control (early version, non-production only).
- **Extension Kit:** New Dual SFTP authentication method (early version, non-production only).
- **App Studio:** New Drawing area component to enable users to draw and attach sketches in apps.

### Improvements

- **Extension Kit:** Enhanced Multi-criteria flow filter UI.
- **Extension Kit:** All newly created flows are saved as inactive by default.
- **Extension Kit:** Deprecated Templating V1 removed from Extension Kit Portal.
- **App Studio:** Maximum number of flows that can be triggered per app increased from five to ten.

### Fixes

- **Extension Kit:** Flows now handle large numbers without failing.
- **Extension Kit:** Liquid loop iteration limit can no longer be bypassed using nested loops.
- **Extension Kit:** Saving a cloned webhook flow in a disabled state no longer logs a 404 error.
- **Extension Kit:** Flow status cannot be changed when cloning a flow.
- **Extension Kit:** PGP Decrypt action now prevents private keys from appearing in logs.
- **App Studio:** App Studio windows appearing blank in ERP due to 404 error is fixed.
- **App Studio:** Toast notification disappears as expected when clicking Close (X).
- **App Studio:** File viewer component no longer breaks application preview on incorrect file format.
- **App Studio:** Help section no longer returns an error.
- **App Studio:** Edges between nodes in Logic flow can now be removed as expected.
- **App Studio:** Publish status now refreshes correctly in the View all versions modal.

---

## v251.6.2

### Hotfix

- **Extension Kit:** Reverted SSH.NET library upgrade to resolve compatibility issue with legacy SFTP configurations.

---

## v251.6.1

### Hotfix

- **App Studio:** Fixed crash when importing an app into the canvas in some cases.
- **App Studio:** Importing metadata without query parameters no longer crashes App Studio.
- **App Studio:** Fixed bundler error when the same HTTP resource was used in different Data grid components.

---

## v251.6.0

### New Features

- **App Studio:** New Dynamic calculation property for Data grid columns (Ripple).
- **App Studio:** New Set app as saved switch in HTTP request and Trigger flow actions.
- **App Studio:** New Query parameters panel to pass data to the app when opened.
- **App Studio:** New ERP CR API resource (not yet available).
- **App Studio:** New File viewer component (Ripple).

### Improvements

- **App Studio:** New Min length, Min and Max properties for certain Text input types.
- **App Studio:** New Vertical gap property in the Container component.

### Fixes

- **App Studio:** On update action on Text input now only triggers when the component loses focus.
- **App Studio:** Content property no longer corrupted when removing files from File uploader.
- **App Studio:** Table and Data grid components now handle numeric values in string format correctly.
- **App Studio:** Close (x) button in Error toast now works as expected.

---

## v251.5.0

### Improvements

- **Extension Kit:** Flow names now only allow letters, numbers, spaces, dashes, underscores, periods, brackets, square brackets and ampersands.
- **Extension Kit:** Root folder path property removed from SFTP connections configuration.
- **Extension Kit:** Log limits increased to 10K in the Run code action.
- **Extension Kit:** Actions renamed to reflect new branding:
  - Digital assistant question → **Unit4 Ava question**
  - Digital assistant push text → **Unit4 Ava push text**

### Fixes

- **Extension Kit:** Tenant ID is now empty when exporting a flow with an App result action; correct Tenant ID assigned automatically on import.
- **Extension Kit:** Blocked users with Owner role no longer receive failing flow notifications.
- **Extension Kit:** Emails no longer sent when a flow ends with a warning.
- **Extension Kit:** Error 500 no longer appears when importing a Marketplace flow.
- **Extension Kit:** Newly created certificates now show Issuer data correctly.
- **Extension Kit:** Slash symbol (/) used as escape character in Webhook trigger JSON Body alters the payload. Workaround available in documentation.

---

## v251.4.0

### New Features

- **App Studio:** New If logic control in the Logic drawer.

### Improvements

- **App Studio:** Data grid has two new properties: Disable adding rows and Disable deleting rows.
- **App Studio:** Reset action now clears all files in the File uploader component.
- **App Studio:** Selection mode property of Data grid is now independent of the Allow editing property.
- **App Studio:** New Min and Max properties for Date, Month, Time, Datetime-local, and Number Text input types.
- **App Studio:** Text component now always selectable in the Canvas even if Text property is temporarily empty.

### Fixes

- **Extension Kit:** Forget me function no longer incorrectly deletes invitations for all tenants related to the user's email.
- **App Studio:** File uploader templating now displays correctly in the Templating drop-down.
- **App Studio:** Plus (+) button to add rows to Data grid is now disabled when filter is active in Business screen apps.
- **App Studio:** Interaction rules in Checkbox or Switch components with a Default value now work on app launch.
- **App Studio:** App Studio no longer crashes when invalid value entered in Value field or Display field of Combobox, Dropdown or Radio components.
- **App Studio:** Transition animation drop-down appears again in the Change screen action (U4Components).

---

## v251.3.0

### Improvements

- **Extension Kit:** New limits for the Run code action.

### Fixes

- **Extension Kit:** Databricks now work as expected.

---

## v251.2.2

### Hotfix

- **Extension Kit:** Custom properties no longer override basic properties in the Message Hub event action.

---

## v251.2.1

### Hotfix

- **App Studio:** Value list Data type property in Data grid Column now behaves like a Combobox component.
- **App Studio:** Fixed inability to edit string data used as input in a Number Data type Column in Data grid (Ripple).

---

## v251.2.0

### New Features

- **Extension Kit:** Automatic step renumbering when rearranging actions. Enable via the Automatic step renumbering toggle in the Overview section.
- **Extension Kit:** New Multi-criteria flow filter to refine flow searches.
- **Extension Kit:** New Tags property to organise flows in the Overview section.
- **App Studio:** Release of the Unit4 Ripple design system. New apps use Ripple; existing U4 component apps remain editable.
- **App Studio:** Two new column properties in the Container component (Ripple): Align and Distribute.

### Improvements

- **Extension Kit:** Flows can now be sorted by status: Enabled or Disabled.
- **Extension Kit:** Warnings issued in Flow history when flow memory limits are exceeded.
- **App Studio:** Download file property of HTTP Request action now supported for ERPx API resources.
- **App Studio:** Apps using both Ripple and U4 Components can now be distributed to all tenants.
- **App Studio:** Improved ERPx CSS style for Business screen apps.

### Fixes

- **Extension Kit:** Stop button now visible even when flow history is not loaded.
- **Extension Kit:** Name field in Message Hub event trigger is now read-only for reader role.
- **Extension Kit:** SFTP connections now filtered by Connection name or Host address server.
- **App Studio:** Visual indicator added in components when using keyboard navigation in Business screen apps.
- **App Studio:** Expandable button removed from Maximum total size (MB) field in File uploader (was causing crashes).

---

## v251.1.0

### New Features

- **App Studio:** New Grant type property for Bearer credentials.

### Improvements

- **App Studio:** Table U4Component has two new properties: Disable adding rows and Disable deleting rows.
- **App Studio:** Loading spinner added to Preview button in Main toolbar.
- **App Studio:** Improved filters for app search in the Dashboard.
- **App Studio:** File uploader validation added in the Stepper component.
- **App Studio:** Table component now treats loss of cell focus as end of editing.

### Fixes

- **App Studio:** Errors now triggered when typing wrong format while editing credentials.
- **App Studio:** Dropdown and Combobox components crash fixed when retrieving a list with integers and numbers.
- **App Studio:** Default value set in Dropdown component now loads correctly every time in the end-user app.
- **App Studio:** System titles now render when APPSTUDIO_TITLES feature flag is disabled.
- **App Studio:** Additional validations now work in File uploader component.
- **App Studio:** Component ID now updates correctly in all resource properties.

---

## v251.0.1

### Hotfix

- **Extension Kit:** Root path folder in SFTP actions disabled as it interferes with existing flows.

---

## v251.0.0

### New Features

- **Extension Kit:** New Clone button to copy an existing action while creating a flow.
- **Extension Kit:** New Multipart content type added to Webhook trigger.
- **App Studio:** Ripple design system released for new apps.
- **App Studio:** New Download file property for HTTP Request action.

### Improvements

- **Extension Kit:** New logic in Message Hub trigger so messages are not marked complete until fully processed.
- **Extension Kit:** Warnings shown when step references are not correct within a flow.
- **App Studio:** New validation system for dependent flows in System apps activation.
- **App Studio:** App Studio now supports both ERPx Classic and Core APIs collections.
- **App Studio:** Panel with tabs has two new properties: Hidden and Disabled.
- **App Studio:** File uploader now shows an error message when file format is not supported.

### Fixes

- **Extension Kit:** Users with Reader role can now see who last modified the flow.
- **Extension Kit:** Application/octet-stream and application/xml options now available in multipart/form-data content type selection.
- **Extension Kit:** SFTP list action now correctly combines root folder path with Folder path in the action.
- **Extension Kit:** Webhook trigger flows no longer crash with more than 1600 lines of text.
- **App Studio:** Various canvas, logic flow, and publishing fixes.

---

## v244.1.0

### Improvements

- **Extension Kit:** Various internal technical enhancements.

---

## v244.0.3

### Hotfix

- **App Studio:** Missing endpoints in ERPx API resource now displayed correctly.
- **App Studio:** Reset action in ERPx rendered apps no longer causes ERPx windows to freeze.

---

## v244.0.2

### Hotfix

- **Extension Kit:** Flow history service improved by optimising assigned resources for performance.

---

## v244.0.1

### Hotfix

- **Extension Kit:** Hibernation service and Pause action improved to support large request bodies.

---

## v244.0.0

### New Features

- **App Studio:** System apps now available for Unit4 to deliver new screens or standalone apps extending ERPx core functionality.

### Improvements

- **App Studio:** Time Datatype added for columns in the Table component.
- **App Studio:** Improved size and colour of label and description in the Range slider component.
- **App Studio:** Users now notified of missing credentials when importing an app.
- **App Studio:** Various minor internal technical and security improvements.

---

## v242.4.0

### Fixes

- **Extension Kit:** Parameters with Sensitive data enabled that contain an empty value can now be saved.
- **Extension Kit:** Updating a certificate with a non-existent ID now correctly returns 404 Not Found.
- **Extension Kit:** Redis upgraded to higher reliability tier.
- **Extension Kit:** Mechanism for detecting trigger configuration changes fixed to prevent unnecessary webhook address regeneration.
- **Extension Kit:** Custom domain address now created correctly when creating a new flow with custom domain activated.

---

## v242.3.0

### Improvements

- **Extension Kit:** Optional Key ID for subkey selection field added to PGP Encrypt action.

### Fixes

- **Extension Kit:** Marketplace flow details can now be correctly viewed when opened from the Metrics window.
- **Extension Kit:** Users without a specified tenant are now automatically logged into the admin tenant.
- **Extension Kit:** Flows with an App trigger that are exported or cloned now correctly send necessary data to App Studio apps.

---

## v242.2.0

### Improvements

- **Extension Kit:** HTTP Request action now supports built-in gzip and Deflate compression/decompression.
- **Extension Kit:** Metrics window redesigned with more detailed flow and action usage data.
- **Extension Kit:** SFTP connections now use SSH.NET version 2024.1.0, supporting 4096-bit SSH key encryption with passphrase.
- **Extension Kit:** Scriban templating engine updated to version 5.10.0; more Liquid functions now supported.
- **Extension Kit:** Various UI, usability, and security enhancements.

### Fixes

- **Extension Kit:** Liquid functions can now convert a range type to an array.
- **Extension Kit:** 403 Forbidden correctly returned when user with insufficient rights attempts to modify a flow.
- **Extension Kit:** Various flow saving and execution edge case fixes.

---

## v242.1.0

### Improvements

- **Extension Kit:** Maximum parameter length increased from 1,024 to 10,000 characters.
- **Extension Kit:** Sensitive parameters now stored in Unit4 Tenant Management System (U4TMS).
- **Extension Kit:** Checkpointing applied to all actions to avoid duplicated flow runs.
- **Extension Kit:** Filters for flow history added (flow run ID, initial date, end date).
- **Extension Kit:** Session expiry pop-up added.
- **Extension Kit:** Internal improvements to Message Hub Event trigger and garbage collection.

---

## v242.0.0

### New Features

- **App Studio:** New Drawing area U4 component for end-users to make drawings and attach them.

### Improvements

- **App Studio:** Component ID property now non-case sensitive.
- **App Studio:** Templating enabled as data source in the Table component.
- **App Studio:** Link component updated to allow only secure addresses (https).

---

## v241.3.0

### Improvements

- **Extension Kit:** Run Code action now includes cryptography support.
- **Extension Kit:** Libraries updated to address potential security vulnerabilities.
- **Extension Kit:** Message Hub Event action failure handling improved with new retry mechanism.

---

## v241.2.0

### New Features

- **App Studio:** App Studio now included in Extension Kit's Admin tenant.

### Improvements

- **App Studio:** Reader role now allows users to see app details.

### Fixes

- **Extension Kit:** Tenant ID of an existing tenant can no longer be changed (now read-only).
- **Extension Kit:** Saving a disabled WebHook flow no longer results in 404 Not Found.

---

## v241.1.0

### New Features

- **Extension Kit:** Basic authentication can now be modified for the Webhook trigger when enabling a flow.
- **Extension Kit:** Retry policy for HTTP requests can now be disabled.

### Improvements

- **Extension Kit:** Flow history optimised for high workload scenarios.
- **Extension Kit:** Security enhancements.

---

## v241.0.0

### New Features

- **App Studio:** Parameters can now be used in the Credentials section.
- **App Studio:** New Value list data type in the Table component for select drop-downs in columns.

### Improvements

- **App Studio:** Flow resources now supported on Business screen apps published in ERPx.
- **App Studio:** Change screen, Field validation and Reset actions now available in Logic flow.

---

## v234.2.0

### New Features

- **Extension Kit:** New beta AI flow assistant for configuring individual flows (preview environments only).

---

## v234.1.0

### New Features

- **Extension Kit:** Static IP address now available as an optional feature for IP address firewall filtering and whitelisting.

### Improvements

- **Extension Kit:** Full input/output messages can now be displayed in flow history.
- **Extension Kit:** Maximum parameter length increased from 1,024 to 2,048 characters.
- **Extension Kit:** PGP Decrypt action now supports pgptool.org key generator.
- **Extension Kit:** PGP Encrypt action improvements including new Encrypt and sign in one pass option.

---

## v234.0.0

### New Features

- **Extension Kit:** New beta AI copilot tool for configuring individual actions (preview environments only).
- **App Studio:** New On finish event for the Wizard component.
- **App Studio:** New On update event to trigger actions after user tabs out of a field.
- **App Studio:** New Notification panel in Canvas toolbar for errors and warnings.

### Improvements

- **App Studio:** File uploader component improvements including Base64 file sending and file selection by name/contentType/content.
- **App Studio:** ERPx API resource can now generate a Content type body sample.
- **App Studio:** Dashboard now loads 20 apps at a time.
- **App Studio:** New Layout panel, collapsible panels, component search, and improved drag and drop.
- **App Studio:** Accessibility improvements for screen reader users (JAWS 2023 and NVDA 2023).

---

## v233.3.0

### New Features

- **Extension Kit:** New Compress and Decompress files actions.

### Improvements

- **Extension Kit:** Deprecated public API endpoints removed.
- **Extension Kit:** PGP Decrypt action improvements for signature handling and multi-key keyrings.

---

## v233.2.1

### New Features

- **Extension Kit:** Stop run flow added to allow users to stop misconfigured flows.
- **Extension Kit:** Flow activation with SFTP connections and certificates added.
- **App Studio:** Flow resource and Trigger flow actions added for integration between apps and Extension Kit flows (up to 5 Trigger flow actions per app).
- **App Studio:** New Change screen action added to Button and Icon button components.

### Improvements

- **Extension Kit:** Optimization of flow memory — Lazy Liquid concept introduced for significantly improved memory performance.
- **Extension Kit:** Logging improvements for easier troubleshooting.

---

## v233.0.0

> From v233.0.0 onwards, App Studio release information is merged with Extension Kit release notes.

### New Features

- **App Studio:** New File uploader component.
- **App Studio:** New Range slider component.
- **App Studio:** Extension Kit parameters now supported in component properties.
- **App Studio:** Multi-screen apps now supported (up to 5 screens).
- **App Studio:** Versioning now supported (save drafts, publish, import/export versions).

### Improvements

- **Extension Kit:** Passwords and sensitive fields now copied when cloning a flow.
- **App Studio:** Various dashboard, canvas, and resource enhancements.

---

## v232.4.0

### New Features

- **Extension Kit:** SFTP connection API endpoints published in Public API.

---

## v232.3.0

### New Features

- **Extension Kit:** New Run button for all triggers to allow manual flow triggering.
- **Extension Kit:** New Run code action for executing JavaScript scripts in a flow.
- **Extension Kit:** New Until action for iterating through a list of actions.
- **Extension Kit:** New Flat File to JSON action for parsing CSV and fixed-width flat files to JSON.

### Deprecated

- Templating V1 will be deprecated from October 1st 2023. Migrate to Templating V2.

---

## v232.0.0

### Breaking Changes

- Rate limiting enabled by default: maximum 10,000 actions per flow in 5 minutes. Exceeding the limit disables the flow (re-enable after 1 minute). Does not apply to Marketplace flows.

### New Features

- **Extension Kit:** New Continue on error setting for actions.
- **Extension Kit:** New Mapping Tables window with import, export and delete support.
- **Extension Kit:** New Generate JWT Token action.

### Improvements

- **Extension Kit:** New Zip and Unzip Liquid functions via Execute Templating Script.
- **Extension Kit:** PGP keys for signing added to PGP Encrypt and PGP Decrypt actions.
- **Extension Kit:** AES-256 cipher algorithm support added to PGP Encrypt.

---

## v231.0.0

### New Features

- **Extension Kit:** New Pause action to stop flow execution for a specified time.
- **Extension Kit:** Filters and conditions enhanced with OR operator, NOT operator, and grouping.

---

## v2022.12.08

### New Features

- **Extension Kit:** New XML Encrypt action.
- **Extension Kit:** New XML Decrypt action.

### Improvements

- Added support for .pem format certificates.
- Added support for nested loops in ForEach action.
- Added support for detached signature type in XML Sign and XML Verify.

---

## v2022.11.07

### Improvements

- Added support for mutual TLS authentication (mTLS) for Webhook (v2) trigger.

---

## v2022.09.30

### Improvements

- PGP Encrypt and PGP Decrypt actions now support both RSA and PGP keys.

---

## v2022.09.12

### New Features

- **Extension Kit:** Multitenant flows service — predefined flows available in a catalogue for ERPx tenants.
- **Extension Kit:** New XSLT3 Transformation action.
- **Extension Kit:** Mapping tables functionality added.

---

## v2022.05.12

### New Features

- **Extension Kit:** New XML Sign action.
- **Extension Kit:** New XML Verify action.
- **Extension Kit:** New PGP Encrypt action (preview).
- **Extension Kit:** New PGP Decrypt action (preview).

---

## v2022.02.16

### New Features

- **Extension Kit:** Export as an App option added.
- **Extension Kit:** Simplified import/export using a single file for flow and parameters definition. ⚠️ Breaking change.
- **Extension Kit:** New JSON to XML action.
- **Extension Kit:** Extension Kit registered in Discovery Service.

---

## v2021.11.25

### New Features

- **Extension Kit:** New SFTP actions (preview): Create file, Delete file, List directory, Get file content.
- **Extension Kit:** New XSLT Transformation action.
- **Extension Kit:** HTTP request action now accepts multipart/form data.

---

## v2021.07.14

### New Features

- **Extension Kit:** HTTP Request action now supports certificates.
- **Extension Kit:** Clean history functionality added.
- **Extension Kit:** Sensitive flows introduced — hides flow history for marked flows.

---

## v2021.06.02

### New Features

- **Extension Kit:** Marketplace flows introduced.
- **Extension Kit:** Discoverable endpoints added to Templating v2.0.

---

## v2021.5.7

### New Features

- **Extension Kit:** New Execute Templating action for independent scripting logic (requires Templating v2.0).

---

## v2021.3.4

### Improvements

- Flow history data older than three months archived; data older than six months deleted.
- Webhook (v1) trigger deprecated — migrate to Webhook (v2).

---

## v2020.10.8

### New Features

- **Extension Kit:** Flows import and export via portal.
- **Extension Kit:** Additional templating options added (experimental).
- **Extension Kit:** Webhook v2 allows customising the verb in secondary response configuration. ⚠️ Breaking change.

---

## v2020.02.19

### New Features

- **Extension Kit:** New For Each action.
- **Extension Kit:** New XML Parse action.
- **Extension Kit:** Alert emails for failed flows sent to tenant owners.

---

## v2020.03.03

### New Features

- **Extension Kit:** New Event Grid Publish action.
