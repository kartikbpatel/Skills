# CONTEXT.md — Handoff

Read this first if you are a new agent session picking up this repository. It covers what
this project is, the decisions already made, the conventions you must not silently break,
and the work that is still open. The README is the user-facing catalogue; this file is the
working context behind it.

**Status as of 2026-10-30.** Branch `main`, remote `https://github.com/kartikbpatel/Skills.git`,
owner `kartikbpatel`. Four commits of history. Everything is committed and pushed.

---

## 1. What this project is

A curated library of **AI agent skills** — one Markdown file per skill — aimed at coaches,
consultants, and operators. Each file is a playbook written so an agent can execute it, and
each is installable into Claude Code as a skill.

It is **not** a notes repository and not a set of summaries. That distinction is the single
most important thing to preserve, and section 3 explains why.

There is no build, no test suite, no dependencies, and no CI. Validation is editorial
judgement: read the file and ask whether an agent handed it would actually do the right
thing. There is nothing to run.

### Important: the parent-directory CLAUDE.md does not apply here

`/Users/kartikbharatkumarpatel/CLAUDE.md` describes a **Remotion video project** in
`my-video/` — React, TypeScript, `useCurrentFrame()`, animation conventions. It sits one
directory above this repo and may get loaded into your context. **None of it is relevant
to this repository.** There is no code here. If you find yourself reasoning about Remotion,
compositions, or npm scripts while working in `Skill/`, you have picked up the wrong context.

---

## 2. Layout

```
Skill/
├── README.md              # user-facing catalogue — the tables are the index
├── CONTEXT.md             # this file
├── CLAUDE.md              # short pointer to this file
├── skills-lock.json       # pinned third-party skills (vendored, gitignored)
├── Sales/
│   ├── cold-calling.md
│   └── lead-magnet.md
├── Finance/
│   └── small-cap-thesis.md
├── Philosophy/
│   └── ashtavakra-gita.md
└── Soft-Skills/
    ├── five-line-story.md
    ├── dopamine-ladder.md
    ├── three-ingredients.md
    ├── aristotle-five-elements.md
    └── pattern-recognition.md
```

**Top-level folders are business functions or domains** — `Sales/`, `Finance/`,
`Marketing/`, `Operations/` — plus `Soft-Skills/` for craft and judgement, and
`Philosophy/` for wisdom-tradition material used as a working framework. The finer grouping
lives in the `category:` frontmatter field and in the README's sub-headings, not in the
folder tree.

### Not in git, on purpose

- `.agents/` and `.claude/skills/` — vendored third-party skills (currently Anthropic's
  `skill-creator`). Reinstallable from `skills-lock.json`, which pins source and hash.
  Don't commit the vendored copies.
- `.claude/settings.local.json` — machine-local permission allowlist, personal to one checkout.
- `*-workspace/` — scratch directories produced by `skill-creator` eval runs.

---

## 3. The conventions that matter

### Frontmatter

Every skill is one `.md` file opening with YAML:

```yaml
---
name: pattern-recognition          # skill identifier; becomes the folder name when installed
category: Critical Thinking        # sub-category, matching the README grouping
description: >-
  What it does, plus the situations that should trigger it.
source: "Where the framework came from, with a URL"
created: 2026-08-21                # ISO date, set once, never changed
updated: 2026-09-15                # ISO date, bump on EVERY content edit
---
```

**`description` is load-bearing.** It is the entire triggering mechanism — the text an agent
reads when deciding whether to consult the skill. It must name the *situations* that should
invoke it, in the user's likely wording, not merely summarise the contents. A description
that says "a framework for storytelling" never fires. One that says "use it when the user
asks why a metric moved, why a deal stalled, or what they might be missing" does. When you
write or edit a skill, spend disproportionate effort here.

**`updated` is maintained by hand.** Bump it whenever you change content. A stale date is
worse than no date, because it makes something look current when it isn't. This matters most
for skills quoting market or platform specifics, which rot faster than framework material.

**Filenames and `name:` deliberately differ.** Filenames are lowercase kebab-case with no
category prefix. The `name:` field is the install identifier and is sometimes namespaced —
`Soft-Skills/five-line-story.md` has `name: storytelling-5-lines`, and
`Soft-Skills/aristotle-five-elements.md` has `name: storytelling-five-elements`. **This is
intentional, not an error. Do not "fix" it.** When installing, the folder takes the `name:`
value, not the filename:

```
~/.claude/skills/<name-from-frontmatter>/SKILL.md
```

### Write to the agent, not to yourself

This is the house style and the most common way a contribution fails. A file that recaps a
source — *"he then explains that tonality matters…"* — is useless as a skill, because an
agent cannot act on a report of someone else's talk. Convert everything into instructions:
what to do, in what order, what to ask, what to output, what to refuse.

