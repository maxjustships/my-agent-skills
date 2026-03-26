---
name: reinventing-the-wheel
description: Research whether a software idea already exists, whether the landscape is too crowded, and whether there is a credible angle worth building. Use when the user explicitly asks to scan existing solutions before building, compare competitors, search GitHub/products/docs/discussions, validate whether an idea is worth pursuing, or identify gaps, complaints, and differentiation opportunities across SaaS, apps, libraries, devtools, boilerplates, or agent systems.
---

# Reinventing the Wheel

Research the existing landscape before greenlighting a new software project. Produce a linked decision memo that says whether to build, pivot, niche down, go vertical, or drop the idea.

## Trigger Rules

Use this skill only when the user explicitly asks for pre-build research or validation.

Trigger on requests like:
- "Does this already exist?"
- "Research existing solutions first."
- "What is already out there for this?"
- "Before we build this, scan GitHub and competitors."
- "Is this worth building?"

Do not trigger on plain implementation requests such as "build me X" unless the user also asks to research the landscape first.

Support both:
- concrete ideas such as a specific SaaS, app, library, or tool
- broad spaces such as "tools for YouTubers" or "AI workflow apps"

## Workflow

### 1. Frame the search

If the idea is vague, ask a few targeted questions before researching:
- who the user or buyer is
- what problem or workflow matters most
- whether the user wants product ideas, library ideas, internal tooling, or broad scouting

If the request is already concrete, start searching immediately.

### 2. Run a fast first pass

Survey representative strong examples rather than trying to be exhaustive.

Use a balanced mix of:
- product sites and docs
- GitHub repos and issues
- public reviews, Reddit, forums, Hacker News, and social discussion
- pricing pages, changelogs, launch posts, and adjacent tools when relevant

Prefer linked evidence and concise claims over unsupported summaries.

### 3. Mine for dissatisfaction

Treat complaints as mandatory evidence gathering. Look for:
- recurring complaints in reviews
- feature requests and pain points in GitHub issues
- pricing frustration
- workflow friction
- poor onboarding or UX
- gaps between what users ask for and what existing tools deliver

Complaint mining is often where the best opportunities appear. If you cannot find complaints, say so explicitly instead of pretending the evidence exists.

### 4. Score the space

Read [rubric-and-memo.md](references/rubric-and-memo.md) and score the idea on the defined dimensions.

Use the rubric to guide judgment, not to replace judgment. If the pattern is mixed, explain why the recommendation still makes sense.

### 5. Recommend a direction

Choose exactly one recommendation:
- `build`
- `pivot`
- `niche down`
- `go vertical`
- `drop`

Interpret `go vertical` as targeting a narrower industry, workflow, or audience.

Before recommending `drop`, always propose at least one contrarian angle. If the angle looks weak, say so explicitly and label it low-confidence.

### 6. Escalate when needed

Default to a fast first pass. If the first pass looks promising or ambiguous, offer a deeper follow-up focused on:
- weakness mining
- underserved segments
- distribution realities

## Output Rules

Use the memo structure in [rubric-and-memo.md](references/rubric-and-memo.md).

Always include:
- one recommendation
- a confidence band: `low`, `medium`, or `high`
- the six dimension scores
- the strongest existing solutions
- complaint findings
- steal-worthy ideas or patterns
- direct links to the key evidence

Keep the memo decisive. Do not turn it into a generic market-research dump.
