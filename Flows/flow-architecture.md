# Architecture

The Unit4 Extension Kit (U4EK) utilizes a Microservices event-based [Orchestration saga](https://docs-external.u4pp.com/extensions-kit/glossary/orchestrator/) architecture. Internal communication and synchronization between services are based on events, allowing the components of U4EK to communicate in a close to real-time manner. By decoupling the individual components of U4EK, a high resilience to failure is achieved, as the sending of events is not affected by the availability of the receiver of those events. Event-based communication together with stateless components enables automatic load balancing when individual components are scaled-out under high workload peaks.

The U4EK works with [Unit4 Identity Services](https://docs-external.u4pp.com/identity-services) (U4IDS) to ensure secure access and communications between components. When deployed, U4EK provisions itself against U4IDS, Unit4 Access Management and [Unit4 Message Hub](https://docs-external.u4pp.com/extensions-kit/glossary/message-hub/). New components ([Triggers](https://docs-external.u4pp.com/extensions-kit/glossary/trigger/) and [Actions](https://docs-external.u4pp.com/extensions-kit/glossary/action/)) can be added at runtime, so U4EK can be extended with zero downtime. When a new component is added to U4EK, it is provisioned automatically so it can start communicating with other components without human intervention.

![Image 3: Home page](https://docs-external.u4pp.com/extensions-kit/images/architecture/application-overview.png)

The U4EK can be reached from external services through the [HTTP Webhook Trigger](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/http-webhook-v2/). This is the only public endpoint of U4EK and only accepts calls that contains one of the keys generated for the [Flows](https://docs-external.u4pp.com/extensions-kit/glossary/flow/). This Trigger enables U4EK to ingest data from external services (like Logic Apps, IFTTT or any other service that can perform an HTTP Request) and perform the defined actions in the corresponding Flow inside Unit4 eco-system.

## Infrastructure

As a cloud-native product, U4EK leverage Azure PaaS to achieve high performance, consistency, and monitoring to ensure every Flow is executed when it has to.
