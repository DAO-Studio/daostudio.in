Title: An agent, a playbook and an application

[Read HTML](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/)

Author: Harsh Joshi

<a id="an-agent-a-playbook-and-an-application"></a>

# An agent, a playbook and an application

A final answer is a convenient interface until another part of the system needs to participate in reaching it. A purchasing assistant may have found the agreement and extracted its terms while still waiting for a delivery date. The reviewer can already do useful work with those terms; the customer's answer should enter at the point where it is needed. Making both people wait for a completed response wastes the structure the application has already built.

[YojnAI](https://daostudio.in/yojnai/)’s composition model gives that unfinished work a form other people and systems can use. An agent makes a contribution, a playbook arranges the contributions, and an application connects them to a customer's records, services and access. Each has a different job to do.

**Context:** the organisation’s records, services, people and permitted access.

**Application:** a particular configuration of playbooks and their connections. Versions can change the configuration’s behaviour without becoming separate service instances.

**Playbook:** agents arranged with checks, dependencies and conditions for continuing.

**Agent:** models and tools combined for one contribution, with intermediate state available to the surrounding work.

<a id="the-space-between-a-call-and-an-entire-system"></a>

## The space between a call and an entire system

Calling a model gives the surrounding application responsibility for arranging the work. Calling an entire orchestrated service gives it a finished response. Between those two lies a place to integrate: the work in progress, with enough identity and meaning for another component to contribute to it.

Think of a hypothetical assistant preparing a purchase request. It retrieves a supplier record, extracts terms, identifies a missing delivery date and asks for clarification. A second system may need to display the missing date before the final request exists. A reviewer may need to inspect the extracted terms without rerunning everything.

An agent-level callback can make the extracted terms available while the purchase is pending. Saved intermediate state keeps that extraction available when the customer supplies the date. The application can continue from the missing answer instead of repeating unrelated work. What crosses the interface is a particular operation, its available results and the dependencies still waiting to be satisfied.

<a id="what-the-agent-takes-on-and-what-it-leaves-alone"></a>

## What the agent takes on, and what it leaves alone

An agent combines models and tools into a unit of application work. The extraction agent needs a source, a way to identify its terms and a form in which to return them. A model can contribute interpretation while retrieval or a deterministic parser supplies another part. The contribution belongs to the whole unit, rather than being another name for the underlying model.

Its output also shapes the next contribution. Returning a guessed delivery date makes the composition appear complete while moving missing information out of view. Returning it as unresolved gives the application a question to ask. Another workflow can reuse that extraction without inheriting the entire purchasing operation, including the authority to place an order. The unit becomes composable because its contribution and limits remain intelligible.

<a id="the-playbook-carries-the-arrangement"></a>

## The playbook carries the arrangement

A playbook arranges agents and checks into a workflow. In the purchasing example, the supplier identity may need to agree across two records, a term may need its source location and a missing value may call for clarification. The draft can proceed when those dependencies are satisfied, then meet a review before leaving the system. The arrangement gives each contribution a reason and a place in the work.

A failed check consequently carries information about what to do next. A missing source location can send the work back to extraction; disagreeing identifiers can prompt investigation of the records; an unresolved intention can require the customer. These checks establish different things. A field's presence or two identifiers agreeing helps the workflow without settling whether this is the supplier the customer intended. Preserving the distinction makes the failure useful instead of reducing it to “the model failed.” The [execution record](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/) can help locate which contribution needs attention.

A financial calculation makes the need for structure especially clear. To calculate the last twelve months, combine the previous financial year with the current partial-year period, then subtract the corresponding prior-year period. Each input needs its period and units: a correct subtraction applied to mismatched periods is still the wrong answer. Named inputs, operations and conditional branches make those choices inspectable.

Basic and diluted shares are different quantities, as are equity value and enterprise value. Price dates, share-count dates and statement dates can also differ. Keeping each definition with its source, period and units prevents the workflow from quietly substituting a different calculation for the one requested.

These intermediate contributions are also places where another application can join the work. [Some things never change](https://daostudio.in/collections/protocols-and-reuse/some-things-never-change/) develops that callback-and-cache argument beyond the individual calculation.

<a id="what-changes-when-the-customer-answers"></a>

## What changes when the customer answers

The moment the user answers the missing-date question, the application has acquired context that did not exist at the first call. That answer belongs to a particular purchase and version of the work. It can unblock the draft without changing the supplier extraction. If the reviewer instead corrects a payment term, the dependent draft needs reconsideration while an unrelated delivery address can remain valid. State becomes useful when the application can distinguish these effects rather than stuffing every change into a larger prompt and hoping it is interpreted correctly.

The following invented state account makes the dependency concrete.

| Contribution | After extraction | After the customer supplies a date | After the reviewer corrects the payment term |
| --- | --- | --- | --- |
| Supplier and source | Available | Retained | Retained if the same source still applies |
| Payment term | Available, awaiting review | Retained | Replaced by the reviewed value |
| Delivery date | Unresolved | Available | Retained |
| Purchase draft | Waiting for the date | Ready to assemble | Recompute the part depending on the term |
| Order placement | Not performed | Not performed | Not performed |

Supplying the date can complete a draft without placing an order. Correcting the payment term can invalidate part of that draft without discarding the address or asking for the date again. A delayed callback carrying the earlier term has to remain an earlier result, rather than overwrite the correction. This is the practical attraction of exposing the work's dependencies: resumption can continue at the change instead of restarting the conversation or replaying a consequence.

The dependency account also has to survive concurrent work. A request sent before a correction can return after it. The application needs to compare the returning result with the source and operation revision it was asked to use; arrival time alone cannot supply that relationship. Retaining the late response can make the execution explainable without accepting it into the current draft. The draft, its dependencies and any external action need distinguishable records.

<a id="the-application-ties-the-playbook-to-one-customer-s-records"></a>

## The application ties the playbook to one customer's records

An app configuration connects playbooks to the records and services they need. The same playbook can enter another context, where different supplier records are connected, different people may inspect them and an approved request goes to another destination. Those choices make it a particular customer's application: they affect the actual work, not merely its branding.

An application configuration can have several versions, which count as one service instance. Revising an agent or check changes the composition without making it a separate instance. The distinction lets the application develop without treating every adjustment as a new commercial identity. Its versions nevertheless need to identify the behaviour and dependencies the customer is choosing to use. Those same conditions matter when [a capability travels to another team](https://daostudio.in/collections/protocols-and-reuse/some-things-never-change/): the contribution has to remain intelligible outside its first application.

<a id="where-another-contribution-can-join-the-purchase"></a>

## Where another contribution can join the purchase

The purchase can now continue through a useful division of work. The extraction supplies terms with their source; the customer supplies a date; the reviewer corrects a value; the playbook assembles the dependent draft. The application makes those contributions part of one operation without treating them as one undifferentiated prompt. A change has somewhere to enter, and the work it affects has somewhere to continue.

The larger question of whether [learned capacities themselves can be composed](https://getharsh.in/collections/meaning-models-and-creative-practice/the-intelligence-between-the-parts/) remains compelling. Here the useful unit is more immediate: a contribution whose meaning and dependencies let another person or system join the work before the final answer exists.


## Article notes

<a id="gazette-notes-what-should-survive-a-change"></a>

## What should survive a change?

A purchase is waiting for payment terms. While extraction is running, the customer supplies a date and a reviewer changes which agreement applies. The earlier extraction then returns. Its result can be faithfully read and no longer belong in the current draft. The following invented event labels make that dependency visible; they are not names from a YojnAI API.

| Event | Operation state | Treatment of the work |
| --- | --- | --- |
| Start extraction from agreement A | Revision 1; payment terms unresolved | Send request X carrying agreement A's identity and revision |
| Customer supplies the delivery date | Revision 2; date available | Retain the address and supplier; the draft still needs terms |
| Reviewer identifies agreement B as the applicable source | Revision 3; terms from A no longer usable | Request terms from B; invalidate draft work depending on A |
| Request X returns terms from A | Revision 3 remains current | Retain the response as the result of X; do not install it as the current terms |
| Extraction from B completes and passes the relevant checks | Revision 4; current terms available | Assemble a new draft using B's terms and the retained date and address |

The source change is important here. The two extractions might return the same words, yet only one answers the request under the selected agreement. Comparing values alone would miss the changed basis. Conversely, incrementing a revision need not invalidate everything: the date supplied by the customer still belongs to this purchase, and the unchanged address did not depend on the agreement. Dependencies determine what survives; a global revision helps identify the request without replacing that account.

Accepting a result and retaining a result are also different operations. Keeping X in the execution record makes the late response explainable. Making it current would undo the reviewer's source correction. A handler can record the response, compare its request and source against the active branch, and leave it out of the draft while continuing to wait for B. That is more useful than silently discarding it or letting the latest arrival win.

There is a second check at assembly. Suppose the response from B was accepted, but a new source correction arrived before the draft was committed. The assembly needs to check that its selected dependencies still match the current purchase. Otherwise it can publish a locally consistent draft assembled from a position the application has already left. A revision check at that boundary, followed by reconsideration of the changed branch, gives the concurrent update a defined treatment.

None of the five events places the order. If a later operation does that, its execution record needs an identity separate from the draft's revision. Losing the reply from an order service creates an uncertainty about an effect, not an invitation to assemble and send the draft again. Recovery first has to establish what that service recorded under the original action. Preserving completed interpretation, accepting a corrected draft and establishing an external effect are three different jobs.



Reading path: [Composing AI work](https://daostudio.in/collections/composing-ai-work/) > [From composition to a deliberate change](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/) > [An agent, a playbook and an application](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/)

Next in journey: [Reading the work behind an answer](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/)
