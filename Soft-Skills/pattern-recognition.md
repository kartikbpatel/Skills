---
name: pattern-recognition
category: Critical Thinking
description: Diagnose business and career situations through five pattern lenses — People, Systems, Temporal, Data, and Market — to find root causes, surface hidden variables, stress-test explanations, and turn observations into decisions. Use this skill whenever the user asks why a metric moved, why a deal stalled, why a launch failed or succeeded, what they might be missing, whether a trend will hold, how to position against a competitor, or how to read a stakeholder — and for any pre-mortem, post-mortem, forecast, or "should we do X" judgment call. Trigger it even when the user only describes a confusing outcome without asking a clear question, because the failure this skill exists to prevent is accepting the first plausible explanation.
source: "The Cutting Edge School — '5 Non-AI Skills That Pay More Than Your Degree' (https://www.youtube.com/watch?v=iuI5JlLkV9k)"
created: 2026-08-21
updated: 2026-09-15
---

# Pattern Recognition

Producing an explanation is cheap now. Producing the *right* explanation, and knowing how much to trust it, is not. Almost every expensive business mistake traces back to the same move: someone accepted the first plausible cause and acted on it.

This skill exists to stop that move. It works by widening the set of possible explanations before narrowing it, and by making every claim carry its own confidence level and its own kill-test.

## The division of labor

Be honest about what you can and cannot do here. You have breadth, recall, and the ability to generate hypotheses the user is too close to see. You do not have the room, the tone of voice, the private context, or accountability for the outcome.

| You do this | The user does this |
|---|---|
| Generate hypotheses **and** counter-hypotheses | Choose which one to believe |
| Name confounds, missing segments, missing data | Supply the context you can't see |
| Find historical and cross-industry analogues | Judge whether the analogue actually fits |
| Run the arithmetic, spot outliers and bad averages | Own the decision and its risk |
| Say what evidence would settle it | Go get that evidence |

This is why every analysis ends with **what the user has to check**. An analysis that reads as a verdict has quietly stolen a decision that isn't yours. An analysis that hands back a ranked hypothesis set plus a cheap next test has done the job.

## Step 1 — Pick the lens

Don't run all five. Route from the symptom, and say which lens you're using and why so the user can redirect you.

| The situation sounds like | Lens |
|---|---|
| A person or group is behaving in a way that doesn't add up; a deal stalls; a stakeholder resists; hiring, negotiation, buy-in | **People** |
| An outcome has multiple moving parts; a fix caused a new problem; "why did this break"; process and incentive design | **Systems** |
| "Is this real or hype?"; forecasting; a shift feels unprecedented; entering a new category | **Temporal** |
| A number moved; a dashboard looks wrong or too good; budget and ROI allocation | **Data** |
| Why customers buy, churn, or won't switch; pricing; positioning; competitor moves | **Market** |

Two lenses is common (a metric moved *because* an incentive changed → Data + Systems). Three is usually a sign you haven't found the question yet. When the situation is genuinely ambiguous, say which lens you're leading with and which you'd reach for next.

## Step 2 — Run the lens

### People patterns

What it sees: incentives, fears, and the gap between what someone says and what they want.

Ask, from the evidence available:
- What outcome does this person actually want — for the company, and for themselves?
- What are they afraid of? What does a bad outcome cost *them personally*?
- What did they avoid saying, deflect, or answer a different question than?
- Who decides, who influences, who can block, and who is merely informed?
- What would make saying yes *safe* for them?

The trap: treating a stated objection as the real one. Price objections are often risk objections; "we need more data" is often "I can't defend this to my boss." Name the stated objection and the likely underlying one separately, and mark which is which.

Strong output looks like a short read of each player's incentive, the objections likely to appear before they appear, and one adjustment to how the user frames the ask.

### System patterns

What it sees: how variables, incentives, and feedback loops connect — and where the first explanation is a symptom.

Ask:
- What changed? And **what else changed at the same time** that nobody is talking about?
- What are three candidate causes, including one boring one (a config change, a holiday, a person leaving, a tracking bug)?
- Which of these is a cause, and which is downstream of the same cause?
- What evidence would disprove the leading candidate?
- Which variables are controllable, and which are external?

When the situation has more than three moving parts, sketch the chain as text: `inputs → process → outputs → feedback`. Feedback loops are where intuition fails hardest, so call them out explicitly — a fix that improves the output but strengthens a loop that caused it will fail later and look like bad luck.

For anything not yet launched, run this backwards as a pre-mortem: assume it failed, and list the three most likely ways.

### Temporal patterns

What it sees: the structurally similar thing that already happened.

History doesn't repeat, but incentives, constraints, and human reactions to novelty do. Before any forecast, ask: **when has something structurally similar happened before?**

Build the analogue explicitly, and never skip the third row — an analogy without its differences is how confident forecasts go wrong:

| | |
|---|---|
| Situation | what's happening now |
| Analogue | the prior case |
| Similarities | which forces are the same |
| **Differences** | what's genuinely new (and whether it breaks the analogy) |
| Implication | what it suggests, and with what confidence |

Give forecasts as ranges with stated assumptions, not points. "Likely 6–18 months, assuming distribution stays gated" is useful; "this will take a year" is a guess wearing a suit.

The trap: forcing a flattering analogue. If the differences row is doing more work than the similarities row, say the analogy fails and drop it.

### Data patterns

What it sees: why a number moved, and what to do about it.

A chart shows *what* happened. The value is entirely in the *why* and the *so what*. Reporting the movement back to the user is not analysis.

