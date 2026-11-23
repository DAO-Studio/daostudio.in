Title: A precognition court for AI

[Read HTML](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/a-precognition-court-for-ai/)

Author: Harsh Joshi

<a id="a-precognition-court-for-ai"></a>

# A precognition court for AI

Imagine an AI powerful enough to rewrite its own programming. We have given it rules intended to keep it safe. What stops it from changing those too?

That was the question behind my January 2024 thought experiment. If the safeguards live entirely inside the system they constrain, we are asking the actor to preserve the rules against which it will be judged. I wanted to put those rules somewhere it could consult but could not unilaterally rewrite. Blockchain interested me as one possible way to make that separation difficult to undo: a shared account maintained outside the AI, with the AI excluded from control of its consensus mechanism.

The ambition was a fail-safe. The thought experiment is how to build one, not evidence that a blockchain has already made an AI safe.

<a id="first-it-is-a-ledger"></a>

## First, it is a ledger

You can keep a ledger on paper, in a spreadsheet or in a database. A blockchain is another way of keeping a record, with a protocol through which participants agree on its history. The interesting part here is what it would take for one participant to change a record that others rely on.

Bitcoin's proof-of-work design makes a changed block require new work, including work for the blocks following it. Its security argument assumes that honest participants collectively control more computational power than the attacker. Under that assumption, an attacker's chance of catching up falls as confirmations accumulate.<sup><a id="fnref-note-6c6564676572"></a>[1](#fn-note-6c6564676572)</sup> That is a conditional, costly-to-rewrite record, not an infinitely difficult problem. Adding participants alone does not make a network invulnerable. Other consensus designs use different resources and assumptions; Ethereum's proof-of-stake documentation, for example, describes attacks and recovery involving both stake and social coordination.<sup><a id="fnref-note-7374616b65"></a>[2](#fn-note-7374616b65)</sup>

The attraction remains: a powerful program should have to contend with an independently maintained system rather than edit a local file and declare itself exempt. But the independence has to exist in the actual arrangement. A chain controlled by the same actor would give the proposal an impressive name without the separation it needs.

<a id="ball-is-in-your-court-now"></a>

## Ball is in your court now

Suppose the rules are outside the acting AI. My January 2024 proposal went as far as every atomic action: before taking any such action, the AI would submit it to a service that checks it against those rules. Permission or refusal would return before the action proceeds. The decision and the version of the rules used would enter the shared record.

**Note**

**A universal ambition.** Checking every atomic action was the proposed scope, not a demonstrated capability. Defining the unit of action, checking it quickly enough and dealing with consequences the checker cannot predict remain feasibility questions.

Call it the *Precognition Court*: the court is supposed to act before the consequence, rather than merely explain it afterwards.

The checking service would be automated but would not itself depend on another AI making an open-ended judgment. It would assess requests, identify patterns among refused actions and feed those patterns into a reward mechanism. Earning that reward would be part of the acting AI's objective, so the system would learn to stay within the rules rather than repeatedly collide with them.

There are two different jobs in that proposal. The check decides whether this action may proceed under the current rule. Learning is intended to make future behaviour better. A reward for compliance cannot replace the check: the action still has to meet the rule even while the system is learning. The proposal needs a way to express the action, evaluate it and handle what the checker cannot determine. Those are substantial parts of the problem.

![An independent check uses a rule version before action; proposals, decisions and observed outcomes return through a shared record for people to review.](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/a-precognition-court-for-ai/court-action-path-light.svg)

The proposed court connects three different kinds of work: people changing the rules, a check governing the action, and a record of the decision and observed result. Dashed arrows carry records and review material; they do not make the action path unavoidable by themselves.

<a id="separation-of-church-and-state"></a>

## Separation of church and state

Asimov's laws offer a familiar image of rules above an individual machine's preferences. The harder question is how those rules acquire enough meaning to govern a real situation, and how they improve when a case exposes a mistake.

AI researchers cannot answer that alone. The court would bring people from public policy, medicine, social science, psychology, defence and other disciplines into governing the rules. They understand different consequences of an action. The acting system would be a citizen of that arrangement, subject to its laws rather than free to change them whenever they obstructed its purpose.

The record of requests and decisions would give those people something to examine. Repeated refusals could reveal a harmful strategy, a badly described request or a rule blocking a legitimate need. They would have to distinguish those possibilities, investigate consequences and amend the rule deliberately. The record supplies cases; it does not supply the answer to every case.

That is why keeping the AI outside the voting mechanism matters to the idea. It separates producing an action from deciding the rules under which the action is permitted. The people changing the rules still need a mandate, and the people affected need a way to question them. A technically independent court could otherwise concentrate all the consequential choices in another unaccountable institution.

<a id="the-rule-has-to-reach-the-action"></a>

## The rule has to reach the action

My proposed hardwiring went as far as dedicated circuitry integrated into each deployed AI, routing every command that reached it through the external check and back before continuing. It was meant to make the court compulsory for every atomic action, rather than another instruction the AI could choose to ignore. Ensuring that no action could bypass such a circuit remained part of the problem.

A smaller, invented example helps expose what that requirement means. A document service prepares a report and obtains approval for version one. It then changes a passage before release. The earlier decision does not automatically approve version two. The release tool has to examine the version actually being sent and the decision that applies to it. If the service also holds an unrestricted upload credential, it can bypass the court altogether.

The [path from approval to effect](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/when-an-approval-reaches-the-effect/) therefore matters as much as the record of approval. A common ledger can make an altered account harder to conceal. It cannot, merely by existing, stop an action occurring through a route outside the arrangement. Keeping the rule beyond the actor's control and making the action depend on that rule are connected engineering problems.

<a id="a-court-people-can-question"></a>

## A court people can question

Now suppose the report contains an error, but the court's rules describe only an initial release. The author wants to correct it; a reader needs to know which version to rely on; the operator needs a procedure it can carry out. A refusal may be faithful to the rule while revealing that the rule is incomplete.

Who can bring that case? Who can inspect the reasons for the refusal? Who may amend the policy? A useful court needs answers that do not depend entirely on the organisation whose decision is being challenged. Different kinds of expertise help, but expertise and the right to decide for other people are not the same thing.

A revised policy could distinguish a correction from a new release, identify when it takes effect and preserve the earlier decision in the history. An urgent correction might need a quicker path than a general change to the rules. That path still needs a visible scope; otherwise exceptions become a second policy known only to the operators. The aim is to make a mistaken rule correctable without giving the acting system an unrestricted escape from review.

This is the wider possibility that made decentralisation interesting to me: people improving a shared arrangement while the system governed by it cannot simply remove the constraints. Recording votes or allocating tokens does not by itself settle who should govern. The question is what the participants can understand, contest and change, and whether their judgment reaches the action.

<a id="the-helmet"></a>

## The helmet

When I first wrote this, I did not expect a rogue AGI any time soon. Relax\! This is just a fun thought experiment. The engineering difficulties do not make the question uninteresting. They tell us what the proposed fail-safe would have to survive: a changed rule, a mistaken judgment, an attacker and an action trying to leave through another door.

My uncle's advice was simpler: you do not need a helmet every day; you need it on the day you have an accident. You do not know which day that will be, so put it on.

That is the spirit of the court. Think about the restraint before the accident, and make sure it is attached to something that can actually restrain the action.

For a more grounded view of the state of AI, there is [The autocorrect paradox](https://rawthoughts.in/blog/the-autocorrect-paradox/).

1. 
   
   <a id="fn-note-6c6564676572"></a>
   
   Satoshi Nakamoto, [*Bitcoin: A Peer-to-Peer Electronic Cash System*](https://bitcoin.org/bitcoin.pdf), sections 4 and 11. The attack analysis depends on relative computational power and accumulated work. [↩](#fnref-note-6c6564676572)

2. 
   
   <a id="fn-note-7374616b65"></a>
   
   Ethereum's [proof-of-stake attack and defence documentation](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/attack-and-defense/) explains the different assumptions and the role of social coordination in some recoveries. Proof of work is not a description of every blockchain. [↩](#fnref-note-7374616b65)


Reading path: [Protocols and reuse](https://daostudio.in/collections/protocols-and-reuse/) > [A court before the consequence](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/) > [A precognition court for AI](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/a-precognition-court-for-ai/)

Next in journey: [When an approval reaches the effect](https://daostudio.in/collections/protocols-and-reuse/a-court-before-the-consequence/when-an-approval-reaches-the-effect/)
