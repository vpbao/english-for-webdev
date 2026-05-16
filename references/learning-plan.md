# Learning Plan — Detailed Instructions

## Before Creating the Plan

Ask the user:
- How many hours per week can they dedicate?
- Any upcoming deadlines? (interview date, project with English-speaking team, etc.)
- Which area feels most urgent?

If the user already provided enough context, do not ask again. Build the plan from what is known and state any assumption briefly.

## Plan Structure

Create a plan with 3 phases. If there's a deadline (e.g., interview in X months), compress or expand phases to fit the timeline.

### Phase 1: Unlock the Mouth (first ~1/3 of timeline)

Goal: stop freezing, build 250–300 active words/chunks, speak in short but complete developer sentences.

- Survival chunks for standup, bugs, tasks, blockers (teach as sentence patterns, not isolated words)
- Essential dev verbs in context with collocations
- Basic grammar through dev sentences: present simple, past simple, articles, required subjects
- Speaking from day 1: daily 30-second standup practice, timed drills
- Short listening with transcript + shadowing

Speaking milestones:
- Week 4: give a 30-second standup without reading
- Week 8: explain a bug and a fix in 60 seconds
- Week 12: describe your current project in 90 seconds

### Phase 2: Work Like a Global Teammate (middle ~1/3)

Goal: communicate reliably in real work situations. Longer speaking turns (1–3 minutes).

- PR descriptions, code review comments, Slack, email
- Explaining code, APIs, architecture, trade-offs
- Listening to dev videos and meeting-style English
- Role-play: standup, planning, clarification, disagreement
- Grammar: modals, present perfect, connectors

Speaking milestones:
- Week 16: write a clean PR description and explain it aloud in 2 min
- Week 20: join a simulated meeting and ask follow-up questions
- Week 24: explain a system or feature with clear structure

### Phase 3: Interview & Transition Ready (final ~1/3)

Goal: become interview-ready and work-ready at a global company.

- "Tell me about yourself" — polished 2-minute answer
- STAR stories for projects, conflicts, deadlines, failures
- Technical interview communication (thinking out loud, narrating while coding)
- System design vocabulary and discussions
- Mock interviews weekly
- CV/project explanations, salary negotiation
- Working in a global team: async communication, cultural awareness

Speaking milestones:
- Week 28: deliver a polished self-introduction
- Week 32: complete a full behavioral + technical mock interview
- Week 34: start real applications
- Week 36: final review and graduation

---

## Monthly Outcome Map

Include a month-by-month map so the learner can see the big picture. Adapt months to fit the actual timeline. Example for a 9-month plan:

| Month | Main outcome |
|---|---|
| Month 1 | Say simple dev sentences without translating every word |
| Month 2 | Give basic standup updates and describe bugs |
| Month 3 | Explain tasks, PRs, and current work clearly |
| Month 4 | Write and speak around daily team communication |
| Month 5 | Handle meetings, clarifications, and code review language |
| Month 6 | Explain architecture and technical decisions |
| Month 7 | Build interview answers and STAR stories |
| Month 8 | Begin applications + weekly mock interviews |
| Month 9 | Interview sprint: speed, fluency, confidence |

---

## Daily Template

Every plan should include the daily 30-minute speaking-first structure:

```text
5 min   Review old chunks (spaced repetition)
10 min  Learn new vocabulary/chunks
10 min  Speak with timer (drills, role-play, or monologue)
5 min   Write down mistakes + one corrected version
```

### Golden Rule — Bad Day Fallback (10 min)

```text
3 min review + 5 min speaking + 2 min recap
```

Include this in every plan. The message: **never let the streak die because the session is imperfect.** Consistency beats intensity.

---

## Weekly Breakdown Template

Each week should include:
- **Chunk set** (5-7 reusable sentence patterns — this is the priority, not isolated words)
- **Supporting vocabulary** (5-10 words with IPA, Vietnamese, and an example that uses a chunk)
- **Grammar point** (taught through developer sentences, never abstract)
- **Reading/Listening input** (a real doc page, blog post, or dev video)
- **Writing exercise** (a realistic artifact: PR, commit, Slack, email)
- **Speaking drill** (timed challenge: 30-sec standup, 60-sec bug explanation, etc.)
- **Checkpoint** (what they should be able to *say or do* by end of this week — speaking milestones, not just knowledge)

Include checkboxes so the user can track progress.

### Weekly Schedule Template

| Day | Focus |
|---|---|
| Mon | Vocabulary + chunks — learn 5-7 new phrases, make personal sentences, speak aloud |
| Tue | Listening + shadowing — short dev video, repeat, summarize in English |
| Wed | Grammar for speaking — one point, transform to work context, timed prompts |
| Thu | Real work English — write one artifact (commit/Slack/PR/email), explain aloud |
| Fri | Role-play with tutor — standup, help, bug, interview, or meeting sim |
| Sat | Review + 1-min monologue using the week's phrases |
| Sun | Light day — fun English, no heavy study, protect consistency |

---

## Interview Preparation Timeline

If the learner has an interview deadline, include a specific application timeline:

| When | What |
|---|---|
| End of Phase 2 | Can speak about daily work without freezing; enough vocabulary for team communication |
| Start of Phase 3 | Can explain experience, one project, one bug, one conflict, one technical decision |
| Phase 3 month 1 | Start applying selectively; 1 mock interview per week; collect real questions as practice |
| Phase 3 month 2 | 2 mock interviews per week; daily 10-min speaking drill; focus on fluency and answer latency |
| Final weeks | Final polishing, weak-point repair, confidence building |

---

## Output Format

If the user only wants guidance, answer in chat. If they want a reusable plan, create a polished structured deliverable.

For reusable plans, prefer an **interactive HTML dashboard** (see `html-deliverables.md` for the design system). The HTML should include:
- Stats overview (starting level, target, timeline)
- Skill radar chart (current vs target) using Chart.js
- Strategy/philosophy section
- Monthly outcome map with current month highlighted
- Collapsible phase sections with progress bars
- Collapsible weekly breakdowns with chunk tables, grammar notes, daily tasks
- Interactive checkboxes (localStorage)
- Milestone markers
- Daily template + golden rule section
- Habits section

Keep a markdown version (`english-learning-plan.md`) as backup/source-of-truth if useful, but the primary deliverable is the HTML dashboard.

Include in both formats:
- Vocabulary lists with IPA, Vietnamese translation, example sentences
- XP milestones and level progression targets
- Spaced repetition review schedule
- Skill radar starting scores and target scores

---

## Quality Bar

A publish-worthy plan should:
- reflect the learner's deadline, available time, and weakest skill
- sequence speaking practice from week 1 instead of postponing it
- include both work-English and interview-English when relevant
- convert goals into concrete weekly behaviors, not just topic lists
- use speaking milestones ("can give a 30-sec standup") not just knowledge milestones ("know 50 words")
- count chunks learned, not isolated words
- include the daily template and golden rule fallback
- feel achievable — bad days are expected and accounted for
- encourage using English at work immediately, not in a vacuum
