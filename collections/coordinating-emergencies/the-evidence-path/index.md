Title: The evidence path

[Read HTML](https://daostudio.in/collections/coordinating-emergencies/the-evidence-path/)

Author: Harsh Joshi

<a id="the-evidence-path"></a>

# The evidence path

A device can report that it is connected while the person reviewing an event has no usable image. The network may still carry small messages while struggling with video. The camera may be sending a black frame. A recent upload may contain an old capture. Each situation leaves a different part of the service working and a different question unanswered.

The useful question is whether the reviewer can see enough, soon enough, to decide what to do. A running process cannot answer that. [YOJN Care](https://daostudio.in/yojn-care/) brings the problem into view through four flows between the premises and the reviewer, each carrying something different.

<a id="four-signals-four-different-questions"></a>

## Four signals, four different questions

A heartbeat says the device was reachable. Event metadata says something happened. Images and video let a person examine it. Device and network information help explain a failure. In the figure, A carries heartbeats, B event metadata, C media and D system information. Small heartbeats travel frequently; larger media arrives when an event needs it. They share a connection without answering the same question.

![One notification has metadata before its media is ready; media completion starts the review allowance, while heartbeats and vitals answer separate questions.](https://daostudio.in/collections/coordinating-emergencies/the-evidence-path/evidence-arrival-light.svg)

The metadata and media belong to the same notification. In this delayed-start option, the review allowance begins when the media is ready; lengths do not represent measured durations.

Separating the flows lets a notification arrive before its image. The review allowance can then begin when the image loads, or loading time can be added to it. Either way, waiting for evidence should not consume the time meant for judging it. A failed upload also needs its own investigation; blaming the reviewer will not restore the image.

<a id="several-flows-share-one-connection"></a>

## Several flows share one connection

Imagine a site whose connection has become severely constrained. Small periodic messages still arrive, an alert reaches the queue, and an image upload remains unfinished. Calling the site “online” accurately describes one exchange but conceals the reviewer's situation. Calling it wholly “offline” loses the information still available. A more useful account names what is working: the device was recently reachable, an event was reported, and its supporting media has not yet become available.

This distinction changes the design of degradation. An event notice may need to travel before a large media transfer completes. A smaller preview might support some judgments while a full stream is unavailable; other judgments may remain impossible. Reducing payload or reserving capacity for a control message can help a particular path, but neither creates missing visual detail. The product has to know which decision a degraded view can support, rather than give every delivered artefact the authority of the original evidence.

It also changes diagnosis. Power loss, a disconnected camera, a saturated uplink and an application failure can all produce a missing image. A timeout alone does not identify which happened. The system needs observations along the chain: capture, processing, transfer and presentation. That chain should help someone locate the failure without forcing the reviewer to become a network engineer before they can mark the evidence unavailable.

Delivery is only part of that chain. A camera moved during maintenance may keep streaming while losing the view the review procedure depended on. Poor placement, a noisy feed or a changed reference can leave an image technically available but unhelpful for the intended judgment. Device power and access to the camera source affect whether capture can happen at all. Installation therefore establishes part of the evidence arrangement: what is being observed, through which devices, and who can restore it when the physical setup changes. Network repair alone cannot recover a view that no longer contains the needed scene.

Google's SRE chapter on [monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) distinguishes internal instrumentation from checks of externally visible behaviour. For an evidence service, that suggests two complementary questions: do the components appear healthy, and can an authorised review session actually receive a usable result? An end-to-end check can expose a broken path that individual health checks miss. It still needs realistic conditions and cannot establish that every image has the context needed for a human judgment.

<a id="how-old-is-this-picture"></a>

## How old is this picture?

Suppose a frame was captured before a connection failed, received after reconnection and displayed immediately. For this timeline, take a shared trusted clock:

| Event | Time | Meaning at display |
| --- | --- | --- |
| Frame captured | 10:00:00 | The scene was observed three minutes earlier |
| Upload received | 10:02:58 | Transport completed two seconds earlier |
| Reviewer sees the frame | 10:03:00 | The presentation is new; the observation is not |

An interface showing only “received two seconds ago” invites a different interpretation from “captured three minutes ago.” Keeping both times gives the reviewer the relevant distinction. In a real multi-device path, the clock uncertainty also belongs beside the comparison; apparent precision cannot synchronise the devices by itself.

Age matters in relation to the decision. An older image might help establish how a scene changed, while being insufficient to show what is happening now. A live label cannot carry that judgment on its own. The interface needs to distinguish the latest available capture, a current stream and historical evidence, then make a gap in observation visible. Otherwise a freeze can look like a calm scene, and the absence of new information can acquire a meaning it never earned.

Reconnection brings ordering as well as freshness problems. A delayed alert may arrive after a newer correction. Several attempts to send the same request may all complete. Identifying the event and the relevant change lets the receiver reconcile these messages instead of treating each arrival as a new incident. Where a message initiates an external action, duplicate handling becomes more consequential than duplicate display: retrying the transport should not unknowingly repeat the commitment.

<a id="retrying-on-a-line-that-is-already-full"></a>

## Retrying on a line that is already full

Retries are useful when a failure is transient. They also consume resources. If every device immediately repeats a large transfer during congestion, recovery traffic can compete with the very evidence the service is waiting for. AWS's [guidance on limiting retries](https://docs.aws.amazon.com/wellarchitected/2024-06-27/framework/rel_mitigate_interaction_failure_limit_retries.html) explains the load created by retries, including compounded attempts across layers, and the role of backoff, jitter and a limit on attempts. Its warning about non-idempotent calls is especially relevant when repeating a request could repeat a side effect.

The service design question is what to recover first. A short message describing the missing evidence may be more immediately useful than another full upload. The latest relevant capture may matter more than an undifferentiated backlog. Historical material may still need retention for review, but it should not crowd out current work by accident. These choices depend on the incident, the available capacity and what the reviewer needs; an indiscriminate “retry until success” policy avoids that judgment rather than solving it.

Moving inference onto a local device changes this path without eliminating it. The device may continue detecting something while disconnected from a remote service. Human review, external notifications and coordinated response may still depend on connections outside it. Local compute can preserve a particular capability through a network interruption, but the product needs to identify that capability precisely. Installation and device maintenance remain part of whether it can continue operating at all.

Care's early Raspberry Pi route brought that operational burden into view. The hardware path was abandoned while installation, device management, manpower and logistics remained unresolved. A later Windows and vendor-software alternative brought recurring costs and integration dependence into the design. The general economic lesson is that a cheap detector can sit inside an expensive delivery arrangement. Provisioning devices, travelling to sites, restoring failures and maintaining compatible integrations all require resources. Comparing the detector's price with a hosted alternative while omitting those responsibilities compares different services. [Continuing-response economics](https://daostudio.in/collections/coordinating-emergencies/the-cost-of-continuing-response/) needs the whole usable path, including the work that keeps its physical endpoints in place.

What matters is the decision the available evidence can support. If an event is visible but its media is unavailable, the case remains [unresolved for a particular reason](https://daostudio.in/collections/coordinating-emergencies/the-cases-that-are-still-waiting/). The evidence path makes that reason available to the operation: a reviewer can identify what is missing, and the people maintaining the service can investigate where it disappeared. That is more useful than a green or red connection indicator. It connects the state of the system to the work somebody can now do.


Reading path: [Coordinating emergencies](https://daostudio.in/collections/coordinating-emergencies/) > [The evidence path](https://daostudio.in/collections/coordinating-emergencies/the-evidence-path/)
