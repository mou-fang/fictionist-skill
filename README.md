# Fictionist Skill / 小说写作 Skill

`fictionist-skill` packages the installable `novel-writer` skill for Codex and Claude Code. It turns the agent into a long-form fiction collaborator: novelist, story editor, continuity keeper, and file-backed project manager.

`fictionist-skill` 仓库打包了可安装的 `novel-writer` skill，可用于 Codex 和 Claude Code。它的目标是让智能体像商业小说作者、故事编辑、连续性管理员一样工作，尤其适合长篇小说、连载、已有稿件续写和复杂大纲管理。

## What It Is / 这是什么

The skill teaches an agent to:

- create structured novel project folders instead of keeping everything in chat memory;
- build and maintain a story bible, canon ledger, timeline, character files, outline, promise ledger, and decision log;
- continue chapters only after rereading the project files;
- preserve canon, relationship state, world rules, timeline logic, setups, payoffs, and genre promises;
- help with premise design, outlining, drafting, revision, continuity audits, and branch planning.
- run a post-write audit after generated content, including continuity, grammar, typos, punctuation, awkward sentences, unclear references, repetition, verbal tics, and stiff expression.

这个 skill 会指导智能体：

- 为长篇项目建立文件化工作区，而不是只依赖聊天上下文；
- 维护故事圣经、正史台账、时间线、人物档案、大纲、伏笔台账和决策记录；
- 在续写前先读取项目文件，避免“凭记忆续写”导致设定漂移；
- 稳定人物动机、关系状态、世界规则、时间线、伏笔回收和类型承诺；
- 支持创意设定、大纲设计、章节写作、修订、连续性审计和分支路线选择。

## Repository Layout / 仓库结构

```text
fictionist-skill/
  README.md
  novel-writer/
    SKILL.md
    agents/
      openai.yaml
    references/
      continuity-audit.md
      genre-playbooks.md
      project-workspace.md
      prose-audit.md
      story-workflow.md
```

Only the `novel-writer/` folder is the actual installable skill. The README explains how to install and use it.

真正需要安装的是 `novel-writer/` 文件夹。README 只是说明文档。

## Install In Codex / 安装到 Codex

Codex discovers user skills from your Codex skills directory. By default, that is:

- Windows: `%USERPROFILE%\.codex\skills`
- macOS/Linux: `~/.codex/skills`
- If you use `CODEX_HOME`, install into `$CODEX_HOME/skills`

Codex 通常会从以下目录读取个人 skill：

- Windows：`%USERPROFILE%\.codex\skills`
- macOS/Linux：`~/.codex/skills`
- 如果你设置了 `CODEX_HOME`，则安装到 `$CODEX_HOME/skills`

### Windows PowerShell

```powershell
git clone https://github.com/mou-fang/fictionist-skill.git
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
Copy-Item -Recurse -Force ".\fictionist-skill\novel-writer" "$env:USERPROFILE\.codex\skills\novel-writer"
```

### macOS / Linux

```bash
git clone https://github.com/mou-fang/fictionist-skill.git
mkdir -p ~/.codex/skills
cp -R fictionist-skill/novel-writer ~/.codex/skills/novel-writer
```

Restart Codex after installing if it was already running.

如果 Codex 已经打开，安装后建议重启一次，让它重新发现 skill。

## Install In Claude Code / 安装到 Claude Code

Claude Code skills use the same `SKILL.md` folder pattern. You can install this skill globally for your user account, or locally inside one project.

Claude Code 的 skill 也使用包含 `SKILL.md` 的文件夹结构。你可以全局安装，也可以只安装到某个项目里。

### Global Install / 全局安装

Install globally when you want the skill available in all Claude Code sessions.

如果希望所有 Claude Code 会话都能使用它，用全局安装：

#### Windows PowerShell

```powershell
git clone https://github.com/mou-fang/fictionist-skill.git
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills" | Out-Null
Copy-Item -Recurse -Force ".\fictionist-skill\novel-writer" "$env:USERPROFILE\.claude\skills\novel-writer"
```

#### macOS / Linux