Ask:
- What exactly moved, over what window, and by how much relative to normal variation?
- **Which segment, cohort, channel, or product drove it?** Aggregate numbers hide the answer almost every time — a flat total is often a large gain and a large loss cancelling out.
- Is this a real trend, seasonality, noise, a mix shift, or a measurement/tracking change? Rule out instrumentation before reaching for a business explanation; it is the single most common false alarm.
- Is an average hiding a skewed distribution? Would a median or a percentile tell a different story?
- What action follows — and what would the metric look like in two weeks if the action worked?

Where unit economics are in play, work in the chain that decisions actually hang on: CAC, conversion rate, AOV, retention/churn, gross margin, payback period, revenue per account. A metric that doesn't connect to one of these is usually a vanity metric; say so.

Estimate the magnitude before computing it. If your estimate and the calculation disagree by a lot, one of them is wrong, and finding out which is where the insight is.

### Market patterns

What it sees: what customers will actually pay for, and why they'd switch.

Customers buy to remove a problem, save time, save money, or make money. If a product's pitch doesn't land on one of those in a sentence, that's the finding.

For any product, feature, or offer, fill in:
- The customer's problem, in their words
- Their current workaround (the real competitor is usually a spreadsheet or doing nothing)
- The cost of doing nothing — if it's low, the deal will stall no matter how good the product is
- Time saved, money saved or earned, quantified if at all possible
- The reason to switch *now*, and the switching cost that offsets it

Then map the field on **better / faster / cheaper**. Strength on two is a real position; all three is rare and usually means the analysis is wrong or the money is going out the door somewhere.

Then look where competitors don't — "major in the minors." Durable advantage hides in small consequential friction: onboarding, support response, one missing integration, pricing legibility, reliability, trust signals. These are unglamorous and therefore unattended.

Close with one strategic move: either double down on a pattern the market already rewards, or introduce a deliberate pattern interrupt that changes what customers notice. Name which one and why.

## Step 3 — Cross-checks before you answer

These apply to every lens, and they're most of the value:

1. **Three explanations minimum, one of them boring.** A single hypothesis isn't analysis, it's a story. Include the mundane candidate — noise, seasonality, a tracking change, one person's decision — because it's frequently correct and always cheapest to rule out.
2. **A kill-test for the leader.** State the specific observation that would disprove your top hypothesis. If you can't name one, the hypothesis is unfalsifiable and you should say that rather than dress it up.
3. **Label your altitude.** Mark claims as observed, inferred, or assumed. The user needs to see where the evidence ends and you started reasoning, so they can audit the part that matters.
4. **Separate controllable from external.** Effort spent on external variables is waste, however well-analysed.
5. **Say what you don't know.** Missing data is a finding. Name the one or two things that would most change the conclusion.

## Output format

Match depth to the question. A one-line question gets a tight answer, not a five-section report; long structure on a small question is its own failure.

For a substantive diagnosis, this shape works:

```
**Lens:** [which, and why this one]

**What we know** — the observed facts, separated from interpretation

**Candidate explanations** — ranked, each with supporting evidence,
the evidence against it, and a confidence level

**Leading hypothesis** — and the single test that would disprove it

**What only you can check** — the 1–3 things requiring their access,
their room, their customers

**If it holds, do this** — the concrete next action, and the signal
that would show it working
```

Skip sections that would be empty. An honest "the data can't distinguish these two causes; here's the cheapest way to tell them apart" is a better answer than a ranked list built on nothing.

## Practice mode

When the user wants to *build* the skill rather than apply it to one case, the mechanism is reps on their own real material — not reading. Offer a rotation and act as the prompt and the critic:

| Day | Rep |
|---|---|
| Mon — People | Three recent conversations: motives, incentives, objections, signals missed |
| Tue — Systems | One outcome: draw the causal chain, list alternative explanations |
| Wed — Temporal | One prior market event, failure, or technology shift in their industry |
| Thu — Data | One metric movement: change, drivers, evidence, next action, on one page |
| Fri — Market | Five reviews, calls, or tickets: pains, desired outcomes, overlooked friction |

Monthly, score 1–5 per lens — but only against evidence, not feeling. People: did they predict the objection before the meeting? Systems: did the root cause hold up? Temporal: did the forecast land, and were the assumptions the ones that mattered? Data: did a metric change turn into an action with a measurable result? Market: can they say in one sentence why a customer would switch?

If a score has no proof attached, it's a 2.

## Failure modes

- **Confident narrative on thin evidence.** The most common and most expensive. Fluency reads as insight; hedge honestly instead.
- **Reporting instead of diagnosing.** Restating that revenue fell 12% is not analysis.
- **Generic advice.** "Improve onboarding" applies to everyone and helps no one. If the recommendation would survive being pasted into a different company's document, it isn't a finding.
- **Skipping the segment split.** Most data questions are answered by disaggregating, and most wrong answers come from not bothering.
- **Forced analogies.** A prior case that only rhymes gives false confidence in a specific number.
- **Taking stated reasons at face value.** In People and Market work, the stated reason and the real one are routinely different.
- **Fabricated specifics.** Never invent a benchmark, a competitor's price, or a market size to fill a gap. Say the number is unknown and say what it would take to get it — an invented figure destroys the whole analysis, because the user can no longer trust any of it.

## Related skills

- **[Ashtavakra Gita](../Philosophy/ashtavakra-gita.md)** — the complement for a different question. This skill diagnoses the *situation*: what caused the outcome, what's really going on, what to do next. That one diagnoses the person's *relationship to* the situation, and is for distress that outlives the cause — "revenue is fine and I still wake up at 4am." When someone brings a business problem with visible distress, run this one first; the practical layer usually is the answer, and reaching for non-dual framing on a solvable problem is a way of not solving it.
