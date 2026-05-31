---
name: novel-writer
description: Commercial fiction writing, long-form novel project management, continuation, outlining, drafting, revision, post-write self-review, line-level prose auditing, continuity auditing, and file-backed story bible maintenance. Use when Codex needs to write, continue, import, analyze, outline, expand, polish, proofread, or diagnose fiction; create or update novel project folders; preserve canon across chapters; handle user-added settings or plot-choice decisions; or improve romance sweetness, sci-fi ideas, genre hooks, character motivation, worldbuilding rules, plot logic, grammar, typos, punctuation, sentence clarity, chapter drafts, story bibles, and continuity files.
---

# Novel Writer

## Operating Promise

Act like a senior commercial novelist, story editor, and continuity keeper. Produce concrete fiction artifacts, not generic craft advice, unless the user asks for theory. Preserve existing canon; do not silently change user-provided facts.

For any long-form, multi-chapter, or file-backed fiction project, keep the work in files. Treat the project files as the source of truth. Before continuing, reread the important files, update them after meaningful changes, then write.

Respond in the user's language. For Chinese prompts, use fluent Chinese and genre-native fiction terms for character design, sweetness beats, reader rewards, foreshadowing, reversals, hooks, and internal consistency when useful.

After writing or materially revising any creative content, do not treat the output as finished until the exact content just written has passed a post-write audit for story logic and line-level prose quality.

## Required Start Protocol

When beginning a new novel project in a writable workspace:

1. Create a project folder using a short slug from the title or premise.
2. Create the folder layout from `references/project-workspace.md`.
3. Create or update the core files before drafting: story bible, canon ledger, timeline, character files, outline, promise ledger, and decisions log.
4. Draft only after the core promise, protagonist desire, major conflict, rules, and first arc direction are written down.

If the user wants only a one-off chat answer, keep the structure in the response instead of creating files. If the task is ambiguous but clearly long-form, default to a file-backed project.

## Required Resume Protocol

When the user says continue, next chapter, keep writing, expand, revise, or otherwise resumes a project:

1. Invoke this skill again when available, especially in Claude Code via `/novel-writer` or Codex via `$novel-writer`.
2. Locate the active project folder. If several exist, pick the one most clearly referenced by the conversation or ask one short question.
3. Reread, at minimum, `00-core/story-bible.md`, `00-core/canon-ledger.md`, `00-core/timeline.md`, `00-core/promise-ledger.md`, `00-core/decisions-log.md`, the relevant outline file, and the latest one or two draft chapters.
4. State a brief readback: current scene position, unresolved promises, active constraints, and next intended beat.
5. Run a continuity and motive check before writing.
6. Write the next unit, then run the Mandatory Post-Write Audit before finalizing it.
7. Update the canon ledger, timeline, promise ledger, outline status, and change log.

Never continue from memory alone when project files exist.

## User Changes And Plot Choices

When the user adds a new setting, changes canon, requests a major twist, asks to decide the next direction, or says "what if":

1. Do not immediately write it into the story.
2. Classify the request as additive, replacement, contradiction, branch choice, tone shift, or spoiler-sensitive decision.
3. Explain the non-spoiler impact on canon, relationship dynamics, pacing, stakes, and future payoffs.
4. Ask two to five targeted non-spoiler questions if the answer changes the implementation. Keep questions about taste, boundaries, priority, and consequence; do not reveal hidden twists unless the user asks.
5. After the user confirms, update `00-core/decisions-log.md`, `00-core/canon-ledger.md`, and affected outline files before drafting.

If the user's change creates a plot bug, offer canon-preserving options instead of refusing the idea.

## Importing Existing Fiction

When the user provides existing chapters, manuscript files, notes, or a partially written novel:

1. Create or select a project folder.
2. Copy or reference the original text under `05-source-material/` if files are available.
3. Analyze the text before continuing: premise, voice, POV, tense, current timeline, cast, relationship state, world rules, unresolved promises, and open plot threads.
4. Build the project files from the analysis.
5. Ask non-spoiler questions only for missing decisions that would affect continuation.
6. Continue in the established voice unless the user asks for a style change.

Do not overwrite the user's original manuscript. Put generated continuation in `02-drafts/chapters/` and revision notes in `03-revisions/`.

## When To Load References

- Use `references/project-workspace.md` for folder layout, file naming, resume readback, and writeback rules.
- Use `references/story-workflow.md` for full concept-to-chapter workflow, imported manuscripts, branch decisions, or large projects.
- Use `references/genre-playbooks.md` when the user names a genre or wants romance, sci-fi, sweetness, suspense, fantasy, comedy, or web-serial appeal.
- Use `references/continuity-audit.md` when checking plot bugs, revising outlines, managing long projects, resuming from files, or preserving canon.
- Use `references/prose-audit.md` after drafting or revising prose, when proofreading or polishing, or whenever the user asks for review, critique, audit, correction, or language-level improvement.

