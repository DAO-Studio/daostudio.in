Title: Turning service work into reusable capability

[Read HTML](https://daostudio.in/blog/turning-service-work-into-reusable-capability/)

Author: Harsh Joshi

<a id="turning-service-work-into-reusable-capability"></a>

# Turning service work into reusable capability

Suppose the second customer asks for a report that sounds almost exactly like the one a team finished last month. The task looks familiar until the documents arrive: the columns differ, the approval comes from another person and a familiar category means something else. How much of last month's work has the team actually saved?

That question sat inside DAO Studio's service-to-product ambition. Consulting put the team close enough to an organisation to understand a useful problem. A product would let that work accumulate: a configurable application, a reusable mechanism and a handover through which the next team could use and improve it. The next customer would receive more than another round of custom development. The interesting part was finding what could remain stable as the organisation around it changed.

<a id="the-studio-s-earlier-proposition"></a>

## The studio’s earlier proposition

The 2022 Startup-as-a-Service proposal joined venture setup to shared delivery. DAO Studio would lead a group supplying strategy, design, engineering, quality assurance and operations. A discounted development fee paid ahead of each phase was paired with a proposed share of future revenue. The product was to reach its first market entry and a handover, then remain listed as a utility under defined platform terms, including an initial exclusive period and a cap on revenue sharing.

That made two different bets. Hands-on work would help a venture reach something useful; a platform listing would give the resulting utility a route beyond the original engagement. The question underneath them still stands: can the reusable part earn its upkeep after the people who created it hand the work over?

A creative and design partnership and a consumer-app prototyping proposal explored different sides of that arrangement. Neither made every partner’s product a studio-owned asset. The intended right to turn the work into a template needed to stay distinct from ownership of the customer’s product and from the actual rights agreed for a particular engagement.

<a id="two-reports-that-only-look-alike"></a>

## Two reports that only look alike

Imagine a team building a weekly purchasing report for a small business. It brings together invoice data, checks missing fields and prepares a manager's summary. Another business asks for something similar. The extraction routine may travel, while supplier records, approval rules and explanations of unusual transactions remain with the first business. The new customer uses another source format, defines a purchasing category differently and has a different approver. The product question is now precise: which mechanism can remain stable across those changes?

The two reports give us a way to examine the resemblance. Perhaps both need to identify a supplier and retain where an amount came from, while only the first uses a particular approval threshold. The common work can become a unit worth maintaining. The threshold remains an explanation of one customer's operation. Copying the whole solution would carry both together; rebuilding everything would throw away the discovery. A product begins to take shape when the team can make that difference usable by somebody else.

<a id="finding-the-stable-part"></a>

## Finding the stable part

A reusable unit exposes what it needs and what it produces. In the reporting example, that could mean an explicit input format, a rule for representing missing values and an output that retains the relevant source locations. Those stable choices leave customer-specific policies as configuration with a named owner. A different approver can use the same extraction mechanism without changing every customer's approval rule. A new source format gives the adapter work to do rather than silently losing fields until the data fits.

The boundary could be made explicit:

| Shared mechanism | Customer-specific setting |
| --- | --- |
| Return an amount with currency and source location | Which purchasing category it belongs to |
| Represent an absent value as unresolved | Who must supply or review that value |
| Detect an unsupported input format | Which source systems this customer connects |
| Produce a versioned extraction result | Which manager may accept the report |

The second customer can change the right-hand column without redefining the extraction result for everyone. An unsupported document still needs a recognisable failure path rather than an empty report that looks like no purchases occurred. A version, known dependencies and [the conditions under which the capability was evaluated](https://daostudio.in/collections/protocols-and-reuse/some-things-never-change/) give the next team somewhere to begin investigating it.

<a id="generalisation-does-not-supply-permission"></a>

## Generalisation does not supply permission

**Caution**

**Removing a name does not establish reuse rights.** An artefact called a template may still contain a customer's confidential process, licensed material or distinctive configuration after their name is removed. The arrangement needs to distinguish the shared platform, the customer's deliverable, their data and any permitted reuse. A reusable input convention can belong to the platform while a particular mapping expresses the customer's process. The actual rights and agreement determine whether either can travel to another use.

DAO Studio explored templatising service work, while [YojnAI](https://daostudio.in/yojnai/) distinguished the shared platform from a partner's product. That distinction gives reuse a concrete form: the platform can develop while the partner keeps the work and records belonging to their application. Other cases may require independent implementation, an approved abstraction or an explicit licence. Sometimes a lesson informs the next design while the original artefact stays with its owner.

<a id="a-handover-is-part-of-the-product-decision"></a>

## A handover is part of the product decision

Consulting can rely on a person who remembers the exceptions. A product has to make more of that knowledge available to the next team. For the report, a handover would explain how to connect the sources, change the permitted configuration, review an uncertain result and recover a failed run. It would also identify the responsibilities that stay with the provider and those the customer's team accepts. These choices give [the shared units a particular operating context](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/).

An easy setup screen can conceal configuration upkeep, evaluation and repair that somebody still has to perform. Without an intelligible handover, a supposedly self-service product may simply move that work into an invisible support queue. Its value depends on another team being able to operate the capability within understood limits, including the ordinary exceptions through which the report becomes useful to them.

<a id="the-first-adoption-and-the-wider-network"></a>

## The first adoption and the wider network

DAO Studio also explored [DAOnet](https://daostudio.in/daonet/), a network through which people could discover and compose capabilities. That introduced a circular adoption problem: contributors want demand, while users want capabilities they can already rely on. A service for one customer can reveal the first need, and a working reusable unit can make the next adoption easier. The reporting tool can deliver value to one business before hundreds of others join.

A network could then improve discovery and coordination around that contribution. Its terms would need to make joining useful to the business: obtaining an ordinary report should not depend on surrendering its private process or participating in an unrelated token system. The capability's value gives the network something to connect; the network's value comes from making that connection easier.

<a id="support-can-consume-the-product-budget"></a>

## Support can consume the product budget

Service income was one proposed source of support for product development and research; the studio’s earlier plan also depended on raising capital. They were not interchangeable sources of money. Service income first had to cover delivery and the continuing work needed to support the customer. Delivery has to leave enough capacity for product development to happen rather than consume it through unfinished support.

A low installation cost says little if every new configuration creates hours of unpriced work. Subscription and conversion forecasts can help plan the operation, but their usefulness depends on demand and costs becoming observable as the service develops. The reusable mechanism should reduce reconstruction across customers; otherwise the product budget may only be subsidising repeated custom delivery.

Consider a deliberately simple monthly budget. A service brings in 100 units of revenue. Delivery uses 60, continuing support uses 15 and the common operating costs use 10. That leaves 15 for product work or a reserve. If exceptional requests lift support to 30, the whole 15 has gone before anyone improves the shared mechanism. Calling part of the income a product budget does not create the time to spend it.

Reuse has an economic effect when it changes that arrangement. A clearer setup path might reduce the next customer's delivery effort; a fix to a common mechanism might reduce support across existing customers. Both can release capacity for another improvement. But generalising a capability also creates its own testing, documentation and compatibility work. The relevant comparison includes that upkeep. The product is becoming more sustainable when the shared work costs less than the reconstruction it prevents, without leaving the customer's exceptions unpaid and unattended.

This is why a second adoption matters more than a reusable-looking codebase. It exposes what travels, what has to be configured and what still depends on the original team. Service income can finance discovery; the resulting product has to earn its continuing maintenance through adoption. Research retains a different freedom: it can pursue an important possibility before there is a customer ready to pay for it, provided the studio can afford that time.
