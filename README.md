# English for Web Developers

[![Website](https://img.shields.io/badge/website-live-52d6c8?style=flat-square)](https://vpbao.github.io/english-for-webdev/)
[![Release](https://img.shields.io/github/v/release/vpbao/english-for-webdev?style=flat-square)](https://github.com/vpbao/english-for-webdev/releases)
[![License](https://img.shields.io/badge/license-MIT-8c7cff?style=flat-square)](#license)

A speaking-first English skill for Vietnamese web developers.

It helps developers move from **reading English** to **using English at work**: in standups, PRs, code reviews, bug reports, documentation, and interviews.

- Website: https://vpbao.github.io/english-for-webdev/
- Latest release: https://github.com/vpbao/english-for-webdev/releases

## Why this exists

Vietnamese developers often know more English than they can use in real time. The bottleneck is usually not vocabulary size; it is retrieval speed, reusable sentence patterns, and practice in realistic situations.

This skill focuses on:

- **speaking-first practice** instead of passive study
- **chunks and collocations** instead of isolated words
- **real developer communication** instead of textbook scenarios
- **Vietnamese-specific guidance** for common grammar and pronunciation traps

## Quick start

### Install the `.skill` package

1. Download `english-for-webdev.skill` from the latest release
2. Double-click it to install into Claude

### Or install from source

```bash
git clone https://github.com/vpbao/english-for-webdev.git
cp -r english-for-webdev ~/.claude/skills/
```

Then talk naturally:

```text
học tiếng Anh
luyện standup 5 phút
dạy mình viết PR description
sửa giúp mình cái email này
luyện phỏng vấn tiếng Anh
```

If the request is broad, the skill offers learning modes. If the request is specific, it acts directly instead of forcing a menu first.

## What it can do

| Mode | Command | Description |
|------|---------|-------------|
| Learning Plan | `/plan` | Build a multi-week study plan around goals and schedule |
| Interactive Lesson | `/lesson` | Teach through warm-up, practice, and summary |
| Quick Practice | `/practice` | Run short drills, quizzes, and role-play |
| Review | `/review` | Improve writing with clarity-focused feedback |
| Interview Prep | `/interview` | Run mock technical interviews with language feedback |
| Inline Correction | `/correct` | Correct writing while teaching the reason behind each fix |
| Progress | `/progress` | Show level, XP, streak, and skill radar |

Built in:

- spaced repetition for words and phrases
- XP, levels, streaks, and badges
- one canonical `english-progress.md` file for continuity
- reusable HTML deliverables for lesson sheets, quizzes, and progress reports
- 15 lesson topics from beginner to advanced
- examples tailored to PHP/Laravel, React/Next.js, and Node.js/TypeScript

## Example

```text
You: sửa giúp mình PR description này

Claude:
Corrected version:
...

Why these changes:
...

Now try one short sentence using "This PR addresses..."
```

## Lesson catalog

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

## Progress between sessions

The skill automatically reuses one `english-progress.md` file:

- if a progress file already exists, it reads and updates that file
- if none exists, it creates one after the first meaningful learning session
- it tracks phrases and chunks such as `I'm still investigating...` or `deploy to production`, not only isolated words

## Project structure

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

## License

MIT
