Title: From feedback to a version worth using

[Read HTML](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/from-feedback-to-a-version-worth-using/)

Author: Harsh Joshi

<a id="from-feedback-to-a-version-worth-using"></a>

# From feedback to a version worth using

The supplier allows fourteen days, says the reviewer, not the thirty days returned by the purchasing assistant. The team could add the correction to its examples and train again. But suppose the answer faithfully followed the previous agreement. Teaching the model another sentence leaves the obsolete source in place, ready to produce the next disagreement.

The objection opens a choice about what to improve. A source, a step, an explanation and the task itself can each need attention. [YojnAI](https://daostudio.in/yojnai/)’s improvement idea connected the person’s objection to that choice through feedback projects, candidate jobs and deliberately selected application versions. The intended result was a system that could become more useful through experience, with the team able to recognise which change it was choosing.

<a id="what-a-reviewer-s-objection-carries-with-it"></a>

## What a reviewer's objection carries with it

The agreement's identity and version make the objection specific. The current document may resolve the immediate case, while the retrieval path needs a way to recognise which agreement applies next time. This is a different improvement from teaching the model to interpret an unfamiliar clause. Both can begin with the same negative rating; the context determines where that rating can become useful work.

Now suppose the source is current but the explanation is so complicated that the user cannot tell what to do. Or the answer includes information the user should not see. These failures call for different interventions: clearer explanation in one case, a repaired access boundary in the other. Feedback becomes useful when it carries the question being judged, the run and configuration involved, and what the person expected instead. Those details help locate a relevant change rather than merely accumulate disapproval.

<a id="different-reviewers-contribute-different-things"></a>

## Different reviewers contribute different things

The intended YojnAI designs separated access roles from expertise weighting and allowed app defaults and project-specific feedback settings to differ. The same execution could be evaluated for several purposes: a domain expert might judge an interpretation, an end user its usefulness, and another reviewer whether the operation was appropriate. Keeping their questions visible made room for disagreement that the product actually needed to address. A single combined score could hide that difference before anyone understood it.

Expertise weighting also left release responsibility as a separate decision. The person best placed to identify an error need not be the person responsible for changing the customer's application. Their contribution can be valuable precisely because it informs someone else's choice. “Human in the loop” acquires a practical meaning when the system gives that contribution a question, a context and a route into the work.

<a id="change-the-part-that-caused-the-problem"></a>

## Change the part that caused the problem

An application can improve through a source correction, a revised tool, a new check, a prompt change, a workflow change or model adaptation. That range was part of the appeal of treating YojnAI as [a composition](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/). The team could examine which contribution carried the failure and change it, while retaining the other work that remained useful.

Suppose extraction repeatedly misses a term across a supported document family. A different model or training approach may help. Suppose the term is extracted correctly but loses its source when passed to the next step. The interface between components may be the better place to change. [Evidence of that route](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/) lets the team choose a relevant intervention instead of treating sophistication as a substitute for diagnosis.

<a id="the-candidate-meets-more-than-its-original-failure"></a>

## The candidate meets more than its original failure

A revised version should encounter the case that prompted the change, alongside other work the application still has to do. An improvement for one question can damage another: a new model can increase latency, a narrower source can omit a previously valid use and a more cautious workflow can make an ordinary task unnecessarily difficult. The comparison needs cases and meanings appropriate to that operation, rather than a score detached from it.

For the purchasing example, we can specify a small comparison before running it:

| Case | What the comparison must examine |
| --- | --- |
| Old and current agreements are both present | Select the applicable version and retain its identity |
| A valid clause uses unfamiliar wording | Interpret the term and retain the source location |
| The delivery date is missing | Ask for it rather than invent it |
| The reviewer has already corrected a term | Preserve the correction against an older callback |

Now imagine a source-selection change fixes the first case but drops the source location in the second. It has repaired the immediate complaint while making review harder. A larger model might resolve the unfamiliar wording but take longer on ordinary requests. Neither trade-off disappears inside an overall accuracy score. The team needs the case-level results and the operating consequence before choosing between them.

YojnAI’s operating design made the path explicit: select an app and version, then a trace and the step being judged. Feedback belonged to a project; an administrator could version that project for fine-tuning, start an improvement job, inspect its result and explicitly push a chosen version to the app’s environment. One-click reversion was part of the same design. The comparison could therefore inform a particular choice, rather than make a negative rating an instruction to train or deploy.

In April 2024 the studio reported differential and cumulative fine-tuning as beta. A project’s access roles, its reviewers’ expertise weights and the person choosing a release still answer different questions.

<a id="choosing-which-version-to-release"></a>

## Choosing which version to release

A candidate can be better in a test and still need a staged introduction or another review before release. Someone has to decide what the evidence warrants in the intended setting. Identifying the selected version and its purpose makes that decision usable: a change chosen to improve extraction is a particular commitment, not a permanent quality inherited by every later configuration.

Recovery belongs to the same choice. If the new version changes a behaviour somebody relies on, the team needs to understand the difference and, where appropriate, return to an earlier arrangement with its dependencies intact. The sequence from objection to investigation, comparison and release makes learning useful to another person. They can understand which part changed, why it was chosen and what work the application should now do better.


Reading path: [Composing AI work](https://daostudio.in/collections/composing-ai-work/) > [From composition to a deliberate change](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/) > [From feedback to a version worth using](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/from-feedback-to-a-version-worth-using/)

Previous in journey: [Reading the work behind an answer](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/)
