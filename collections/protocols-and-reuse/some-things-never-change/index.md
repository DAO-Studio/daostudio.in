Title: Some things never change. It’s time they do…

[Read HTML](https://daostudio.in/collections/protocols-and-reuse/some-things-never-change/)

Author: Harsh Joshi

<a id="some-things-never-change-it-s-time-they-do"></a>

# Some things never change. It’s time they do…

Okay. Before we get into AI interoperability and the possible role of a blockchain, a refresher.

What is a blockchain? In its most rudimentary form, a ledger. A better one, or a worse one, depending on the use case. Cryptography helps participants verify records; a consensus mechanism determines which history they accept. The familiar operations of creating, reading, updating and deleting data take a different shape when participants need to agree on a shared record. “Immutable” is shorthand for resistance to rewriting under the system's security assumptions, not a magical exemption from attack.<sup><a id="fnref-note-6c6564676572"></a>[1](#fn-note-6c6564676572)</sup> Once you have that ledger, you can do cool shit with it. DeFi was all the craze a couple of years before I wrote this in May 2024.

And a neural network? At this level of abstraction, a function approximator. Think of a sine wave and the periodic functions it suggests; then think of aperiodic, linear and nonlinear relationships. Given data spread through an n-dimensional space, can a network learn a useful relationship among the values? Fitting those examples is one part. Generalising beyond them is what makes the result useful. I hear “generation” is all the craze these days.

Cool. That's it. No more extra-credit assignments from this point on.

I lied. There's one more thing.

What's an API? A defined way for software systems to talk to each other. A really awesome one, sometimes. Its usefulness depends on what it lets the other system do.

<a id="the-interface-stayed-familiar"></a>

## The interface stayed familiar

Software had decades in which to develop its routines, interfaces, deployment practices and containers. Then the post-2022 AI rush made a familiar neighbourhood model, GPT, everyone's business. The question I was asking in 2024 was what happened when we took established software interfaces and translated them almost verbatim into this much younger wave of applications.

Did you read the paragraph above?

Yes or no?

That gives us a simple state to reason about. In an ordinary program, we can often name routines, describe their inputs and outputs, and expose the parts another program needs to call. For a fixed set of inputs and state, a deterministic routine produces a fixed result. Randomness and concurrency can complicate that behaviour, while the named routines still give us parts to examine and compose.

A trained neural network offers a different problem. We can see its architecture and, where available, its parameters. That does not automatically give us a set of independent, named abilities that can be lifted out and used like ordinary routines. Knowing where multiplication occurs is not the same as knowing where “understands a supplier's exception” lives.

Yet the familiar request-and-response interface is often the first thing we build around it. That is useful. It can also conceal the part we have not learned how to separate.

Consider Docker and the software engineering practices around containers. They arrived through years of testing, adoption and adjustment. The AI application rush was trying to compress a comparable maturation into a couple of years. Two years versus decades. What could go wrong?

Plenty.

<a id="zero-or-one-which-part-can-another-system-call"></a>

## Zero or one: which part can another system call?

A modern AI application can look remarkably like an operating system, loosely speaking. Retrieval is part of its input/output path. Context resembles working memory. Agents resemble threads carrying out activities. These are analogies, not literal descriptions of an LLM's internals, but they help locate the work.

A model is invoked at a particular point in the agent flow. The orchestration framework supplies context, remembers intermediate results, chooses the next call and eventually returns an answer. Much of the application's useful behaviour lives in that arrangement around the model.

Now let a second system call it. Suppose the exposed choices are only:

- **Zero:** call the base language model.
- **One:** call the complete orchestrated application and receive its final answer.

Calling that final endpoint from an ordinary application may be entirely sufficient. But when one agent system needs to work with another, the choice is limiting. It may need the state reached halfway through a task, the evidence already collected, or a callback when a particular agent has finished. Starting again at the base model discards useful work. Calling the final endpoint asks for more work than the receiving system needs.

The problem is not that an API is incapable of carrying state. An application can persist memory and expose finer operations. The problem is that a wrapper which exposes only those two endpoints has not done so. Its caller cannot reach the internal memory merely because the application uses agents. And exposing that memory still says nothing about whether learned abilities inside the underlying model are independently reusable.

<a id="what-we-tried-with-yojnai"></a>

## What we tried with YojnAI

With [YojnAI](https://daostudio.in/yojnai/), our approach was to wrap memory states in a data structure and keep caching those states so the application could expose callbacks at the agent level. A caller could work with an intermediate state instead of choosing only between the base model and the final orchestration endpoint.

This also let us “teach” the invoked LLMs to work with the wrapper's memory operations during the application flow. The wrapper kept the states; the model could use those operations. That is different from a neural network acquiring a memory subsystem we could lift out and transplant into another model.

We built utilities on top of that work and called them Apps. Different story. [YojnAI's application design](https://daostudio.in/yojnai/compose-inspect-and-improve/) follows those parts through the work a customer needed to do.

But even that approach was not enough for the larger question.

<a id="a-third-possibility-combine-the-learned-parts"></a>

## A third possibility: combine the learned parts

What I really wanted was a third scenario: a subnet of one neural network working with a subnet of another. Not merely their final answers passing through an endpoint. The learned capacities themselves becoming composable.

Imagine a model M1 containing capacities I1, I2, I3, …, In, realised through subnets which might overlap. Another model, M2, contains capacities K1, K2, K3, …, Kn, again potentially overlapping.

How would you take **K2 from M2, and I2 and I3 from M1, to make M3?**

**Note**

**Naming a capacity does not isolate it.** The notation makes the question easy to write. It does not establish that those capacities are cleanly located, separable or compatible. Overlap is part of the difficulty. Removing the part we call I2 might also remove something I3 relies on. Two representations that work within their own models may not mean the same thing when connected.

There are two different times at which we might attempt the combination:

| When the combination happens | The question it raises |
| --- | --- |
| Before deployment, loosely like compilation | Can selected learned components be aligned and assembled into a new model which preserves the wanted capacities? |
| During execution, loosely like runtime linking | Can one running system use a selected learned capacity in another, with the representations, state and dependencies needed for that interaction? |

Pre-deployment composition is a research problem of its own. Work such as Git Re-Basin examines a particular route to aligning and merging model weights.<sup><a id="fnref-note-6d657267696e67"></a>[2](#fn-note-6d657267696e67)</sup> The runtime question reaches beyond what a request-and-response wrapper has solved. Transporting a message cannot, by itself, discover a decomposition of the learned computation or make incompatible representations fit.

That was the force of my complaint about the API model. The familiar interface can carry the eventual interaction. It cannot substitute for understanding what is being composed.

My gut said a blockchain might have a role here. A shared record could help parties coordinate contributions, versions or use. It would still need something meaningful to record. The road from a ledger to a working M3 is long and hard.

The inquiry continues in [The intelligence between the parts](https://getharsh.in/collections/meaning-models-and-creative-practice/the-intelligence-between-the-parts/). It asks what must pass between learned capacities for their combination to retain meaning. There is also nearer work we can do without claiming to have solved that problem: make the capabilities we already know how to share intelligible to their next user.

<a id="several-different-things-can-look-like-intelligence"></a>

## Several different things can look like intelligence

A model, a prompt, a dataset, a workflow and a hosted service can each contribute to a useful result, but the next team receives something different in each case. A dataset provides examples, a prompt supplies instructions in a context and a workflow connects operations. A model contains learned parameters, while an endpoint offers a response with much of its implementation remaining at the provider. These forms carry different dependencies and different opportunities to change the behaviour: adopting a prompt leaves the consumer to supply the model and its context, whereas invoking a service leaves more of the operation with the provider. A useful catalogue makes that contribution and continuing responsibility intelligible, so a team can discover the form it actually needs.

<a id="application-composition-is-a-nearer-form-of-reuse"></a>

## Application composition is a nearer form of reuse

Consider two hypothetical document capabilities. One extracts supplier details from an invoice; another checks a proposed payment against the extracted terms. They can be combined through defined inputs and outputs. The second does not need the first system's entire internal process, but it does need enough context to know what the result means. Was the supplier identity confirmed or merely inferred? Is a payment date absent, or was extraction unsuccessful? Does the returned value refer to this invoice or another record? Each distinction changes what the checking step can do with the answer.

A catalogue entry for that invented extraction capability could carry a compact account rather than a promise of general document understanding:

| Part of the capability description | Example declaration |
| --- | --- |
| Object being supplied | A document-extraction workflow, not a trained subnetwork |
| Input | A declared family of invoice documents |
| Output | Supplier fields and payment terms, with source locations and unresolved values |
| Required context | Document identity, language and the selected workflow version |
| Evaluation question | Whether supported examples preserve the fields and evidence needed by the payment check |
| Boundary | No authority to approve or execute a payment |
| Conditions of use | The workflow's licence and dependencies, without any customer's invoice data |

The next component can now ask a particular question of the output. An absent payment date can remain unresolved rather than masquerade as a zero or an extraction success. Another document layout gives the receiving team a case to test, not a reason to assume the same result. The description supplies a starting point for adoption; the receiving application still has to examine the contribution in its own setting.

<a id="versioning-is-a-relationship-with-downstream-work"></a>

## Versioning is a relationship with downstream work

If the extraction changes, the checking step may change even when its own code does not. A newer model might recognise more layouts and produce a different format. A revised tool might treat a missing field differently. Moving from a source location to a bare value could leave the payment check without the evidence it used to receive. Versioning connects those changes to the downstream work that depends on them; its value comes from identifying relevant behaviour and requirements.

The application needs to identify which capability it used and retain enough context to investigate a regression. Keeping an earlier configuration available can support recovery, provided its dependencies can still be supplied. The practical promise of reuse is less repeated work. Unannounced changes reverse that promise when every consumer has to rediscover the same failure, reconstruct its cause and repair their application separately.

<a id="adoption-gives-the-description-a-test"></a>

## Adoption gives the description a test

The receiving team can now try the capability against a small set of its own permitted documents. Some may match the declared layout; one may use a different currency convention; another may omit a term that the payment check requires. This is where the description becomes useful. It tells the team which result would count as a supported contribution, which case should return an unresolved value and which case needs another adapter or method.

A failed adoption can improve the shared account. If the consumer had supplied a supported document and lost its source locations, the implementation may need correction. If the document was outside the declared family, a clearer discovery filter could have saved the trial. If the output was faithful but the consumer needed a different question answered, the capability may be working and still be the wrong choice. A network that retains those distinctions can improve discovery without turning every poor fit into a bad rating.

This form of adoption is already a useful contribution to the larger ambition. A catalogue can make models, workflows and methods easier to adopt while keeping clear which object is being shared.

<a id="rights-travel-with-the-dependency"></a>

## Rights travel with the dependency

A useful configuration may contain a customer's process. A model may carry a licence with particular limits. A dataset may be available for one purpose without permission for another. A standard interface can connect them while their rights remain different. The consumer needs to know which contribution they may use, how they may change it and what must stay with the original owner.

DAO Studio's platform and partner-product distinction made this concrete: the shared platform and the application made for a partner could have different owners. [A reusable mechanism could emerge from service work](https://daostudio.in/blog/turning-service-work-into-reusable-capability/) while the partner's records and particular work remained theirs. That boundary makes a contribution possible without asking people to surrender everything they bring. It also gives the receiving team a clearer account of what they can build upon.

<a id="what-a-network-would-have-to-add"></a>

## What a network would have to add

A functioning capability may already be useful to one organisation. A network would need to make something else easier: discovery, comparison, composition, payment, coordination or maintaining a shared account of versions. Contributors need demand; users need capabilities worth adopting. A useful protocol connects those needs to work people can already value, with a reason to participate beyond the hope of a larger network.

[DAOnet](https://daostudio.in/daonet/) explored that protocol ambition through a proposed ledger, memory, observation and execution stack for agents. The wider goal was cumulative capability: one team’s work becoming a useful contribution to another application. A [common record](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/when-an-approval-reaches-the-effect/) could support part of the coordination, while a catalogue and intelligible interfaces could support others. The choice of mechanism should follow the interaction it improves.

Useful work can accumulate only if its conditions remain intelligible as it travels. A shared capability should save the next person from repeating the mechanism, not force them to repeat the investigation into what it actually means.

1. 
   
   <a id="fn-note-6c6564676572"></a>
   
   Nakamoto's [Bitcoin paper](https://bitcoin.org/bitcoin.pdf) states the honest computational-majority assumption behind its history-selection argument. Other consensus systems have their own assumptions; the ledger description here does not make them interchangeable. [↩](#fnref-note-6c6564676572)

2. 
   
   <a id="fn-note-6d657267696e67"></a>
   
   Ainsworth, Hayase and Srinivasa, [Git Re-Basin: Merging Models modulo Permutation Symmetries](https://arxiv.org/abs/2209.04836), studies aligning model units through permutations and merging in weight space. It is a specific model-merging result, not the arbitrary I/K-capacity operation posed here. [↩](#fnref-note-6d657267696e67)


Reading path: [Protocols and reuse](https://daostudio.in/collections/protocols-and-reuse/) > [Some things never change. It’s time they do…](https://daostudio.in/collections/protocols-and-reuse/some-things-never-change/)
