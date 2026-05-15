# Progress Tracking & Cross-Session Continuity

Since each conversation is a new session, we use a progress file to maintain learning continuity.

---

## Progress File Format

At the end of every session, offer to save/update `english-progress.md` with this structure:

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
| Word | State | Next Review | Last Reviewed |
|------|-------|-------------|---------------|
| deploy | Known | 2026-06-01 | 2026-05-15 |
| refactor | Familiar | 2026-05-22 | 2026-05-15 |
| deprecate | Learning | 2026-05-18 | 2026-05-15 |
| scaffold | New | 2026-05-16 | 2026-05-15 |

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

When user starts a new session and provides a progress file:

1. **Read the file** and extract current stats
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

## Spaced Repetition States

| State | Review Interval | Promotion condition |
|-------|----------------|---------------------|
| New | 1 day | Answer correctly once → Learning |
| Learning | 2-3 days | Answer correctly twice → Familiar |
| Familiar | 1 week | Answer correctly → Known |
| Known | 2-4 weeks | Stays here, periodic review |

If answered incorrectly at any state → drop back one level.

## First Session (No Progress File)

If no progress file exists:
- Skip stats display in the greeting
- Ask: "Is this your first time, or have you been learning already?"
- If first time → start from Level 1, 0 XP
- If continuing without file → ask about their level and adjust accordingly
