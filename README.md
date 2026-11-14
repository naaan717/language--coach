# Language Coach / 语言口语教练

一个面向任何支持 `SKILL.md` 的代理的口语教练技能。练习用目标语言进行，纠正、说明和收尾复习用学习者的解释语言（默认简体中文）。

An open-source speaking-coach skill for any agent that reads `SKILL.md`. Practice stays in the target language. Corrections, explanations, and the wrap-up are written in the learner's explanation language, Simplified Chinese by default.

技能名是 `language-coach`。仓库名里的两个连字符只是仓库地址，不是技能名。

The skill id is `language-coach`. The second hyphen in the repository name is only the GitHub path.

## 它做什么

教练陪学习者说话，而不是把对话改成语法课。

- 一次只问一个问题，停顿和口头填充都不打断。
- 只改重要的、反复出现的、或在所选变体里明显不自然的说法。先回应意思，再给一个更口语的说法。
- 学习者说 **Add this to my vocabulary**（或“请把这个记到词汇本”）时，把该条记进当天的词汇表。
- 听到“今天就到这里”或 `Let's wrap up` 时，不立刻道别，先给出固定的六段复习。
- 复习之后逐句影子跟读或朗读。宿主没有语音时，改为学习者自己读出声。
- 需要安排时，按 30 天计划给当天的任务。
- 变体规则放在单独文件里。现在提供美式英语 `en-US` 和英式英语 `en-GB`。再加一种语言或变体，只需要在 `variants/` 里新增一个文件。

## What it does

The coach holds a conversation instead of turning the session into a grammar class.

- One question at a time. Pauses and fillers are not interruptions.
- Corrections are limited to language that is important, repeated, or clearly unnatural for the chosen variant. Meaning comes first, then one more natural wording.
- **Add this to my vocabulary** (or the same request in the explanation language) stores that item for the session.
- `Let's wrap up`, or “今天就到这里”, does not end the chat. A fixed six-part review comes first.
- After the review, shadowing or read-aloud proceeds one sentence at a time. With no audio in the host, the learner reads the line aloud.
- A 30-day plan supplies the day's job when they want a schedule.
- Variety-specific rules live in their own files. American English (`en-US`) and British English (`en-GB`) ship now. Another language or variety is one new file under `variants/`.

## 安装

任选一种。

把技能目录复制到代理用来加载技能的文件夹：

```text
skills/language-coach/
```

常见位置：

| 代理 | 目录 |
| --- | --- |
| Claude Code | `.claude/skills/language-coach` 或 `~/.claude/skills/language-coach` |
| Cursor | `.cursor/skills/language-coach` |
| Codex | `~/.codex/skills/language-coach`，或把本仓库当作插件安装 |
| 其他支持 SKILL.md 的代理（包括 Grok Bot） | 该代理自己的 skills 目录 |

也可以用技能安装器。在你的项目目录里运行：

```bash
npx skills add https://github.com/naaan717/language--coach
```

安装器会找到 `skills/language-coach/SKILL.md`。需要的话用 `--skill language-coach` 指定名字，并用 `-a` 选择代理。

本技能不绑定 Codex。仓库里的 `.codex-plugin/plugin.json` 只是让 Codex 的插件安装流程能发现它。Claude Code、Cursor、Grok Bot 以及其他读取 `SKILL.md` 的代理都不依赖这个文件。

实时语音取决于宿主应用。技能规定练什么、怎么纠正、怎么收尾；麦克风和播放由宿主提供。没有语音时，跟读自动改成朗读。

长期笔记不是自动写回磁盘的。把会话里生成的复习和词汇表贴进 `knowledge-base/` 下的对应模板，下次才接得上。模板可以跟着技能走，也可以复制到你自己的笔记目录。

## Install

Use either method.

Copy the skill folder into the directory your agent loads skills from:

```text
skills/language-coach/
```

Common locations:

| Agent | Directory |
| --- | --- |
| Claude Code | `.claude/skills/language-coach` or `~/.claude/skills/language-coach` |
| Cursor | `.cursor/skills/language-coach` |
| Codex | `~/.codex/skills/language-coach`, or install this repository as a plugin |
| Other SKILL.md agents, including Grok Bot | that agent's own skills directory |

Or use the skills installer from your project directory:

```bash
npx skills add https://github.com/naaan717/language--coach
```

The installer discovers `skills/language-coach/SKILL.md`. Pass `--skill language-coach` to select it, and `-a` to choose an agent.

The skill is not tied to Codex. `.codex-plugin/plugin.json` exists so Codex plugin install can find the skill. Claude Code, Cursor, Grok Bot, and any other host that reads `SKILL.md` ignore that file.

Real-time voice depends on the host app. The skill decides what to practice, what to correct, and how a session ends. The host supplies the microphone and playback. With no audio, shadowing becomes read-aloud.

