Title: Reuse a capability

[Read HTML](https://daostudio.in/daonet/reuse-a-capability/)

Rights holder: DAO Studio Private Limited

<a id="reuse-a-capability"></a>

# Reuse a capability

Another team has an invoice-extraction workflow you would like to use. It returns supplier fields and payment terms, with their locations in the document. Your application could use those results to prepare a payment for review. What must travel with the workflow for you to rely on it?

[DAOnet](https://daostudio.in/daonet/) connects discovery and reuse with execution, continuing memory and a shared account of the exchange. It is paused and remains a protocol design; this worked example explains the exchange rather than a running marketplace. Scope for any work on it is agreed through [RawThoughts consulting](https://rawthoughts.in/services/) (on RawThoughts).

<a id="find-out-what-the-workflow-returns"></a>

## Find out what the workflow returns

Suppose an invoice says “payment due 30 days after delivery” but gives no delivery date. The workflow should return the term and its location while leaving the due date unresolved. Your application can then ask for the delivery date. A guessed date would conceal the information the reviewer still needs.

Before adopting [such a capability](https://daostudio.in/collections/protocols-and-reuse/some-things-never-change/), the receiving team needs to understand which documents it supports, what it returns and what must be supplied by the application.

**Important**

**Check both permissions.** The workflow's licence governs reuse of the contribution. Permission to process the customer's invoices is a separate requirement.

Extraction supplies information for payment review; it does not approve or execute the payment.

<a id="follow-a-version-into-the-receiving-application"></a>

## Follow a version into the receiving application

Compare two hypothetical versions against the same invoice:

| Version | Returned result | Consequence for payment review |
| --- | --- | --- |
| A | The payment term, its document location and an unresolved due date | The reviewer can inspect the term and request the delivery date. |
| B | A proposed date without the supporting term or location | The reviewer cannot check where the date came from using this result. |

Version B could support more invoice layouts and still break this application's review. The team could keep A while its dependencies remain available, or return the invoice for manual handling. “Latest” does not tell a consumer whether a change is suitable.

To investigate a later problem, both teams need to identify the version used, the invoice and the returned output. That lets them distinguish an unsupported document from a changed result or an error in the receiving application. Versioning makes those dependencies visible as the capability travels beyond its first use.

<a id="let-use-improve-the-next-contribution"></a>

## Let use improve the next contribution

Reusing the workflow can also help improve it. In the design, a coordinating agent called CEO GPT arranges agents that use intelligences, the capabilities agents draw on, and playbooks from the marketplace. Their traces pass through DAOnet to ExpertGPT, the design’s name for the human-feedback service, which informs the next intelligences and playbooks offered for reuse.

In the invoice example, repeated confusion between a payment term and a delivery date could become a case for review. A reviewer could identify the distinction, help improve the extraction capability or its playbook, and make a revised version available to the next application. The version comparison still matters: receiving an improvement does not mean accepting it blindly.

The same traces connect use with credit for the contributors, although the calculation of credit and payment remains open. Recording a trace cannot itself improve a model or determine what somebody is owed; review and evaluation still have work to do.

<a id="after-discovery-execution-memory-and-observability"></a>

## After discovery: execution, memory and observability

Finding the workflow is only the start. Configuration connects it to your application; **execution** runs the chosen operation, such as extracting invoice terms. **Memory** keeps the invoice and its context connected across requests, so a later delivery date meets the right term.

Both teams also need to examine an attempt and its result. If the connection fails, did the request leave your application, did the workflow run, and did its answer return? **Observability** makes those events available to investigate.

DAOnet includes a ledger and smart-contract layer for shared transaction arrangements. Which arrangements need a chain, and which could use existing infrastructure, remains open.

<a id="what-a-shared-record-leaves-to-judgment"></a>

## What a shared record leaves to judgment

A [shared record](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/when-an-approval-reaches-the-effect/) could identify the version used, the agreed use and the operation attempted. The payment reviewer still needs the extraction result and enough evidence to decide whether to approve it. Recording an approval also does not tell the participants whether a payment succeeded. They need an account of the result as well as the decision.

The choice of infrastructure follows that coordination problem. A common ledger could help participants compare their accounts of an exchange. It cannot supply a missing delivery date, judge an invoice or make an unsupported extraction reliable.

<a id="reuse-within-one-application-and-across-applications"></a>

## Reuse within one application and across applications

[YojnAI](https://daostudio.in/yojnai/) approaches reuse within an application by arranging models, tools and checks for a particular operation. DAOnet's [protocol](https://daostudio.in/collections/protocols-and-reuse/) extends reuse across applications and teams. Its practical question is whether sharing a capability saves the receiving team work while preserving what it needs to understand and review the result.


Reading path: [DAOnet](https://daostudio.in/daonet/) > [Reuse a capability](https://daostudio.in/daonet/reuse-a-capability/)
