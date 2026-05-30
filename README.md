# Fictionist Skill

`novel-writer` is a Codex skill for writing and managing long-form fiction projects. It helps Codex act as a novelist, story editor, continuity keeper, and file-backed project manager for novels, serial fiction, imported manuscripts, outlines, revisions, and canon tracking.

## What It Does

- Creates structured novel project folders with a story bible, canon ledger, timeline, outline, draft folders, revision notes, and source-material tracking.
- Continues existing fiction from project files instead of stale chat memory.
- Preserves canon, character motivation, relationship state, timeline logic, and genre promises across chapters.
- Supports concept development, outlining, chapter drafting, revision, continuity audits, and branch planning.
- Includes focused reference guides for project workspace rules, story workflow, genre playbooks, and continuity auditing.

## Included Files

```text
novel-writer/
  SKILL.md
  agents/
    openai.yaml
  references/
    continuity-audit.md
    genre-playbooks.md
    project-workspace.md
    story-workflow.md
```

## Install

Copy the `novel-writer` folder into your Codex skills directory:

```powershell
Copy-Item -Recurse .\novel-writer "$env:USERPROFILE\.codex\skills\novel-writer"
```

Restart Codex if it was already running. After installation, invoke it with:

```text
$novel-writer
```

Example prompts:

```text
$novel-writer Create a cozy sci-fi romance novel project with a story bible and the first three chapter beats.
$novel-writer Continue the previous chapter after reading the project files and giving a short resume readback.
$novel-writer Audit this outline for character motivation gaps and timeline bugs.
```

## Development

Validate the skill before publishing changes:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" .\novel-writer
```

This repository keeps the installable skill source in `novel-writer/`. Local build outputs, zip packages, Codex local settings, and private manuscripts should stay out of version control.
