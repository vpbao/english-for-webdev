# English for Web Developers

A speaking-first English skill for Vietnamese web developers.

## What is this?

This is a **Claude Skill** (`.skill` file) that turns Claude into a practical English coach for real developer communication: standups, PRs, code reviews, bugs, meetings, documentation, and interviews.

It is built around one central idea: Vietnamese developers often know more English than they can use in real time. So the skill trains **retrieval**, **reusable chunks**, and **workplace communication**, not just passive vocabulary.

## Features

**7 Learning Modes**

| Mode | Command | Description |
|------|---------|-------------|
| Learning Plan | `/plan` | Multi-week study plan tailored to your schedule and goals |
| Interactive Lesson | `/lesson` | Structured lesson with warm-up, teaching, practice, and summary |
| Quick Practice | `/practice` | 5-10 minute drills: translate, fix errors, role-play |
| Review | `/review` | Paste your English writing and get clarity-focused feedback |
| Interview Prep | `/interview` | Mock technical interviews with feedback |
| Inline Correction | `/correct` | Correct + teach: the reason behind each fix |
| Progress | `/progress` | View your level, XP, streak, and skill radar |

**Built-in Systems**

- Speaking-first, chunk-based teaching
- Spaced repetition for words and phrases
- XP, levels, streaks, and badges
- Automatic progress continuity through one `english-progress.md` file
- Reusable HTML deliverables for lesson sheets, quizzes, and progress reports
- 15 lesson topics from beginner to advanced
- Vietnamese-specific grammar and pronunciation guidance

**Stack-aware examples**

Examples favor PHP/Laravel, React/Next.js, and Node.js/TypeScript so the English stays close to real web-development work.

## Website

A polished GitHub Pages landing page lives in `docs/index.html`. Once Pages is enabled for the `docs/` folder, the public site can live at:

```text
https://vpbao.github.io/english-for-webdev/
```

## Installation

### Option 1: Install the `.skill` file

1. Download `english-for-webdev.skill`
2. Double-click it to install into Claude

### Option 2: Install from source

```bash
git clone https://github.com/vpbao/english-for-webdev.git
cp -r english-for-webdev ~/.claude/skills/
```

## Usage

Talk naturally:

```text
học tiếng Anh
I want to learn English for work
dạy mình viết PR description
sửa giúp mình cái email này
luyện phỏng vấn tiếng Anh
tạo lộ trình học cho mình
```

If your request is broad, the skill offers modes. If your request is specific, it acts directly instead of forcing you through a menu.

### Example

```text
You: sửa giúp mình PR description này

Claude:
Corrected version:
...

Why these changes:
...

Now try one short sentence using "This PR addresses..."
```

## Progress Between Sessions

The skill automatically reuses one `english-progress.md` file for continuity:

- if a progress file already exists, it reads and updates that file
- if none exists, it creates one after the first meaningful learning session
- the learner should not need to manually upload or manage progress files

The skill tracks phrases and chunks such as `I'm still investigating...` or `deploy to production`, not only isolated words.

## Skill Structure

```text
english-for-webdev/
├── SKILL.md
└── references/
    ├── learning-plan.md
    ├── lessons.md
    ├── interview-prep.md
    ├── vocabulary-database.md
    ├── vietnamese-challenges.md
    ├── gamification.md
    ├── progress-tracking.md
    └── html-deliverables.md
```

The skill uses **progressive disclosure**: the core instructions stay compact, and Claude reads detailed reference files only when a mode needs them.

## Lesson Catalog

| # | Topic | Level |
|---|-------|-------|
| 1 | Reading error messages like a pro | Beginner |
| 2 | Your first PR description | Beginner |
| 3 | Standup survival kit | Beginner |
| 4 | Git commit messages that make sense | Beginner |
| 5 | Slack 101 for developers | Beginner |
| 6 | Code review: giving and receiving feedback | Intermediate |
| 7 | Writing bug reports that get fixed | Intermediate |
| 8 | Explaining your architecture | Intermediate |
| 9 | Email to your tech lead | Intermediate |
| 10 | Sprint planning vocabulary | Intermediate |
| 11 | Technical interview: thinking out loud | Advanced |
| 12 | System design discussion | Advanced |
| 13 | Presenting a demo | Advanced |
| 14 | Writing an RFC/tech spec | Advanced |
| 15 | Negotiating technical decisions | Advanced |

## License

MIT
