Title: Reading the work behind an answer

[Read HTML](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/)

Author: Harsh Joshi

<a id="reading-the-work-behind-an-answer"></a>

# Reading the work behind an answer

A purchasing assistant says the supplier allows payment after thirty days. The reviewer opens the agreement and cannot find the term. The answer is fluent and the disagreement is clear, but where should the investigation begin? Perhaps the assistant read another agreement. Perhaps it added a term to the right one. Perhaps the term was correct when retrieved and changed before it reached the reviewer. The final sentence gives each possibility the same appearance.

[YojnAI](https://daostudio.in/yojnai/)’s tracing and feedback tools were meant to help with this problem: the same wrong answer can require different repairs. We need to follow the agreement into the application, see which term was extracted and find out what reached the reviewer. Then the complaint can tell the team where to look.

<a id="two-runs-that-end-in-the-same-wrong-answer"></a>

## Two runs that end in the same wrong answer

Take two hypothetical runs. In the first, retrieval selects another agreement with a similar name and extraction accurately returns its term. Asking extraction to become more careful would address the wrong part of the work; the source selection needs attention. In another run, the right agreement reaches the model and the term appears only in generation. Now the investigation has a particular step to examine, including the input, instruction and returned value.

Put the two paths beside the same final sentence:

| Recorded part of the work | Wrong source, faithful extraction | Right source, unsupported extraction |
| --- | --- | --- |
| Expected agreement | Supplier A, agreement v2 | Supplier A, agreement v2 |
| Retrieved agreement | Supplier B, agreement v1 | Supplier A, agreement v2 |
| Source term | Thirty days | Fourteen days |
| Extracted term | Thirty days | Thirty days |
| Final answer | Thirty days | Thirty days |
| First investigation | Why did retrieval select B? | Why did extraction return a term absent from A v2? |

The first path does not ask for a more faithful extraction; it asks for a different source selection. The second requires examining the extraction input and operation. If a third run records only the final sentence, neither investigation has that starting point. Logging becomes useful through the distinctions it preserves, not its volume.

<a id="what-a-call-log-and-a-step-trace-each-show"></a>

## What a call log and a step trace each show

YojnAI included API-call logging and records for steps within a run. An endpoint, time and response status describe the call; inputs, outputs and relationships between steps describe more of the composition. A processed request can still return a wrong answer, and a step tree shows only the events chosen for recording. A trace is a representation designed for particular questions, so its usefulness depends on what those questions require it to preserve.

**Caution**

**Logs can expose more than the answer.** What the record preserves shapes both the investigation and the exposure it creates. Omitting source identity can leave a reviewer unable to distinguish a correct extraction from the wrong agreement; retaining every input can preserve sensitive material the final answer never disclosed. The logging decision needs to follow the operation being investigated and the people who need to examine it. Enough context to locate the failure, with a defined purpose for retaining and accessing that context, is a more useful aim than treating the amount logged as a measure of diagnostic quality.

YojnAI’s own logging shows why these levels must remain separate. A central logger recorded one row per API call, while a partner application’s trace service stored callbacks with run and parent-run identifiers, inputs, outputs and feedback. Those rows could preserve contributions without guaranteeing a valid execution tree or a history of successive assessments. They therefore answer the narrower question of what was recorded, not whether the whole explanation and improvement loop worked.

The finance-research designs exposed a different class of failure: a calculation could mix a price date with another period’s share count, confuse equity with enterprise value, or lose a qualifier such as stock-based compensation while copying a definition. A richer trace helps only if it retains the relevant definition and source. More events cannot repair a calculation whose terms already mean the wrong thing.

<a id="one-explanation-for-the-engineer-another-for-the-operator"></a>

## One explanation for the engineer, another for the operator

An engineer may need to inspect the step that transformed a value. A business operator may need to know why that value is appropriate for the customer's situation. Giving both the same raw log leaves the operator to reconstruct the business meaning, while giving both a fluent explanation can leave the engineer without the execution evidence. The presentation follows the question each person is trying to answer.

A model's account of why it answered can be material to examine, but it is not a verified account of its internal process. A more modest explanation can be stronger: this statement comes from this source, this rule permits the proposed action, this assumption remains unresolved. It connects the result to something a person can assess without claiming access to every hidden computation. Showing the source excerpt, the tool response and the generated explanation distinctly lets the reader understand what each contributes.

<a id="one-run-can-raise-several-questions"></a>

## One run can raise several questions

YojnAI's intended feedback design allowed the same trace to be considered in more than one feedback project. Accuracy was one question; usefulness and appropriate disclosure were others. An answer could be correct and needlessly complicated, clear and unsuitable to disclose, or satisfactory to the immediate user while leaving the business task unfinished. Separate questions made those judgments actionable instead of compressing them into a rating whose meaning changed with each reviewer.

The reviewers also brought different kinds of knowledge and responsibility. Access to a feedback project did not establish expertise in a specialised result; expertise did not establish authority to change the customer's application. Identifying what each person was judging let the team use those contributions together. Disagreement could then point towards a real trade-off or a missing question, rather than become a contest over whose general score should prevail.

<a id="what-the-investigation-leads-to"></a>

## What the investigation leads to

An investigation gives the record its practical value. It may show that retrieval needs a better source, that a model requires a different instruction or that the customer process leaves an exception undefined. Sometimes the available trace cannot distinguish those possibilities. Improving that record can then be the relevant change: the next run should preserve the evidence needed to resolve the question, rather than append a plausible explanation to the missing part.

Tracing, explanation and evaluation contribute different parts of the improvement. The trace locates the operation; interpretation makes its evidence meaningful; evaluation asks whether the result was acceptable. Together they can turn a complaint into a source correction, a changed component or a clearer business decision. The investigation gives [the next version](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/from-feedback-to-a-version-worth-using/) something specific to address, so the change can be examined for the work it actually improves.


Reading path: [Composing AI work](https://daostudio.in/collections/composing-ai-work/) > [From composition to a deliberate change](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/) > [Reading the work behind an answer](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/reading-the-work-behind-an-answer/)

Previous in journey: [An agent, a playbook and an application](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/)

Next in journey: [From feedback to a version worth using](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/from-feedback-to-a-version-worth-using/)
