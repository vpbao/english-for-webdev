# Progress Tracking & Cross-Session Continuity

Since each conversation is a new session, we use a progress file to maintain learning continuity.

---

## Contents

1. Canonical Progress File Policy
2. Progress File Format
3. Session Resume Logic
4. Spaced Repetition System
5. First Session

## Canonical Progress File Policy

Use exactly one progress file for a learner:

1. Search for an existing `english-progress.md` in the active learning location:
   - first, the current workspace root
   - then obvious existing learning folders such as `claude/` or `codex/`
2. If one exists, reuse that file for the whole learner journey.
3. If none exists, create `english-progress.md` in the current workspace root after the first meaningful session.
4. Never create duplicate progress files in multiple folders unless the user explicitly asks for separate profiles.

## Progress File Format

At the end of every completed learning session, save/update the canonical `english-progress.md` with this structure:

```markdown
# English Learning Progress

## Stats
- **Level:** 5 — Team Chatter
- **Total XP:** 1,250
- **Current Streak:** 12 days
- **Longest Streak:** 12 days
- **Last Session:** 2026-05-15

## Skill Radar
| Skill | Score | Notes |
|-------|-------|-------|
| Reading | 3/5 | Can read most docs |
| Writing | 2/5 | Basic PRs OK, emails need work |
| Speaking | 1/5 | Not practiced yet |
| Listening | 2/5 | Can follow slow speech |
| Vocabulary | 2/5 | ~80 words learned |
| Grammar | 2/5 | Articles and tenses still weak |

## Vocabulary (Spaced Repetition)
| Word / Phrase | State | Next Review | Last Reviewed |
|---------------|-------|-------------|---------------|
| deploy to production | Known | 2026-06-01 | 2026-05-15 |
| refactor this controller | Familiar | 2026-05-22 | 2026-05-15 |
| I'm still investigating... | Learning | 2026-05-18 | 2026-05-15 |
| The issue happens when... | New | 2026-05-16 | 2026-05-15 |

## Completed Lessons
- [x] 2026-05-10 — Standup survival kit (+50 XP)
- [x] 2026-05-12 — Your first PR description (+50 XP)
- [x] 2026-05-14 — Git commit messages (+50 XP)

## Badges Earned
- 🎯 First PR in English (2026-05-12)
- 🔥 Week Warrior (2026-05-14)

## Common Mistakes (working on)
1. Missing articles ("I fixed bug" → "I fixed the bug")
2. Wrong tense with time markers ("I have fixed it yesterday")
3. Dropping subjects ("Is working" → "It is working")

## Next Focus
- Practice articles (a/the) in writing exercises
- Try first standup role-play (Speaking skill is lowest)
```

## Session Resume Logic

### Auto-read Progress (no upload needed)

At session start, automatically read the canonical progress file if it exists. The user should not need to upload it manually.

Steps:
1. **Auto-read** the canonical `english-progress.md` silently
2. **Calculate streak:** Compare last session date with today
   - Same day or consecutive → streak continues
   - 1 day gap → streak continues (grace period)
   - 2+ days gap → streak resets to 1
3. **Check vocabulary for review:** Find words where `Next Review ≤ today`
4. **Welcome back message:**
   "Welcome back! 🔥 Day [N] streak!
   You have [N] words due for review.
   Last time you learned about [topic].
   Ready to continue?"
5. **Suggest next activity** based on:
   - Lowest skill radar score → suggest a lesson in that area
   - Words due for review → weave them into warm-up
   - Next uncompleted lesson from the catalog

### Auto-save Progress (no manual step needed)

At the end of every completed learning session, automatically save/update the canonical `english-progress.md`. Do not ask for permission; confirm briefly: "Progress saved! See you tomorrow 🔥"

## Spaced Repetition System — How It Actually Works

### The Challenge

Unlike Anki or Duolingo, this skill runs in chat sessions without a persistent database. Each conversation starts fresh. So spaced repetition relies on two mechanisms working together:

1. **Progress file** (`english-progress.md`) — the "memory" between sessions
2. **Scheduled daily reminder** — the "alarm clock" that nudges you to review

### Learning States

Each vocabulary word progresses through 4 states:

```
New → Learning → Familiar → Known
 ↑       ↑          ↑
 └───────┴──────────┘  (drop back if answered wrong)
```

| State | Review Interval | Promotion condition |
|-------|----------------|---------------------|
| New | 1 day | Answer correctly once → Learning |
| Learning | 2-3 days | Answer correctly twice → Familiar |
| Familiar | 1 week | Answer correctly → Known |
| Known | 2-4 weeks | Stays here, periodic review |

If answered incorrectly at any state → drop back one level.

### Flow in Practice

**End of each session:**
1. Skill lists all new words/chunks learned with their state and next review date
2. Skill updates the progress file with the new vocabulary entries
3. Skill saves the updated `english-progress.md`

**Start of next session:**
1. Skill reads the canonical progress file
2. Skill scans the vocabulary table for words where `Next Review ≤ today`
3. Due words are woven into the warm-up naturally — not as a flashcard drill, but as part of conversation:
   - "Before we start today's lesson, quick check: how would you describe deploying a hotfix to production?"
   - "Remember 'refactor'? Use it in a sentence about your current project."
4. Based on the user's answer, update the word's state (promote or demote)

**During lessons:**
- When teaching new content, naturally reuse previously learned vocabulary
- If a user correctly uses a "Familiar" word unprompted, note it and consider promoting to "Known"

### Daily Review Reminder (Scheduled Task)

To compensate for the lack of push notifications, the skill should suggest setting up a daily scheduled task on first use. This task runs automatically and prompts the user to do a quick review session.

After the first lesson, suggest:
"Bạn có muốn mình tạo lịch nhắc ôn tập hàng ngày không? Mỗi sáng mình sẽ gửi cho bạn 5 từ cần ôn — chỉ mất 2-3 phút thôi!"

If the user agrees, guide them to set up a scheduled task with a prompt like:
"Read my english-progress.md file, find words due for review today, and give me a quick 5-word quiz. Keep it under 3 minutes. Show my streak status too."

This creates a daily habit loop:
```
Morning reminder → 2-min vocab quiz → streak maintained → motivation sustained
```

### Limitations & Honesty

Be transparent with the user about what this system can and can't do:
- ✅ Tracks vocabulary states and review dates accurately
- ✅ Naturally weaves reviews into lessons (not boring flashcards)
- ✅ Daily reminders via scheduled tasks
- ✅ Auto-save/auto-read progress — no manual upload needed
- ❌ Can't track review accuracy across sessions precisely (relies on answers in chat)
- ❌ No mobile push notifications

The trade-off: less automatic than a dedicated app, but every review happens in the context of real developer work — which makes vocabulary stick better than isolated flashcards.

## First Session (No Progress File)

If no canonical `english-progress.md` is found:
- Skip stats display in the greeting
- Ask: "Is this your first time, or have you been learning already?"
- If first time → start from Level 1, 0 XP
- If continuing without file → ask about their level and adjust accordingly
- After the session, auto-create `english-progress.md` in the current workspace root — future sessions should reuse that same file
