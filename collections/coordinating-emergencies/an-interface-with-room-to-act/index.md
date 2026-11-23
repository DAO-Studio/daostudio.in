Title: An interface with room to act

[Read HTML](https://daostudio.in/collections/coordinating-emergencies/an-interface-with-room-to-act/)

Author: Harsh Joshi

<a id="an-interface-with-room-to-act"></a>

# An interface with room to act

A person asking for help may have one hand free, little time and no interest in learning an application. The reviewer needs to understand what happened and what they can do next. Both depend on an interface that makes the action clear without promising more than has happened.

[YOJN Care](https://daostudio.in/yojn-care/) connects one-handed SOS and High Alert actions with the people reviewing them. An SOS says somebody is asking for help; a camera alert supplies an observation to investigate. Neither tells the whole story, and an SOS can be activated accidentally. The interface has to carry that difference from the first gesture into the review.

<a id="from-the-first-gesture-to-what-the-service-has-received"></a>

## From the first gesture to what the service has received

Imagine a person opening an assistance interface with one hand while trying to leave an unfamiliar place. The immediate action should be easy to find and physically usable. If it sits behind several screens, the product is asking for attention the situation may not allow. Yet making it prominent does not settle when a gesture becomes a request, whether the person can correct it or what the service has actually received. Those questions belong together: speed of access is useful when the user can also understand the consequence.

A button that activates on the first touch and one that activates when the finger is released leave different opportunities to recover from a mistaken gesture. W3C's [pointer-cancellation criterion](https://www.w3.org/WAI/WCAG22/Understanding/pointer-cancellation.html) recognises this distinction for single-pointer web interaction, including completion on release, abort and undo. It does not prescribe a universal emergency gesture. The interaction still needs to be tested with its users and constraints. A long press, for example, may reduce some accidental touches while making the action harder for somebody who cannot maintain contact.

The request's progress needs equally careful language. A compact state account can guide the design:

| Displayed state | What has happened | What it must not imply |
| --- | --- | --- |
| Trying to send | The local interface is attempting transmission | That the service received the request |
| Received | The service acknowledged the request | That a person accepted the response work |
| Review accepted | A reviewer accepted the relevant work | That assistance arrived |
| Withdrawal requested | A correction was submitted | That every earlier action has been reversed |

These messages may arrive at different times. A spinning indicator that quietly becomes a reassuring tick can conceal the difference, particularly when the network drops after the initial action. The person needs to know what happened, rather than interpret the animation as a promise of assistance.

That feedback must reach people who do not see the screen in the same way. W3C's [status-message guidance](https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html) explains how qualifying web status updates can be exposed to assistive technology without moving focus. The broader design problem is continuity: a request should remain understandable through changes in attention, perception and connection. Announcing a state is useful only when the state itself has an honest meaning.

<a id="care-state-clock"></a>

## What a label and a clock mean

The personal-request code defined `PENDING`, `DELIVERED` and `READ` notification labels, separately from an SOS’s `START` and `STOP`. Their implementation is a warning about names: the SOS save path wrote `DELIVERED` **before** attempting the push notification, and listing notifications changed their stored state to `READ`. The push result was recorded separately. Neither label proves that a person saw the request, accepted responsibility or dispatched help.

The personal-request labels and the monitoring design’s clocks answer different questions: what has been recorded, and how long the reviewer has to act. Operator pickup was due before 90 seconds and the work had to be closed before 105; the manager’s corresponding windows were 60 and 75 seconds. A missed operator response passed to the manager; a manager timeout passed to the community as suspicious. For media loading, the design allowed either delaying the timer’s start or adding the delay to its allowance. The table sets the labels and the clocks side by side; where the page’s controls are available, they work the delayed-start variant and show the delay.

| Event | Stored label or design consequence | What remains unknown |
| --- | --- | --- |
| Notification row saved, before push attempt | `DELIVERED` | Whether transport or a recipient received it |
| Notifications listed | `READ` | Whether a person understood or accepted the work |
| Personal SOS started or stopped | `START` or `STOP` | Whether every recipient acted on the latest state |
| Operator not picked up before 90 seconds | Proposed manager handoff | Whether the next person is available |
| Picked up, not closed before 105 seconds | Proposed manager handoff | Whether evidence or another dependency delayed the judgment |

<a id="correcting-an-accidental-request-after-it-has-been-sent"></a>

## Correcting an accidental request after it has been sent

**Caution**

**Cancellation may need a continuing response.** Suppose the person realises the request was accidental and cancels it. Before transmission, cancellation may stop the local operation. After receipt, it is a new piece of information for the service. After someone has begun an external action, that action may have its own withdrawal process. A cancelled screen cannot make the earlier request cease to have existed.

The interface can carry the correction forward: when it was requested, whether the service received it and whether a reviewer acknowledged the change. It can also distinguish an intended withdrawal from a confirmed one. This is especially important after reconnection, when delayed messages may arrive in an unexpected order. A later view should not quietly restore an old active state simply because an earlier message finished travelling. The design question is how to keep the evolving request coherent across the people and systems holding it.

Configuration creates another kind of interruption. A missing contact, disabled permission or unavailable connection may prevent a particular action. An urgent interface should make the obstacle specific and take the person towards the relevant correction where that is possible. A general “setup incomplete” message hides the actual problem. Equally, a setup checklist presented as a prerequisite for every request can trap the person in administrative work at the moment they need a usable path. Which limited actions remain possible under an incomplete setup is a product decision that has to be explicit.

<a id="the-reviewer-has-a-different-interface"></a>

## The reviewer has a different interface

On the receiving side, selecting the next incident and deciding what it means are separate movements. A queue helps allocate attention; a review view helps interpret evidence. Mixing them can encourage a reviewer to settle a label while merely trying to move the queue along. Relevant context includes the kind of request, available observations, their age, prior actions and the commitments already accepted. More panels are useful only if they help someone answer one of those questions.

Consider two constructed events: a deliberate request waiting for acknowledgement and an automatic alert with an incomplete camera view. Their visual presentation should preserve the difference in origin and missing information. Giving both a red tile marked “emergency” makes them easier to count but harder to understand. Conversely, a very elaborate category tree can make urgent work slow to find. Priority rules need a reason grounded in the response arrangement and actual evaluation, not just an attractive ordering of labels.

Care's people view also separated event state from relationship affinity. Its proposed ordering put an unattended SOS ahead of an active SOS, followed by the high-alert states; family, friend and co-worker relationships ordered people within an event class rather than overriding it. The design idea is that a close relationship and work needing attention now answer different questions. In a constructed view, an unattended request from a co-worker should not disappear beneath routine activity from a favourite contact simply because that contact is closer to the user. The exact ranking still needs evaluation against the intended operation. A relationship label can help somebody recognise a person, but it neither establishes response competence nor grants permission to act for them.

Industrial alarm design offers a neighbouring principle. The UK's HSE [alarm-management guidance](https://www.hse.gov.uk/humanfactors/topics/alarm-management.htm) relates alarms to a defined operator response and the time available to make it. Its context is process operations, not a validated priority scheme for personal emergencies. The transferable question is whether a signal directs someone towards meaningful work. An attention-grabbing alert with no actionable context consumes the same scarce attention that the service depends on.

The final interface is therefore larger than the emergency button. It includes the correction, the acknowledgement, the evidence view and [the transition into accepted work](https://daostudio.in/collections/coordinating-emergencies/who-carries-the-incident/). The person asking for help can understand what has reached the service; the reviewer can see what remains uncertain and which commitment is theirs to carry. A well-shaped interface makes room for both actions, with display states that keep their different meanings intact.


Reading path: [Coordinating emergencies](https://daostudio.in/collections/coordinating-emergencies/) > [An interface with room to act](https://daostudio.in/collections/coordinating-emergencies/an-interface-with-room-to-act/)
