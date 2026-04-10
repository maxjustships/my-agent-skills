---
name: omg-navigator
description: A specialized guide for the `oh-my-gemini-cli` harness. Use when the user needs help navigating the multi-agent workflow, selecting the right `/omg:*` commands, or understanding the current stage of their task. It provides proactive suggestions, explains command sequences, and helps manage the "Single Source of Truth" (SSoT) across complex sessions.
---

# OMG Navigator

The `omg-navigator` is your expert guide for the `oh-my-gemini-cli` (OmG) harness. Since OmG is a manual, role-driven orchestration layer, this skill helps you decide which commands to run and when, ensuring a smooth transition between workflow stages.

## Trigger Rules

Use this skill when the user asks for guidance on using the OmG harness or its commands.

Trigger on requests like:
- "How do I use this harness?"
- "What should I do next in OmG?"
- "Help me with the /omg commands."
- "What stage are we in?"
- "Explain the OmG workflow."

Do not trigger for general coding or research tasks that don't involve the OmG harness itself.

## Workflow

### 1. Assess the State
Start by identifying where you are in the OmG lifecycle. Check:
- Current active agents (`/omg:status`)
- Taskboard progress (`/omg:taskboard`)
- State files in `.omg/state/` (if accessible)

### 2. Identify the Current Phase
Map the current state to one of the OmG phases:
- **Discovery**: Unclear requirements or ambiguous intent.
- **Planning**: Defining milestones, risks, and PRDs.
- **Assembly**: Building or adjusting the agent team.
- **Execution**: Implementing code or content.
- **Verification**: Running tests and quality gates.
- **Fixing**: Addressing regressions or failures.

### 3. Recommend the Next Command
Provide the most logical next step using the `/omg:*` namespaced commands or `$` skills.

Common sequences:
- **Starting a task**: `/omg:intent "task description"` -> `/omg:doctor team`
- **Ambiguous task**: `$deep-dive "task description"` -> `/omg:intent`
- **Ready to plan**: `$plan "task description"` or `/omg:team-plan`
- **Ready to build**: `/omg:team-assemble` -> `/omg:team`
- **Continuing work**: `/omg:loop` or `/omg:taskboard`

### 4. Provide Command Syntax
Always output the exact command for the user to copy and run. Include a brief explanation of what the command does.

Example:
> **Recommended Step:** Define your core objective.
> ` /omg:intent "Refactor the authentication module for better error handling"`
> *This locks in the "North Star" for all agents in the session.*

### 5. Offer Alternatives
If the primary path is blocked or the user wants more control, suggest an alternative.

Example:
> **Alternative:** If you want to refine the team first:
> ` /omg:team-assemble "Refactor the authentication module"`

### 6. Verify and Loop
Remind the user to check the status after running a command or to use `/omg:loop` if the task is multi-stage.

## Output Rules

- **Directive & Concise**: Avoid long-winded explanations. Focus on "What" and "Why."
- **Command-First**: Place the recommended command prominently.
- **Context-Aware**: Reference the current task or state if known.
- **Safety First**: Remind the user about the `/omg:doctor` command if they encounter issues.

## Reference: Primary Command Map

- **Status**: `/omg:status`, `/omg:hud`, `/omg:doctor`
- **Orchestration**: `/omg:intent`, `/omg:team-assemble`, `/omg:team`, `/omg:loop`
- **State**: `/omg:workspace`, `/omg:taskboard`, `/omg:recall`, `/omg:memory`
- **Policy**: `/omg:model`, `/omg:approval`, `/omg:reasoning`, `/omg:optimize`
- **Hooks**: `/omg:hooks`, `/omg:hooks-validate`, `/omg:hooks-test`
