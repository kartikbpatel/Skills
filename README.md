# Skills

A curated collection of AI agent skills for coaches, consultants, and e-commerce entrepreneurs. Each skill is a structured playbook you can plug into Claude Code to get expert-level guidance on demand.

---

## Skills Directory

### Sales

Scripts, frameworks, and systems to convert leads into paying clients.

| Skill | What You Get |
|-------|-------------|
| [Lead Magnet](Sales/lead-magnet.md) | A complete sales system built on Alex Hormozi's $100M Offers philosophy. Includes **ready-to-send payment collection messages**, a **full closing call script** with objection handling for every scenario, **3-step LinkedIn follow-up sequences** to re-engage cold prospects, **8 lead magnet ideas** tailored for coaches/consultants, and a **nurturing cadence** that alternates value and conversation so you never come across as pushy. Use this when prospects have said yes but haven't paid, when leads go cold after connecting, or when you need a structured system to turn interest into revenue. |

### Soft Skills

The judgment and communication craft that doesn't show up in a playbook but decides whether the playbook works.

#### Storytelling

Four skills that divide the work rather than compete. Three form the **narrative track**, used in that order for a script or talk — **5-Line Story → Dopamine Ladder → Three Ingredients**: spine first, then retention, then texture. The fourth is a separate track for **information-heavy writing**, where the material is facts that have to persuade rather than a story to tell.

| Skill | What You Get |
|-------|-------------|
| [5-Line Story](Soft-Skills/five-line-story.md) | **The structural spine.** Tim Runia's method: reduce any story to exactly five lines — Situation, Desire, Conflict, Change, Result — before writing a word of script, slide, or outline. Includes worked examples, the **5 → 10 → 20 → full script** expansion path, the **connect-back test** for cutting material that serves no line, and a diagnosis for when the five lines *won't* come (which line is missing tells you what's actually wrong — "no Desire" is where most *my content is boring* problems live). Use it when there's no story yet, when a draft is shapeless, or when you're lost in the details mid-project. |
| [Dopamine Ladder](Soft-Skills/dopamine-ladder.md) | **Retention engineering.** Kallaway's six-level framework — Stimulation → Captivation → Anticipation → Validation → Affection → Revelation — for diagnosing exactly *where* attention leaks. Includes the question-engineering workflow, the **anticipation arc** (the highest-leverage level and the one most creators skip), head fakes and question stacking, short-form vs long-form differences, a level-by-level review checklist, and honest caveats about where the framework's neuroscience is a simplification. Use it when structure is sound but people still drop off. |
| [Three Ingredients](Soft-Skills/three-ingredients.md) | **Texture, delivery, and meaning.** Vinh Giang's three ingredients: Be Specific (the six-sense palette, one vivid detail per beat), Relive Don't Report (present tense is the highest-leverage edit available and costs nothing), and Share the Meaning (*"the reason I'm telling you this is because…"* — the sentence that turns a story into something the listener can use). Includes the **umbrella test** for anecdotes with no point, the punchline → point → relevance sequence, the **15-minute rule** for when *not* to tell a story, and how to unblock someone who thinks their life isn't interesting enough. Use it when a story is structurally fine but reads flat. |
| [Aristotle's Five Elements](Soft-Skills/aristotle-five-elements.md) | **Persuading with facts.** Palki Sharma Upadhyay's playbook for when you're not short of material — you're short of a reason for anyone to spend time on it. The five elements (**ethos, logos, pathos, metaphor, brevity**) used as a diagnostic: score a draft on each, fix the weakest, never average them. Includes the *katha/kathakar* premise (when facts are commodity, differentiation lives entirely in the telling), three pre-writing questions that stop competent writing coming out generic, the crucial **pathos-is-not-drama** distinction, the **orbit-shift** diagnostic for the four gravities that make everyone's content sound identical, and a full worked example rewriting launch copy. Use it for market analysis, exec briefings, board updates, launches, thought-leadership, or whenever writing feels dry and interchangeable. |

#### Critical Thinking

| Skill | What You Get |
|-------|-------------|
| [Pattern Recognition](Soft-Skills/pattern-recognition.md) | **Judgment when the first plausible answer is wrong.** Five diagnostic lenses — People, Systems, Temporal, Data, Market — routed from the symptom, so you run the one that fits instead of all five. Enforces the discipline that does the real work: **three explanations minimum, one of them boring** (tracking bug, seasonality, one person's decision); a **kill-test** naming what would disprove the leading hypothesis; claims labelled observed / inferred / assumed so you can see where evidence ends and reasoning starts; and controllable separated from external. Use it for "why did this metric move," root-cause work, pre- and post-mortems, forecasts, positioning calls, or any "what am I missing." |

---

## How to Use

1. Browse the skill you need from the tables above.
2. Open the `.md` file for the complete frameworks, scripts, and templates — all copy-paste ready.
3. To install as a Claude Code skill, copy the file to `~/.claude/skills/<skill-name>/SKILL.md`, where `<skill-name>` is the `name:` field in the file's frontmatter (e.g. `storytelling-dopamine-ladder`, not the filename).

The Soft Skills entries are written as instructions to the agent rather than notes to yourself, so they work as installed skills and as reference reading.

## Conventions

Every skill is a single `.md` file with YAML frontmatter:

```yaml
---
name: pattern-recognition          # skill identifier; the folder name when installed
category: Critical Thinking        # sub-category, matching the README grouping
description: What it does, plus the contexts that should trigger it.
source: "Where the framework came from, with a URL"
---
```

The `description` is the whole triggering mechanism — it's what the agent reads when deciding whether to consult the skill, so it needs to name the situations that should invoke it, not just summarise the contents.

Filenames are lowercase kebab-case with no category prefix; the category lives in frontmatter and in the README grouping.

## Contributing

To add a new skill:

1. Put it in the right top-level folder — a **business function** (`Sales/`, `Finance/`, `Marketing/`, `Operations/`) or `Soft-Skills/` for craft and judgment. Set `category:` in the frontmatter to the sub-category you want it grouped under.
2. Write it as instructions to the agent, not as notes to yourself. A source recap that says *"he then explains…"* won't work as a skill — convert it into what to do, and keep the examples, since those are what actually teach.
3. Where two skills overlap, add a short **Related skills** section to each saying which one to reach for when. Skills with competing triggers and no awareness of each other get picked at random.
4. Add a row to the relevant table above.

---

Built for coaches and consultants who want systems, not guesswork.
