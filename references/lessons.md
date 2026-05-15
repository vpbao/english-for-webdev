# Lessons — Detailed Instructions

This file covers Modes 2 (Interactive Lesson), 3 (Quick Practice), 4 (Review & Correct), and 6 (Inline Correction).

---

## Contents

1. Mode 2: Interactive Lesson
2. Mode 3: Quick Practice
3. Mode 4: Review & Correct
4. Mode 6: Inline Correction
5. Output Formatting

## Mode 2: Interactive Lesson

Each lesson follows 4 parts:

### Lesson Design Defaults

- Start with speaking, not exposition.
- Teach reusable chunks and sentence patterns before isolated vocabulary.
- Use the learner's real tasks, bugs, PRs, or meetings whenever possible.
- When the learner makes an error, diagnose the cause: translation-from-Vietnamese, missing chunk, tense rule, article use, preposition, or pronunciation.
- Include at least one timed drill so the learner practices retrieval speed, not only recognition.
- End with a sentence the learner can realistically reuse at work the next day.

### Part 1: Warm-up (2-3 minutes)
A quick question or mini-exercise in English to activate what they know. Keep it fun and low-pressure.

Example: "How would you tell your teammate that the API endpoint is returning a 500 error? Try writing it in English — don't worry about being perfect!"

### Part 2: Core Content (adjustable to user's requested duration)

If the user doesn't specify a topic, suggest from this lesson catalog:

**Beginner:**
1. "Reading error messages like a pro" — common error patterns and what they mean
2. "Your first PR description" — basic template and essential phrases
3. "Standup survival kit" — the 3 sentences you need for daily standup
4. "Git commit messages that make sense" — conventions and vocabulary
5. "Slack 101 for developers" — asking questions, sharing updates, emoji reactions

**Intermediate:**
6. "Code review: giving and receiving feedback" — polite but clear language
7. "Writing bug reports that get fixed" — structure and precise language
8. "Explaining your architecture" — describing how systems connect
9. "Email to your tech lead" — professional tone, status updates, asking for help
10. "Sprint planning vocabulary" — estimation, prioritization, scoping phrases

**Advanced:**
11. "Technical interview: thinking out loud" — narrating your problem-solving process
12. "System design discussion" — trade-offs, scalability, architecture vocabulary
13. "Presenting a demo" — transitions, highlighting features, handling questions
14. "Writing an RFC/tech spec" — formal technical writing
15. "Negotiating technical decisions" — disagreeing respectfully, proposing alternatives

#### Lesson Types

**Vocabulary Lessons:**
- Group words by developer context (e.g., "Words you'll see in React docs", "Verbs for code review")
- For each word/phrase: definition, pronunciation guide (IPA + Vietnamese approximation), 2-3 example sentences from real dev contexts, common mistakes Vietnamese speakers make
- Include collocations (words that naturally go together, e.g., "deploy TO production", "merge INTO main")

**Grammar Lessons:**
- Teach grammar through developer communication patterns
- Present Perfect for status updates: "I have finished the API integration" vs "I finished it yesterday"
- Modal verbs for code review: "We should refactor this" vs "We could consider refactoring" vs "This must be fixed before merge"
- Conditionals for technical discussion: "If we use Redis, the response time will improve"

**Writing Lessons:**
- Template + practice for a specific writing task
- e.g., "How to write a clear PR description"
  - Structure: What changed → Why → How to test → Screenshots if UI
  - Useful phrases: "This PR addresses...", "The main changes include...", "To verify, you can..."
  - Common mistakes and how to fix them
  - Practice: give the user a scenario and have them write one

**Speaking/Listening Lessons:**
- Simulate real conversations (standup, planning, interview)
- Provide useful phrases and sentence starters
- Role-play exercises where Claude plays the teammate/interviewer
- Pronunciation tips specific to Vietnamese speakers (→ see `vietnamese-challenges.md`)

### Part 3: Practice (adjustable)
Interactive exercises:
- Fill-in-the-blank with developer context
- Rewrite Vietnamese developer messages in English
- Spot the error in a PR comment or email
- Role-play a short conversation
- Translate a code comment or error message

### Part 4: Summary & Takeaway
- Key phrases/vocabulary from this lesson (bilingual table: English | IPA | Vietnamese | Example)
- One "homework" suggestion they can do at work tomorrow
- Quick self-check: "Can you now ___?"
- Words to Review section with next review dates (spaced repetition)
- XP earned summary

Adapt depth and pace to the user's level. Struggling → slow down, more Vietnamese. Breezing through → more challenge, less Vietnamese.

### Quality Bar

Every completed lesson should include:
- 3-7 reusable chunks or sentence patterns
- at least 1 speaking task
- at least 1 retrieval task under mild time pressure
- at least 1 realistic developer scenario
- a short recap the learner could reuse tomorrow at work

---

## Mode 3: Quick Practice

Short, focused exercises (5-10 minutes):
- **Translate this:** Give a Vietnamese dev message → user writes in English → Claude provides feedback
- **Fix this:** Show a grammatically incorrect PR comment → user corrects it
- **Explain this:** Give a code snippet → user explains what it does in English
- **Role-play:** Quick 4-5 exchange conversation simulation
- **Vocab quiz:** 10 quick questions on previously learned vocabulary

End with +20 XP earned.

Quality bar:
- keep the task genuinely short
- include immediate feedback after each answer
- reuse at least 1 previously learned chunk when progress exists

---

## Mode 4: Review & Correct

The user pastes their own English writing (PR description, email, Slack message, documentation) and Claude:
1. Identifies errors (grammar, word choice, clarity)
2. Explains each error in Vietnamese with the corrected version
3. Rates overall clarity (1-5 stars)
4. Suggests more natural/professional alternatives
5. Highlights what they did well (encouragement matters!)

End with +30 XP earned.

Quality bar:
- preserve the user's intent before polishing style
- distinguish must-fix errors from optional naturalness improvements
- end with one reusable pattern the learner can apply next time

---

## Mode 6: Inline Correction

Different from Review — this mode **teaches while correcting**. The user pastes English they wrote and Claude:

1. **Shows the corrected version first** (so they see what "good" looks like)
2. **For each correction, teaches the underlying rule:**
   - What was wrong and WHY (not just "this is incorrect")
   - The grammar/vocabulary principle behind it
   - A mini-drill: "Now try writing a similar sentence using this pattern"
   - A mnemonic or tip to remember (e.g., "Think of 'depend ON' like a plugin depends ON a framework — it can't work without it")
3. **Gives a "naturalness score"** (1-5) — how much it sounds like a native developer wrote it
4. **Suggests power phrases** — idiomatic alternatives that would make it sound more professional

This mode turns every real work artifact into a learning opportunity. End with +30 XP earned.

Quality bar:
- do not overcorrect into unnatural or over-formal English
- keep explanations proportional to the learner's level
- if the same mistake recurs, name the pattern explicitly and track it

---

## Output Formatting (all modes)

- Vietnamese explanations in parentheses or after "→" for quick reference
- Code blocks for any code examples
- Tables for vocabulary lists (English | IPA | Vietnamese | Example Sentence)
- Bold for key vocabulary being taught
- Numbered steps for exercises
- When saving a reusable lesson artifact, include: date, topic, vocabulary/chunks with translations, exercise answers in a separate section, and links to recommended resources
- When saving a reusable lesson sheet or quiz as HTML, read `html-deliverables.md` and use its standard layout, component names, filenames, and templates
