# Gamification & Motivation System

Learning a language is a marathon. Gamification creates the short-term motivation loops that keep learners going day after day.

---

## XP (Experience Points)

Award XP for activities:

| Activity | XP |
|----------|-----|
| Complete a lesson | +50 |
| Quick practice session | +20 |
| Write a correct sentence on first try | +10 |
| Use a previously learned word correctly | +5 |
| Complete a review/correct session | +30 |
| Mock interview completed | +100 |

## Levels

Levels map to real English proficiency milestones:

| Level | Title | XP Range | What you can do |
|-------|-------|----------|----------------|
| 1-3 | Code Reader | 0-500 | Read English docs and comments |
| 4-6 | Team Chatter | 500-1,500 | Write basic Slack/email, participate in standup |
| 7-9 | PR Pro | 1,500-3,500 | Write clear PRs, reviews, technical emails |
| 10-12 | Tech Communicator | 3,500-6,000 | Present, interview, write docs confidently |
| 13-15 | Global Dev | 6,000+ | Communicate naturally in any professional context |

## Streaks

Track consecutive days of learning:
- Show current streak at session start: "🔥 Day 5 streak! Keep it going!"
- Streak milestones:
  - 7 days: "One week strong! Consistency beats intensity."
  - 30 days: "A month! Your English brain is forming new neural pathways."
  - 100 days: "Legend status. Most people quit at day 3."
- Streak freeze: "Busy day? Do a 2-minute quick quiz to keep your streak alive."

## Achievements / Badges

| Badge | Name | How to unlock |
|-------|------|--------------|
| 🎯 | First PR in English | Write your first PR description |
| 🔄 | Refactor Master | Learn 50 code-related verbs |
| 💬 | Standup Star | Complete 10 standup simulations |
| 🎤 | Interview Ready | Complete 5 mock interviews |
| 📚 | Vocabulary Century | Learn 100 words |
| ✍️ | Grammar Ninja | Get 10 perfect scores on grammar exercises |
| 🔥 | Week Warrior | 7-day streak |
| 🏔️ | Month Master | 30-day streak |
| 💎 | Century Legend | 100-day streak |

## Session End Display

At the end of every session, show this progress summary:

```
━━━ Session Complete ━━━
+[N] XP earned | Total: [N] XP
Level [N]: [Title] ████████░░ ([N] XP to Level [N+1])
🔥 Streak: [N] days
🏆 [New badge if any]
━━━━━━━━━━━━━━━━━━━━━━━
```

## Progress Report Format (Mode 7)

When the user asks for `/progress`, generate:

1. **Overview:** Level, total XP, streak
2. **Skill Radar:** Scores across 6 dimensions (1-5 each):
   - Reading — Understanding docs, blog posts, error messages
   - Writing — PRs, commits, emails, Slack, documentation
   - Speaking — Standup, meetings, presentations, interviews
   - Listening — Understanding spoken English in meetings/videos
   - Vocabulary — Size and depth of technical vocabulary
   - Grammar — Accuracy of grammar usage
3. **Words Learned:** Total count + recent additions
4. **Common Mistakes:** Top 3 recurring errors
5. **Badges Earned:** List with dates
6. **Streak Stats:** Current, longest, consistency percentage
7. **Recommendation:** What to focus on next session
8. **Comparison:** vs previous report if available
