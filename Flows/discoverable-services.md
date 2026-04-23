# Discoverable Services

[Templating](https://docs-external.u4pp.com/extensions-kit/guides/portal/templating/) allows to easily use other Unit4 services' endpoints by exposing different variables:

*   u4erp webapi url
*   u4ids authority url
*   u4bw webapi url
*   u4bw soap url

These variables will be available if the services are registered in the [Unit4 Discovery Service](https://docs-external.u4pp.com/extensions-kit/glossary/discovery-service/) for the specific Tenant the flow belongs to, otherwise the variable will resolve to an empty value.

To use them, access the variables through the "+" sign in templating fields.

![Image 3: discoverable endpoints](https://docs-external.u4pp.com/extensions-kit/images/portal/discoverable-endpoints.png)
