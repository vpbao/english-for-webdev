# English for Web Developers

A Claude skill that teaches English specifically for web developers — built by a Vietnamese developer, for Vietnamese developers.

## What is this?

This is a **Claude Skill** (`.skill` file) that turns Claude into a personalized English tutor who understands your tech stack, your daily work, and the specific challenges Vietnamese speakers face when learning English.

## Features

**7 Learning Modes:**

| Mode | Command | Description |
|------|---------|-------------|
| Learning Plan | `/plan` | Multi-week study plan tailored to your schedule and goals |
| Interactive Lesson | `/lesson` | Structured lesson with warm-up, content, practice, and summary |
| Quick Practice | `/practice` | 5-10 minute exercises: translate, fix errors, role-play |
| Review | `/review` | Paste your English writing, get corrections and tips |
| Interview Prep | `/interview` | Mock technical interviews with feedback |
| Inline Correction | `/correct` | Correct + teach: explains the rule behind each error |
| Progress | `/progress` | View your level, XP, streak, and skill radar |

**Built-in Systems:**
- Spaced Repetition — review vocabulary right before you forget
- Gamification — XP, levels (Code Reader → Global Dev), streaks, badges
- Progress Tracking — saves progress between sessions via `english-progress.md`
- 15 pre-built lesson topics from beginner to advanced
- Vietnamese-specific pronunciation and grammar guidance

**Stack-Aware:** All examples use PHP/Laravel, React/Next.js, and Node.js/TypeScript.

## Installation

### Option 1: Install the `.skill` file (Recommended)

1. Download `english-for-webdev.skill` from the [Releases](../../releases) page
2. Double-click the file — it will auto-install into Claude

### Option 2: Install from source

1. Clone this repo:
   ```bash
   git clone https://github.com/YOUR_USERNAME/english-for-webdev.git
   ```
2. Copy the skill folder to your Claude skills directory:
   ```bash
   # macOS
   cp -r english-for-webdev ~/.claude/skills/

   # Or add to your project's .claude/skills/ directory
   cp -r english-for-webdev /path/to/your/project/.claude/skills/
   ```

## Usage

Once installed, just talk to Claude naturally:

```
"học tiếng Anh"
"I want to learn English"  
"dạy mình viết PR description"
"sửa giúp mình cái email này"
"luyện phỏng vấn tiếng Anh"
"tạo lộ trình học cho mình"
```

The skill will automatically trigger and present you with learning options.

### Example Session

```
You: học tiếng Anh

Claude: Chào bạn! Ready to level up your English today? 💪

Hôm nay bạn muốn làm gì?

1. 📋 Learning Plan — Tạo/xem lộ trình học
2. 📖 Lesson — Học một bài mới
3. ✏️ Practice — Luyện tập nhanh 5-10 phút
4. 🔍 Review — Sửa bài viết tiếng Anh của bạn
5. 🎤 Interview Prep — Luyện phỏng vấn
6. ✨ Correct — Paste bài viết, mình sửa + dạy luôn
7. 📊 Progress — Xem tiến độ học tập
```

### Saving Progress Between Sessions

At the end of each session, the skill will offer to save your progress to `english-progress.md`. Keep this file and share it at the start of your next session to continue where you left off.

## Skill Structure

```
english-for-webdev/
├── SKILL.md                          # Core skill (mode routing, session start)
└── references/
    ├── learning-plan.md              # Learning plan generation details
    ├── lessons.md                    # Lesson/practice/review/correction details
    ├── interview-prep.md             # Mock interview flow
    ├── vocabulary-database.md        # Word lists and phrase banks
    ├── vietnamese-challenges.md      # Vietnamese-specific English difficulties
    ├── gamification.md               # XP, levels, streaks, badges
    └── progress-tracking.md          # Progress file format, session resume
```

The skill uses **progressive disclosure** — Claude only loads the SKILL.md (100 lines) on trigger, then reads specific reference files as needed. This keeps context usage efficient.

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
