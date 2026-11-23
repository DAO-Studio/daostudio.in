Title: Review a disputed answer

[Read HTML](https://daostudio.in/yojnai/review-a-disputed-answer/)

Rights holder: DAO Studio Private Limited

<a id="review-a-disputed-answer"></a>

# Review a disputed answer

A reviewer says the supplier allows fourteen days, while the purchasing assistant returned thirty. Before changing the model, find the agreement and intermediate work behind that answer. The error may be in the source, the extraction or the choice of agreement version.

**Note**

**Illustrative walkthrough.** This purchase example explains [YojnAI](https://daostudio.in/yojnai/)’s review and improvement design.

<a id="identify-the-contribution-being-questioned"></a>

## Find the agreement behind the disputed term

Start with the purchase, the application version and the agreement used for the disputed term. Check what the agreement said when the answer was produced, as well as whether it applied to this purchase.

| What you find | What to investigate |
| --- | --- |
| Another supplier's agreement was retrieved | Source selection |
| The applicable agreement says fourteen days, but extraction returned thirty | The input and operation that produced the unsupported value |
| An earlier agreement allowed thirty days | How the application chooses the applicable version |
| An older result replaced a corrected term | The request and revision associated with that late result |

Suppose the earlier agreement allowed thirty days, but the purchase was governed by its fourteen-day replacement. Extraction read its input correctly. Correct the draft to use the applicable agreement and keep that version beside the term. The improvement needs to address source selection; teaching extraction to return fourteen in every case would introduce another error.

<a id="keep-useful-work-while-reconsidering-its-dependents"></a>

## Keep useful work while reconsidering its dependents

The customer's delivery date can remain useful while the payment term changes. Reconsider the draft that uses the term, without asking for the date again or repeating unrelated work.

A late response still belongs to the request and source it answered. Keeping it in the history helps explain what happened. Treating it as current could undo the correction. The [composition account](https://daostudio.in/collections/composing-ai-work/from-composition-to-a-deliberate-change/agent-playbook-and-application/) follows those dependencies through the wider purchase workflow.

<a id="ask-what-should-improve"></a>

## Choose the change that fixes the answer

A useful change might correct a source, replace a tool, add a check, clarify an instruction, revise the workflow or adapt a model. A YojnAI feedback project keeps that question with the evidence being reviewed. Permission to review and the expertise behind a judgment remain separate.

For this purchase, compare two source-selection changes. One always prefers the newest agreement. The other chooses the agreement effective for the purchase date and returns that version with the term. Both could return fourteen days today; only the second has a reason to return thirty for a purchase governed by the earlier agreement. If the date is missing, it should ask rather than silently choose the newest document.

**Tip**

**Compare more than the reported failure.** Try the proposed change against both purchases, an unresolved date and a late response. Check that it returns the applicable term, preserves the source and does not overwrite a correction. Also consider what it costs elsewhere: better selection that drops the evidence location makes review harder, and a stronger model may slow ordinary requests.

The review now has a specific proposal: choose by applicability, keep the agreement's identity and leave extraction alone when it reads the source correctly. Review the proposal and its results before choosing a version for the application. [The application model](https://daostudio.in/yojnai/compose-inspect-and-improve/) places that choice within composition, deployment and feedback.


Reading path: [YojnAI](https://daostudio.in/yojnai/) > [Review a disputed answer](https://daostudio.in/yojnai/review-a-disputed-answer/)