```bash
git clone https://github.com/mou-fang/fictionist-skill.git
mkdir -p ~/.claude/skills
cp -R fictionist-skill/novel-writer ~/.claude/skills/novel-writer
```

### Project Install / 项目内安装

Install locally when you want the skill available only inside one writing or coding project.

如果只想在某个项目里使用，把它放到项目的 `.claude/skills/` 目录：

#### Windows PowerShell

```powershell
git clone https://github.com/mou-fang/fictionist-skill.git
New-Item -ItemType Directory -Force ".\.claude\skills" | Out-Null
Copy-Item -Recurse -Force ".\fictionist-skill\novel-writer" ".\.claude\skills\novel-writer"
```

#### macOS / Linux

```bash
git clone https://github.com/mou-fang/fictionist-skill.git
mkdir -p .claude/skills
cp -R fictionist-skill/novel-writer .claude/skills/novel-writer
```

Restart Claude Code after installing if it was already running.

如果 Claude Code 已经打开，安装后建议重启一次。

## How To Use In Codex / 在 Codex 中使用

In Codex, explicitly call the skill with:

在 Codex 里，可以直接这样调用：

```text
$novel-writer
```

Good prompts:

推荐提示词：

```text
$novel-writer Create a file-backed fantasy romance novel project. Start with the story bible, main cast, rules, and a 10-chapter outline.

$novel-writer Continue chapter 4. First reread the story bible, canon ledger, timeline, promise ledger, and the latest chapter. Give me a short readback before drafting.

$novel-writer Audit this outline for timeline bugs, weak motivation, unearned reveals, and missing setup/payoff.
```

中文示例：

```text
$novel-writer 帮我创建一个文件化的甜宠科幻长篇项目，先写故事圣经、主角设定、世界规则和前十章大纲。

$novel-writer 继续第 4 章。先读取故事圣经、正史台账、时间线、伏笔台账和最新章节，给我一个简短读回，再开始写。

$novel-writer 审核这个大纲，重点看时间线漏洞、人物动机不足、反转是否缺铺垫、伏笔回收是否成立。
```

## How To Use In Claude Code / 在 Claude Code 中使用

In Claude Code, the skill can be invoked by name. Depending on your Claude Code version and setup, use either a direct command-style invocation or a natural-language request that names the skill:

在 Claude Code 中，可以按 skill 名称调用。根据你的 Claude Code 版本和配置，可以使用命令式调用，也可以在自然语言里点名这个 skill：

```text
/novel-writer
```

or:

或者：

```text
Use the novel-writer skill to create a file-backed novel project.
```

Chinese examples:

中文示例：

```text
/novel-writer 帮我导入这份已有小说稿，提取人物、时间线、世界规则、未回收伏笔，然后给出续写方案。

Use the novel-writer skill。请先读取项目文件，做连续性检查，再续写下一章。

Use the novel-writer skill。这个新设定可能会改动主线，先分析它对人物关系、节奏、伏笔和结局承诺的影响，不要立刻写进正文。
```

## Recommended Workflow / 推荐工作流

### 1. Start A New Project / 新建项目

Ask the agent to create a file-backed project folder. The skill should generate core files before drafting:

新项目建议先让智能体创建文件化项目。skill 会要求先建立核心文件，再开始正文：

```text
$novel-writer Start a new cyberpunk mystery romance project. Create the project workspace, story bible, canon ledger, character files, timeline, rules, promise ledger, and chapter plan before drafting.
```

### 2. Import Existing Writing / 导入已有稿件

Put your manuscript or notes in the workspace, then ask the agent to analyze before continuing:

把已有稿件或设定放到工作区后，让智能体先分析再续写：

```text
$novel-writer Import the existing manuscript in 05-source-material. Extract canon, POV, voice, cast, relationship state, open plot threads, and the immediate next scene pressure.
```

### 3. Continue Chapters / 续写章节

For continuation, always ask for a readback first. This helps catch stale context and contradictions:

续写时建议先要求“读回”，这样可以减少上下文过期和设定矛盾：

