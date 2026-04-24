# Meeting Notes to Jira Playbook

A practical playbook for turning meeting notes into Jira-ready execution artifacts.

This repository documents a simple rule: meetings should not end as text. They should end as decisions, open questions, and tasks that can move into delivery.

The workflow here assumes a Markdown-first environment:

1. Capture the raw transcript.
2. Convert it into a structured meeting note.
3. Normalize the outcome into a Jira-friendly task draft.
4. Push only the actionable parts into Jira.
5. Keep a link back to the source note so context is never lost.

This works especially well with Obsidian-based note systems and repositories like `markdown-jira-sync`.

## Why this matters

Many teams either:

- keep everything inside notes and lose execution discipline
- or push everything into Jira and lose the original reasoning

The better pattern is to keep both layers:

- notes preserve context
- Jira preserves ownership and delivery state

## Core operating model

### Layer 1: Meeting note

The meeting note should answer:

- what was discussed
- what was decided
- what remains unclear
- what needs to be done

### Layer 2: Jira-ready extraction

From the note, extract only the pieces that deserve tracking:

- implementation tasks
- investigation tasks
- product decisions that need follow-up
- risks that need explicit owners
- dependencies blocking delivery

### Layer 3: Jira issue creation

A Jira issue draft should be clear enough to execute without the full transcript.

At minimum it should contain:

- summary
- background
- scope
- open questions
- acceptance criteria or expected outcome
- links to the meeting note and related docs

## What should become a Jira issue

Good candidates:

- concrete engineering tasks
- integration work
- API changes
- analytics implementation
- documentation work with a clear deliverable
- follow-up investigations with a clear output

Bad candidates:

- vague ideas without next action
- unresolved brainstorming fragments
- pure transcript fragments
- long context dumps without an owner

## Recommended note-to-task pipeline

```text
Raw transcript
  -> structured meeting note
  -> extracted decisions and action items
  -> normalized Jira draft
  -> Jira issue
```

## Suggested folder structure

```text
Projects/
  Project Name/
    Meeting Notes/
    Task Drafts/
```

## Suggested meeting note sections

- Context
- Main topics
- Decisions
- Open questions
- Action items
- Risks / dependencies

## Suggested Jira draft structure

See [examples/jira_task_draft.md](./examples/jira_task_draft.md).

A practical format:

- Summary
- Background
- Problem
- Proposed scope
- Open questions
- Expected result
- Links

## Prompt pattern

Use a second-step prompt after the note is ready:

```text
Based on this meeting note, extract only the items that should become Jira issues.

Requirements:
- do not create issues for vague ideas
- group related action items into one task where appropriate
- keep each issue independently understandable
- include enough background to execute the work without reopening the full transcript
- preserve open questions when they block implementation
- return the result as structured Markdown suitable for Jira issue creation
```

## Relationship to tooling

This playbook is intentionally tool-agnostic at the method level, but it pairs well with:

- Obsidian for the note system
- Cursor for transcript-to-note conversion
- `markdown-jira-sync` for issue creation
- Confluence or internal docs for persistent specs

## Design principles

- notes are for context
- Jira is for execution
- not every bullet deserves a ticket
- tasks should be independent enough to survive handoff
- source links should always be preserved

## License

MIT
