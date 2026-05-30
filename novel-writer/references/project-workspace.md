# Project Workspace

Use this reference for file-backed novel projects, continuations, imported manuscripts, and long-running drafting.

## Default Folder Layout

Create this layout inside a project folder named from the title or premise:

```text
<novel-slug>/
  00-core/
    story-bible.md
    canon-ledger.md
    characters.md
    relationships.md
    timeline.md
    rules-and-constraints.md
    promise-ledger.md
    decisions-log.md
  01-outline/
    master-outline.md
    arc-map.md
    chapter-plan.md
    branch-options.md
  02-drafts/
    chapters/
    scenes/
    scraps/
  03-revisions/
    continuity-audits.md
    rewrite-notes.md
    change-log.md
  04-research/
    research-notes.md
  05-source-material/
    manifest.md
  99-exports/
```

Keep filenames lowercase and stable. Use chapter files like `chapter-001.md`, `chapter-002.md`, and scene files like `scene-001-market-meeting.md`.

## Core File Contracts

- `story-bible.md`: premise, genre promise, theme question, protagonist desire, opposition, stakes, ending direction if known.
- `canon-ledger.md`: confirmed facts only. Include names, ages, skills, secrets, rules, objects, places, injuries, relationship status, and facts that cannot change.
- `characters.md`: desire, fear, wound, mask, contradiction, skill, blind spot, voice, arc, and current state for each important character.
- `relationships.md`: attraction, debt, trust, rivalry, secrecy, power balance, emotional temperature, boundaries, and unresolved tension.
- `timeline.md`: dated or ordered events, travel time, deadlines, recovery time, communication gaps, and chapter placement.
- `rules-and-constraints.md`: technology, magic, legal, social, economic, family, school, workplace, distance, secrecy, or genre constraints.
- `promise-ledger.md`: mysteries, emotional debts, Chekhov objects, planted clues, delayed kisses, threats, vows, reversals, and required payoffs.
- `decisions-log.md`: user decisions, accepted changes, rejected options, open questions, and the reason each major direction was chosen.
- `master-outline.md`: act structure, major turns, midpoint, low point, climax logic, ending promise.
- `chapter-plan.md`: planned chapter beats, status, hooks, setups, payoffs, and next chapter target.
- `branch-options.md`: non-canon options under consideration. Move a choice to canon only after user confirmation.
- `continuity-audits.md`: dated checks with severity, issue, evidence, and fix.
- `change-log.md`: every generated chapter, major canon update, rewrite, or user-approved setting change.

## New Project Protocol

When starting from a blank idea:

1. Create the folder layout.
2. Write initial `story-bible.md`, `characters.md`, `rules-and-constraints.md`, and `master-outline.md`.
3. Write `canon-ledger.md` with only confirmed facts; mark unknowns in `decisions-log.md`, not canon.
4. Write the first chapter plan before drafting.
5. Generate chapter text into `02-drafts/chapters/`.
6. Update ledgers and logs after each generated unit.

## Resume Readback Protocol

Before continuing any existing project, reread:

- `00-core/story-bible.md`
- `00-core/canon-ledger.md`
- `00-core/characters.md`
- `00-core/relationships.md`
- `00-core/timeline.md`
- `00-core/promise-ledger.md`
- `00-core/decisions-log.md`
- `01-outline/chapter-plan.md`
- Latest relevant chapter files in `02-drafts/chapters/`

Then produce a short readback before drafting:

- Current position: where the story is now.
- Active constraints: rules, secrets, deadlines, relationship boundaries.
- Open promises: what must be paid off.
- Next beat: what should happen next and why it follows causally.

If files contradict each other, pause drafting and run a continuity audit first.

## Writeback Protocol After Generation

After writing a chapter, scene, outline section, or accepted change:

- Add new facts to `canon-ledger.md`.
- Add relationship movement to `relationships.md`.
- Add dated or ordered events to `timeline.md`.
- Add new setups, clues, emotional debts, and hooks to `promise-ledger.md`.
- Mark completed or changed beats in `chapter-plan.md`.
- Add a short entry to `03-revisions/change-log.md`.
- If a bug was found or fixed, add it to `03-revisions/continuity-audits.md`.

Do not bury canon only inside prose. If a fact matters later, write it to core files.

## User Decision Protocol

When the user adds a setting, asks to choose a route, or proposes a twist:

1. Put the idea in `01-outline/branch-options.md` or a temporary response section.
2. Classify it:
   - Additive: adds flavor or a subplot without breaking canon.
   - Replacement: changes an established fact.
   - Contradiction: conflicts with canon or timeline.
   - Branch: creates two or more future paths.
   - Tone shift: changes sweetness, darkness, pace, or target audience.
3. Ask non-spoiler questions before canonizing it:
   - What emotional effect should this create?
   - Should this raise stakes, deepen romance, create mystery, or change the protagonist?
   - How much should it affect the existing outline: light, medium, or major?
   - What should remain untouched?
4. After the user chooses, update `decisions-log.md`, affected core files, and outline files.

Never reveal hidden twists or future solutions while asking unless the user asks to see spoilers.

## Existing Manuscript Import

When the user provides existing fiction:

1. Preserve the original under `05-source-material/` or list it in `05-source-material/manifest.md`.
2. Extract:
   - Current premise and genre promise.
   - POV, tense, voice, pacing, paragraph style, dialogue habits.
   - Cast and relationship states.
   - Timeline and location chain.
   - World rules and constraints.
   - Open promises, clues, secrets, and unresolved emotional debts.
   - Last scene state and immediate next pressure.
3. Build or update core files from the extraction.
4. Create a continuation plan in `01-outline/chapter-plan.md`.
5. Continue in `02-drafts/chapters/` without overwriting source material.

If the manuscript is too long to read fully at once, sample beginning, recent chapters, endings of chapters, and any outline files first; then ask for or inspect the missing segments most relevant to continuation.
