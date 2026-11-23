Title: Follow the data, not the deployment label

[Read HTML](https://daostudio.in/blog/follow-the-data/)

Author: Harsh Joshi

<a id="follow-the-data-not-the-deployment-label"></a>

# Follow the data, not the deployment label

The customer has installed the application on their own machine. They ask it a question about a document stored there, receive an answer and later send a correction. Where did the document go? Where is the correction now? If they stop the application, which parts of that exchange remain elsewhere?

The installation answers only part of those questions. It can keep retrieval close to the customer's records while sending prepared context to a provider's gateway, using another organisation's model and retaining a trace in a separate store. Those connections are the service the customer has chosen to depend on. Following them gives “self-hosted” a more useful meaning than either a promise that everything stayed local or a reason to discount the control the local component really provides.

[YojnAI](https://daostudio.in/yojnai/)'s operating model makes this distinction concrete. Customer-side instances and databases were intended to connect to services and caches hosted by DAO Studio. Create, Deploy, Improve and Comply described different responsibilities: configure the composition, serve its requests, prepare improvements from feedback, and govern access or personal-information exchange. Their relationship determined the application the customer would actually operate.

<a id="a-local-model-is-one-part-of-the-system"></a>

## A local model is one part of the system

In YojnAI’s pilots in investment banking, operations and the CFO office, I adapted a 4-bit Mistral 7B model through reinforcement learning from human feedback: MMLU comparable to GPT-3.5, BigBench above 70%, and self-hosting at about $1.75 an hour. Those are the results I reported at the time. The hourly figure is not the cost of delivering and supporting the whole application.

The February 2024 operating design made the split explicit. The customer’s infrastructure held the application, integration, model instances and trace, user and document databases. YOJN hosted gateways, microservices and stores for configuration, feedback and metrics. Installing the model beside the customer’s documents therefore left other parts of the operation crossing that boundary. A self-hosted model and a wholly local service were different arrangements in the studio’s own design.

<a id="where-each-thing-goes"></a>

## Where each thing goes

Following that exchange means distinguishing the source document from the context prepared for a model, and both from the [execution record](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/). The source can remain in the customer's system while a selected passage travels in a request. The trace might retain the passage, a source identifier or only the result; each choice changes what can later be investigated and what information remains outside the customer's machine. Feedback then creates another record with its own destination and use. One exchange has produced several continuing relationships, even if the customer saw a single answer.

An illustrative hybrid deployment makes the questions easier to locate.

| Object | Example path | What the customer needs to know |
| --- | --- | --- |
| Source document | Customer store → customer-side retrieval | Which component can read the original? |
| Prepared context | Retrieval → hosted gateway → selected model provider | Which passages leave the local environment? |
| Model result | Provider → application | Where is it retained and attached to the request? |
| Diagnostic trace | Selected steps → diagnostic store | Does it contain passages, identifiers or only operational metadata? |
| Reviewer correction | Review screen → feedback project | Which application and permitted improvement purpose does it serve? |

Moving the model changes one row of this map; it does not automatically move the diagnostic or feedback stores. A box labelled “cloud” or “on-premise” is too broad to show the customer which dependencies remain. Each transfer and continuing record needs its own destination and purpose.

<a id="creation-deployment-improvement-and-compliance-are-separate-jobs"></a>

## Creation, deployment, improvement and compliance are separate jobs

Creation is the work of preparing [the composition](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/) and its connections. Deployment makes a selected arrangement available for requests. Improvement examines feedback and prepares changes. Compliance concerns the conditions under which information and access are handled.

Those roles can be served through different components and by different people. In YojnAI’s operating design, creation began as consulting and deployment as installation services; broader self-service was a proposed extension. A configuration screen did not remove the work of understanding the source or adapting the workflow, and a local deployment could still depend on the provider's improvement process. The [customer's own people](https://daostudio.in/blog/the-organisation-around-the-ai/) also need a way to keep their knowledge current and correct a mismatch in use. Describing that continuing relationship gives the customer a more useful choice than treating the location of installation as a promise of independence.

<a id="who-runs-it-and-who-owns-it"></a>

## Who runs it, and who owns it

A customer can administer infrastructure while the application includes platform code, a partner-owned configuration and a third-party model. The ability to stop a process or copy a file concerns technical control; the rights in those components follow their own arrangements. Receiving a trace similarly gives the provider information without making its contents unrestricted platform material.

DAO Studio's platform and partner-product distinction made this an actual commercial boundary. The platform could be reused while the partner's application and records remained with their owner. Keeping that distinction through the deployment arrangement makes both kinds of control intelligible: who can operate the system and which components or records each party may use for another purpose.

<a id="diagnostics-is-a-use-not-merely-a-by-product"></a>

## Diagnostics is a use, not merely a by-product

An execution record can help diagnose a failure, understand cost or improve the platform, while containing information the customer never intended to contribute to a general training corpus. Retaining it therefore creates a relationship around its use, not merely a technical by-product of serving the request. The customer needs to understand which diagnostic information the provider requires, why it is retained and whether improvement means repairing this application or using the material elsewhere. Those questions make the agreed purpose specific enough to shape the handling path.

YojnAI's terms distinguished consent-bound diagnostic and improvement use. That agreement and its technical enforcement have different roles: the agreement defines the permitted purpose, while the actual handling path must implement it. A diagnostic record can help a provider repair the application without becoming unrestricted material for another use. The customer needs a way to understand that purpose and exercise the control the arrangement promises.

<a id="the-exit-is-part-of-the-choice"></a>

## The exit is part of the choice

A customer deciding to depend on a system needs an account of what happens if the relationship changes. Retaining the configuration, exporting records, replacing a hosted gateway and restoring an earlier version each depend on a different part of the arrangement. Model and tool licences may constrain the next environment even when the customer holds a local copy. Recovery requires the selected version, its dependencies and the customer's own state to fit together; an installer completing successfully establishes only one part of that work.

A provider may offer something the customer reasonably wants to depend on. A hosted service can make the operation easier to maintain, while a local component gives the customer control over another part. The meaningful promise is an arrangement they can understand, operate and leave on known terms. Deployment location contributes to that choice alongside the purpose of transfers, the rights in the components and a workable exit.