```text
$novel-writer Continue the next chapter. First reread the core files and latest two chapters, then summarize current position, active constraints, open promises, and the next intended beat.
```

### 4. Change A Plot Direction / 修改剧情方向

When you add a twist or major setting change, ask for impact analysis before canonizing it:

当你添加重大转折或设定变化时，先让它分析影响，不要直接写入正史：

```text
$novel-writer What if the male lead has been hiding a false identity? Classify the change, explain non-spoiler impact, list risks, and ask what I need to decide before updating canon.
```

### 5. Audit Continuity / 审核连续性

Use this before large revisions, long continuations, or after many chapters:

长篇写到中后段、准备大修或连续续写前，建议做一次连续性审计：

```text
$novel-writer Run a continuity audit. Check timeline, motives, world rules, relationship state, clues, promises, and whether any chapter solves problems with unseeded information.
```

## What The Reference Files Do / 参考文件说明

- `references/project-workspace.md`: folder layout, file contracts, resume readback, writeback rules.
- `references/story-workflow.md`: concept, bible, outline, scene drafting, revision, import workflow.
- `references/genre-playbooks.md`: romance, sci-fi, suspense, fantasy, comedy, and web-serial quality gates.
- `references/continuity-audit.md`: contradiction checks, severity, motive testing, timeline testing, fix patterns.

对应中文说明：

- `references/project-workspace.md`：项目文件夹结构、核心文件职责、续写读回、写后更新规则。
- `references/story-workflow.md`：从创意到故事圣经、大纲、场景写作、修订、导入已有稿件的流程。
- `references/genre-playbooks.md`：甜宠、科幻、悬疑、奇幻、喜剧、网文连载等类型质量门槛。
- `references/continuity-audit.md`：矛盾检查、严重程度判断、人物动机测试、时间线测试和修复方案。

## Updating The Skill / 更新 skill

To update an existing installation, pull the repository and copy the folder again:

更新已安装版本时，拉取仓库后重新复制 `novel-writer/`：

```powershell
git pull
Remove-Item -Recurse -Force "$env:USERPROFILE\.codex\skills\novel-writer" -ErrorAction SilentlyContinue
Remove-Item -Recurse -Force "$env:USERPROFILE\.claude\skills\novel-writer" -ErrorAction SilentlyContinue
Copy-Item -Recurse -Force ".\novel-writer" "$env:USERPROFILE\.codex\skills\novel-writer"
Copy-Item -Recurse -Force ".\novel-writer" "$env:USERPROFILE\.claude\skills\novel-writer"
```

For macOS/Linux:

```bash
git pull
rm -rf ~/.codex/skills/novel-writer ~/.claude/skills/novel-writer
cp -R novel-writer ~/.codex/skills/novel-writer
cp -R novel-writer ~/.claude/skills/novel-writer
```

## Validation / 校验

Validate the Codex skill structure before publishing changes:

发布前可以校验 skill 结构：

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" .\novel-writer
```

If your system `python` command is unavailable, use the Python bundled with your agent runtime or any local Python 3 installation.

如果系统没有可用的 `python` 命令，可以使用智能体运行时自带的 Python，或任意本地 Python 3。

## Notes / 注意事项

- Keep private manuscripts out of this repository.
- Keep generated project folders separate from the skill source unless you intentionally want to publish an example.
- Review any third-party skill before installing it, because skills can contain operational instructions and bundled files.
- The skill itself is instruction-only; it does not include model weights, API keys, or private writing projects.

中文注意事项：

- 不要把私人稿件提交到这个仓库。
- 生成的小说项目文件夹建议和 skill 源码分开放，除非你明确想发布示例项目。
- 安装第三方 skill 前建议先读一遍内容，因为 skill 可能包含操作指令和附带文件。
- 这个 skill 只包含写作流程说明和参考文件，不包含模型权重、API key 或私人小说项目。

## References / 参考

- Claude Code skills documentation: <https://code.claude.com/docs/en/skills>
- Claude Code SDK skills documentation: <https://code.claude.com/docs/en/agent-sdk/skills>
- OpenAI skills repository: <https://github.com/openai/skills>