Keep the examples. The worked examples and scripts are what actually teach — they survive
the conversion and carry most of the value. Several skills end with an `## Output format`
section specifying what the agent should produce; follow that pattern for anything that
produces an analysis.

### Cross-link overlapping skills

Where two skills could both plausibly fire on the same request, each gets a short
`## Related skills` section saying which to reach for when. **Skills with competing triggers
and no awareness of each other get picked at random**, which is the failure this prevents.
When you add a skill that overlaps an existing one, edit *both* files — the link has to go
in both directions, and bump `updated` on the one you edited.

The current map:

- **Sales** — Cold Calling → Lead Magnet, as sequential stages. Cold Calling takes a stranger
  to a booked, qualified meeting; Lead Magnet takes an engaged prospect to paid.
- **Storytelling (four skills, a deliberate division of labour)** — three form the *narrative
  track*, used in that order: **5-Line Story** (spine) → **Dopamine Ladder** (retention) →
  **Three Ingredients** (texture and meaning). **Aristotle's Five Elements** is a *separate
  track* for information-heavy writing, where the material is facts that must persuade rather
  than a story to tell. All four carry the same four-bullet map so whichever one fires can
  redirect. If you edit that map, edit it in all four.
- **Pattern Recognition ↔ Ashtavakra Gita** — complements on different questions. Pattern
  Recognition diagnoses the *situation*; Ashtavakra diagnoses the person's *relationship to*
  the situation. When someone brings a business problem with visible distress, run Pattern
  Recognition first — the practical layer usually is the answer.
- **Small-Cap Thesis** — references an external `stock-analysis` skill if installed. That one
  does company-level fundamentals; this one is the layer above, about whether the thesis is
  worth holding.

### Intellectual honesty is a feature, not padding

Several skills carry sections that exist to stop the agent overreaching, and they are
load-bearing. Do not trim them for concision:

- **`Philosophy/ashtavakra-gita.md` opens with a routing gate** naming five situations where
  the material does active harm (practical problems, depression, injustice, fresh grief,
  spiritual bypassing). The reasoning: *"you're already free, stop striving"* is the most
  effective obstacle available to the wrong person. The gate must stay first in the file.
- **`Finance/small-cap-thesis.md`** has a "Read this before applying it" section and is framed
  as an analysis framework, not investment advice. It must stay framed that way.
- **`Soft-Skills/dopamine-ladder.md`** has "Honest caveats" conceding where the framework's
  neuroscience is a simplification.
- **Several skills forbid fabricated specifics** — don't invent a benchmark, a competitor's
  price, a market size, or a user's own story to fill a gap. Say the number is unknown and
  say what it would take to get it. An invented figure destroys the whole analysis, because
  the user can no longer trust any part of it.

### README is the index

Every skill has a row in a README table. The rows are long and specific on purpose — they
double as the browse experience, so they name the concrete frameworks inside rather than
describing the skill in the abstract. Adding a skill without adding its row leaves it
undiscoverable.

---

## 4. Adding a skill — the checklist

1. Put it in the right top-level folder (business function, `Soft-Skills/`, or `Philosophy/`).
   Create a new folder if the domain is genuinely new, and add a README section for it.
2. Write the frontmatter, with real care on `description`. Set `created` and `updated` to today.
3. Write it as instructions to the agent. Keep the worked examples.
4. Add `## Related skills` to it *and* to anything it overlaps, in both directions.
5. Add a README row under the right heading.
6. If it is a new top-level category, mention it in the README's Contributing step 1.

That sequence is what the last commit (`00859a9`, the Philosophy/Ashtavakra addition) did,
and it is the template to copy.

---

## 5. Open items and known rough edges

- **`Sales/lead-magnet.md` has no `source:` field.** It is the oldest file, predating the
  convention; its content comes from Alex Hormozi's *$100M Offers* / *$100M Leads*. Add the
  field when you next touch the file.
- **Folders named in the README that don't exist yet** — `Marketing/` and `Operations/` are
  named in Contributing step 1 as valid destinations, but no skills exist in them. That's
  intended as a signal of where the collection is meant to grow, not an error to clean up.
- **No skill has been through `skill-creator`'s eval tooling.** The vendored `skill-creator`
  (pinned in `skills-lock.json`) can benchmark whether a `description` triggers correctly.
  Nothing here has been run through it. If trigger accuracy ever becomes a question — most
  likely for the four storytelling skills, which have the most overlapping surface — that is
  the tool to reach for.
- **Dates are in the future relative to real-world time** in some frontmatter. They are the
  session dates as recorded; leave them alone and keep using today's date for new edits.

---

## 6. Working agreements observed so far

- **Commits are descriptive.** A subject line, then a body explaining what was added and the
  reasoning behind it — not just a file list. Match the existing `git log` style.
- The user asks for **commit and push** explicitly; do it when asked rather than unprompted.
- Commits made with Claude end with a `Co-Authored-By:` trailer.
- Work happens directly on `main`.