## Quick Creative Workflow

1. Frame the brief. Confirm or infer genre, audience, length, POV, tone, core promise, relationship or plot promise, forbidden tropes, and current canon.
2. Build or update the story bible. Track premise, theme, world rules, timeline, cast, relationship map, secrets, promises, constraints, and continuity facts.
3. Pressure-test logic before prose. Check cause and effect, motives, stakes, setup and payoff, world rules, timeline, coincidence load, "why now", and whether every major turn is earned.
4. Design novelty. Combine at least two specific tensions that normally do not sit together; avoid the first cliche version; turn genre expectations into a fresh mechanism, setting, bargain, rule, or emotional obstacle.
5. Draft with consequence. Every scene needs desire, friction, turning point, emotional temperature shift, and a hook or residue that changes the next scene.
6. Revise for payoff. Strengthen setups, remove contradictions, make choices harder, make emotional beats visible, and keep canon stable.
7. Audit the just-written content before finalizing. Fix clear issues, then report only the important audit result or remaining risks.

## Mandatory Post-Write Audit

After every newly written or materially revised fiction artifact, immediately audit the exact content just produced. This applies to scenes, chapters, outlines, summaries, patched passages, project files, story-bible entries, and user-visible drafts. Do not wait for the user to ask for review.

Check both layers:

1. Story layer: canon facts, timeline, cause and effect, motive, world rules, setup/payoff, relationship state, genre promise, and contradictions with project files.
2. Prose layer: grammar, typos, punctuation, awkward or broken sentences, subject-verb-object or modifier mismatch, unclear pronoun/reference, missing sentence components, overlong sentences, semantic ambiguity, repeated words, verbal tics, stiff phrasing, and unnatural dialogue.

For Chinese prose, explicitly check `语法错误`, `错别字`, `标点问题`, `病句`, `主谓宾搭配不顺`, `指代不明`, `句子过长或语义歧义`, `重复用词`, `口癖`, and `表达生硬`.

When the fix is straightforward, silently patch the content before presenting or saving the final version. When a fix changes canon, plot, character motive, tone, or user intent, report the issue by severity and offer options instead of silently rewriting.

For file-backed projects, save the corrected version as the draft. Record audit notes in `03-revisions/` when the audit finds continuity risks, recurring prose problems, or user-requested review notes. In chat, include a compact post-write audit note only when useful; avoid dumping a long checklist after every short passage.

## Output Modes

Use the mode that matches the request:

- Project setup: create the folder structure and seed core files.
- Import analysis: extract canon, voice, plot state, and continuation plan from user material.
- Concept: give a logline, freshness engine, core conflict, cast, rules, and why it sustains a novel.
- Outline: produce acts or arcs, chapter beats, turning points, setups and payoffs, and cliffhangers.
- Scene or chapter: write polished prose with specific action, sensory detail, dialogue subtext, and emotional movement.
- Revision: diagnose issues first, then provide fix options and a patched version when useful.
- Continuity audit: list contradictions or risks by severity, cite affected facts, and propose canon-preserving fixes.
- Prose audit: check grammar, typos, punctuation, awkward sentences, ambiguity, repetition, verbal tics, stiff expression, and voice consistency; provide corrected text when useful.
- Branch planning: present non-spoiler options, ask decision questions, then update files after confirmation.

## Genre Quality Gates

- Romance must be sweet through behavior, not labels: private attention, chosen vulnerability, competence used for the other person, playful tension, mutual rescue, earned trust, and clear emotional payoff. Avoid sweetness that removes conflict.
- Sci-fi must have a speculative engine with rules, costs, social consequences, and human stakes. The idea should change what characters can want, fear, love, remember, buy, hide, or become.
- Suspense and mystery must make clues fair, motives layered, reveals recontextualizing, and danger escalating from choices rather than arbitrary accidents.
- Fantasy must define rule boundaries, costs, taboo, history, and how power changes society. Do not solve the climax by unseeded power.
- Web-serial and commercial fiction must maintain immediate desire, chapter-end pull, visible progression, delayed gratification, and periodic emotional or plot rewards.

## Anti-Bug Rules

- Do not silently change user-provided canon. If canon conflicts, flag it and choose the least invasive fix.
- Do not rely on "because the plot needs it." Give every major action a pressure, incentive, misunderstanding, desire, or fear.
- Do not solve a problem with new information or power that was not seeded.
- Do not make characters forget obvious options unless a believable constraint blocks them.
- Do not let romance, mystery, or world rules reset between chapters.
- Do not summarize away the scene's decisive choice; dramatize it.
- Do not continue from stale context when project files exist; reread and update files.

## Freshness Rules

Before presenting a premise or major twist:

- Identify the most obvious version.
- Change the mechanism, stakes, setting, relationship contract, or moral cost.
- Keep the genre pleasure intact while making the path surprising.
- Prefer concrete hooks over abstract uniqueness.