Notes are not written back to disk on their own. Paste the review and the vocabulary table into the matching file under `knowledge-base/` if you want them next time. Keep those templates with the skill, or copy them into your own notes.

## 怎么用

先告诉教练目标和解释语言。不说的话，解释语言是简体中文；变体需要你指定，或写在 `knowledge-base/learner-profile.md`。

```text
我们开始今天的口语练习。我想练美式英语。
```

```text
请用英式英语。解释继续用简体中文。
```

```text
We're starting today's speaking session. American English, please.
```

练习过程中保存一条说法：

```text
Add this to my vocabulary.
```

```text
请把这个记到词汇本。
```

结束时：

```text
今天就到这里。
```

```text
Let's wrap up.
```

教练会先用简体中文写出六段复习（词汇、实用短语、自然表达、重要纠正、润色后的说法、下次练习目标），例句仍是英文；然后给出词汇更新表；然后一次只给一句跟读。

换解释语言：

```text
解释改成英文。
```

按计划练：

```text
今天按 30 天计划的第 8 天来。
```

想让拼写和用词严格统一成一种变体时，说一声。否则 *colour* 和 *color* 这类合法差异不会被当成错误。

## Usage

Name the variety and the explanation language. If you name neither, explanations stay in Simplified Chinese, and the coach will ask which variety to load unless `knowledge-base/learner-profile.md` already says.

```text
我们开始今天的口语练习。我想练美式英语。
```

```text
请用英式英语。解释继续用简体中文。
```

```text
We're starting today's speaking session. American English, please.
```

Save a line during practice:

```text
Add this to my vocabulary.
```

```text
请把这个记到词汇本。
```

End the session:

```text
今天就到这里。
```

```text
Let's wrap up.
```

The coach writes the six-part review in Simplified Chinese (vocabulary, useful phrases, natural expressions, important corrections, one polished version, one next-session goal), keeps the English examples in English, then the vocabulary table, then a single shadowing sentence.

Switch the explanation language:

```text
解释改成英文。
```

Follow the plan:

```text
今天按 30 天计划的第 8 天来。
```

Ask for strict consistency if you want one variety's spelling and word choice throughout. Otherwise a valid form from the other variety, such as *colour* beside *color*, is not treated as an error.

## 目录

```text
language--coach/
├── LICENSE
├── NOTICE
├── README.md
├── CONTRIBUTING.md
├── .codex-plugin/plugin.json      可选，仅用于 Codex 发现技能
└── skills/language-coach/
    ├── SKILL.md                   会话流程，与具体语言无关
    ├── variants/
    │   ├── _TEMPLATE.md           新增变体时复制
    │   ├── en-US.md
    │   └── en-GB.md
    ├── references/
    │   ├── session-review-template.md
    │   ├── shadowing-guidelines.md
    │   └── 30-day-practice-plan.md
    ├── knowledge-base/
    │   ├── learner-profile.md
    │   ├── vocabulary-notebook.md
    │   ├── common-mistakes.md
    │   ├── progress-tracker.md
    │   ├── sessions/SESSION_TEMPLATE.md
    │   └── weekly-reviews/WEEKLY_REVIEW_TEMPLATE.md
    └── examples/sample-session.md
```

## 扩展

新增一门语言或一种变体：复制 `skills/language-coach/variants/_TEMPLATE.md`，另存为 `variants/<id>.md`，填好拼写、用词、日常表达、语法偏好和发音。不要改 `SKILL.md`。步骤写在 [CONTRIBUTING.md](CONTRIBUTING.md)。

## Extending

To add a language or a variety, copy `skills/language-coach/variants/_TEMPLATE.md` to `variants/<id>.md` and fill in spelling, vocabulary, everyday expressions, grammar preferences, and pronunciation. Do not edit `SKILL.md`. The steps are in [CONTRIBUTING.md](CONTRIBUTING.md).

## 来源与许可

本仓库采用 MIT 许可证，Copyright (c) 2026 naaan717。

会话方式改编自 Prof. Shihmin Lo 的 English Speaking Coach（MIT，Copyright (c) 2026 Prof. Shihmin Lo）：

https://github.com/lolopodcast/english-speaking-coach-plugin

原文的版权声明和许可文本保留在 [LICENSE](LICENSE) 与 [NOTICE](NOTICE)。本仓库的文字是重新写过的通用版本，不是原文的拷贝。

## Credit and license

MIT License, Copyright (c) 2026 naaan717.

The session design is adapted from Prof. Shihmin Lo's English Speaking Coach (MIT, Copyright (c) 2026 Prof. Shihmin Lo):

https://github.com/lolopodcast/english-speaking-coach-plugin

The original copyright notice and permission notice are kept in [LICENSE](LICENSE) and [NOTICE](NOTICE). The text in this repository is a rewritten, general-purpose skill, not a copy of the original.
