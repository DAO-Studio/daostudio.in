Title: Compose, inspect and improve an application

[Read HTML](https://daostudio.in/yojnai/compose-inspect-and-improve/)

Rights holder: DAO Studio Private Limited

<a id="compose-inspect-and-improve-an-application"></a>

# Compose, inspect and improve an application

Your purchasing assistant has found the agreement and extracted its payment terms, but it is waiting for a delivery date. A reviewer could already check the terms while the customer supplies the date. Why should both wait for the assistant's final answer?

[YojnAI](https://daostudio.in/yojnai/) lets teams participate in that unfinished work, connecting models, tools and checks with intermediate results people can inspect. This hypothetical purchase follows the application design from a source document to a reviewed change.

YojnAI is paused as a product. Delivery and integration remain available through [RawThoughts consulting](https://rawthoughts.in/services/); this guide explains the application model.

<a id="give-each-part-of-the-purchase-a-job"></a>

## Give each part of the purchase a job

An **agent** combines models and tools for one contribution, such as retrieving the agreement or extracting its payment terms. A **playbook** arranges agents and checks into a workflow: retrieve the agreement, extract the terms, check that each term has a source, then prepare the draft once the missing date arrives.

An **application configuration** connects that playbook to the customer's actual agreements, services and permitted access. A reviewer's knowledge can become a check where it is needed, rather than another instruction added to one large prompt. Configuring these apps, checks, tools, agents and models is the **Create** part of YojnAI.

A financial calculation needs the same care: named inputs, operations and conditional branches keep the chosen periods and definitions visible. The [composition account](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/) follows those choices.

<a id="intermediate-work-is-an-integration-surface"></a>

## Continue without repeating completed work

An application that receives only a finished answer has little opportunity to contribute while the work is running. Agent-level callbacks and saved intermediate state give another person or component a place to inspect a result, supply missing context and continue.

In the purchase example, a reviewer could examine the extracted terms while the customer supplied the delivery date. Keeping the completed extraction would avoid running it again just to incorporate that date. The important distinction is between the work already available and the dependency still waiting for an answer.

<a id="add-a-customer-s-date-and-a-reviewer-s-correction-without-redoing-work"></a>

## Add a customer’s date and a reviewer’s correction without redoing work

The customer’s date and the reviewer’s correction should enter without discarding completed work:

| Part of the request | After extraction | Customer supplies a date | Reviewer corrects a term |
| --- | --- | --- | --- |
| Supplier and source | Available | Unchanged | Still useful if the same source applies |
| Payment term | Available, awaiting review | Unchanged | Use the reviewed value |
| Delivery date | Missing | Use the supplied date | Unchanged |
| Purchase draft | Waiting for the date | Ready to assemble | Reconsider the part using the term |
| Order placement | Not performed | Not performed | Not performed |

The date can unblock a draft without repeating extraction. A corrected term can change the draft without losing that date. An older response arriving after the correction must remain an earlier result; using it as the current term could undo the review. The [composition account](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/) develops this example, including concurrent work.

<a id="find-the-step-that-needs-to-change"></a>

## Find the step that needs to change

Suppose the reviewer disputes the payment term. The final answer alone cannot say whether the assistant read the wrong agreement, used an old version or extracted the wrong value. An execution trace connects the run to its steps, inputs, outputs and metadata, giving the reviewer somewhere to look. [Review a disputed answer](https://daostudio.in/yojnai/review-a-disputed-answer/) follows this investigation.

Start the review with the application and version, then the trace and the particular step being judged. A feedback project keeps assessments together, so reviewers can compare a proposed change with its results. Access roles determine who can review; expertise weights determine how their judgments contribute to evaluation. Permission to submit feedback and knowledge of a financial calculation answer different questions.

This assessment and feedback work belongs to **Improve**. An administrator versions the feedback project and starts an improvement job. The team then inspects the result and chooses whether to use it. One-click reversion gives them a way back if the new version proves unsuitable.

<a id="choose-which-version-people-use"></a>

## Choose which version people use

**Deploy** connects an application configuration to customer requests through versions, runs and A/B tests. A correction can inform a candidate version while people continue using the current one. The team can evaluate the change before choosing it.

Several versions of one configuration count as one service instance. Changing a model or check does not itself create another instance.

<a id="know-where-the-agreement-and-feedback-go"></a>

## Know where the agreement and feedback go

The purchasing team also needs to know who may read the agreement and which services receive it. **Comply** organises users, projects and objectives around access and the exchange of personal information. Partner applications keep their own owners.

**Important**

**Map the whole deployment.** Customer-side integrations and databases connected to gateways, services and caches hosted by DAO Studio. Installing the integration on the customer’s infrastructure did not keep every request, trace or piece of feedback there. [Follow the data, not the deployment label](https://daostudio.in/blog/follow-the-data/) explains the different paths.

The people who know the operation remain essential. They can identify an exception, correct a source or explain why a plausible answer is unsuitable. Composition gives that knowledge a useful place: a source, a check, a reviewed interpretation or a changed workflow. [The organisation around the AI](https://daostudio.in/blog/the-organisation-around-the-ai/) explores how those contributions fit the team's work.


Reading path: [YojnAI](https://daostudio.in/yojnai/) > [Compose, inspect and improve an application](https://daostudio.in/yojnai/compose-inspect-and-improve/)
