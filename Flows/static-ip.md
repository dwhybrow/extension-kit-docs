# Static IP address

> Note: A static IP address is a premium add-on feature available for an additional subscription cost. Please contact your Unit4 account manager for pricing information.

A static IP address can be requested for a tenant as an optional feature from Unit4 Cloud Services to provide a trusted, static IP address. Static IP addresses are enabled per tenant and are applicable for flows that use the **HTTP Request** and **SFTP** actions.

When the static IP feature is enabled for a tenant, a static IP addess is automatically assigned and the _Static IP_ setting is available in the **Configuration** section of the flow overview. This static IP address will not change and can be used in firewall filtering and whitelists etc.

![Image 3: Static IP setting](https://docs-external.u4pp.com/extensions-kit/images/portal/static-ip1.png)

> Note:
> 
> 
> *   Static IP addresses are only relevant for actions that require an IP address, such as the **HTTP Request** and **SFTP** actions.
> *   Static IP addresses are not permitted in marketplace flows.
> *   Importing and exporting a flow with a static IP, deactivates the _Static IP_ setting.
