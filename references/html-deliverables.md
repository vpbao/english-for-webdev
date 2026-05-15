# HTML Deliverables

Use this reference when creating reusable HTML artifacts for:

1. lesson sheets
2. quizzes / quick-practice pages
3. progress reports

Do **not** create HTML for every interaction. Chat remains the default. HTML is for artifacts the learner may revisit.

---

## Shared Rules

### File names

| Artifact | File name |
|----------|-----------|
| Lesson sheet | `lesson-YYYY-MM-DD-topic-slug.html` |
| Quiz / practice | `quiz-YYYY-MM-DD-topic-slug.html` |
| Progress report | `english-progress-report.html` |

### Technical requirements

- Self-contained single-file HTML
- Inline CSS and inline JS
- Responsive down to mobile width
- No build step
- Use semantic HTML where possible
- Persist interactive state with `localStorage`
- Use Chart.js only for charts in progress reports
- Include Vietnamese support text where it removes friction, but keep English visible and central

### Visual system

Use the same token palette across all artifacts:

```css
:root {
  --bg: #0f1117;
  --surface: #1a1d27;
  --surface-2: #242838;
  --border: #2e3348;
  --text: #e2e4ed;
  --muted: #8b8fa8;
  --accent: #6c5ce7;
  --accent-soft: #a29bfe;
  --green: #00b894;
  --yellow: #fdcb6e;
  --red: #e17055;
  --blue: #74b9ff;
}
```

### Shared components

Every artifact should reuse these component ideas:

- `hero`: title, date, learner goal, and compact meta
- `card`: reusable content container
- `pill`: compact labels such as difficulty, XP, or review state
- `chunk-grid`: reusable phrase cards
- `callout`: short teaching note or memory hook
- `progress-bar`: XP or completion state
- `exercise`: one task with answer / feedback behavior
- `footer-note`: next action or homework

### Accessibility & UX

- Keep line length readable
- Buttons need visible hover/focus states
- Do not rely on color alone to signal correctness
- Prefer large tap targets on mobile
- If using timers, always provide a manual start/reset button
- Keep interactions useful even if JavaScript fails

---

## Lesson Sheet Template

Use this for reusable lessons the learner may revisit after chat.

### Required sections

1. Hero
2. Today’s goal
3. Chunks to activate
4. Micro-lesson / explanation
5. Timed speaking drill
6. Practice exercises
7. Corrections & common traps
8. Homework
9. Words / chunks to review

### Minimal HTML skeleton

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Lesson — [Topic]</title>
  <style>
    /* shared tokens + layout styles */
  </style>
</head>
<body>
  <main class="page">
    <header class="hero">
      <p class="eyebrow">Lesson</p>
      <h1>[Topic]</h1>
      <p>[One-sentence learner outcome]</p>
    </header>

    <section class="card">
      <h2>Today’s goal</h2>
      <p>[What the learner should be able to say or do]</p>
    </section>

    <section class="card">
      <h2>Chunks to activate</h2>
      <div class="chunk-grid">
        <!-- chunk cards -->
      </div>
    </section>

    <section class="card">
      <h2>Timed speaking drill</h2>
      <p>[30-second or 60-second prompt]</p>
      <button data-timer-start>Start timer</button>
      <output data-timer>00:30</output>
    </section>

    <section class="card">
      <h2>Practice</h2>
      <!-- exercises -->
    </section>

    <section class="card">
      <h2>Common traps</h2>
      <!-- corrections / diagnosis -->
    </section>

    <section class="card footer-note">
      <h2>Homework</h2>
      <p>[One realistic workplace action for tomorrow]</p>
    </section>
  </main>
  <script>
    // timer + localStorage progress hooks
  </script>
</body>
</html>
```

### Lesson-specific behavior

- Put reusable chunks above isolated vocabulary
- Include at least one timer-based speaking drill
- Show “why this mistake happens” for recurring Vietnamese-speaker traps
- Make the homework transfer directly into work life

---

## Quiz / Practice Template

Use this for reusable practice pages, not for every quick chat drill.

### Required sections

1. Hero
2. Instructions
3. Question set
4. Score summary
5. Review of missed items
6. Next practice suggestion

### Minimal HTML skeleton

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Quiz — [Topic]</title>
  <style>
    /* shared tokens + layout styles */
  </style>
</head>
<body>
  <main class="page">
    <header class="hero">
      <p class="eyebrow">Quiz</p>
      <h1>[Topic]</h1>
      <p>[What this quiz trains]</p>
    </header>

    <section class="card">
      <h2>How to use this</h2>
      <p>[Instructions]</p>
    </section>

    <section class="card">
      <h2>Questions</h2>
      <!-- question cards with answer inputs/buttons -->
    </section>

    <section class="card">
      <h2>Your score</h2>
      <div class="progress-bar"></div>
      <p data-score>[0 / N]</p>
    </section>

    <section class="card">
      <h2>Review</h2>
      <!-- missed items + explanations -->
    </section>
  </main>
  <script>
    // scoring + immediate feedback + localStorage persistence
  </script>
</body>
</html>
```

### Quiz-specific behavior

- Give immediate feedback
- Prefer production/retrieval tasks over pure recognition
- Reuse previously learned chunks when progress exists
- Track misses in a way that can inform future review
- When the quiz is meant to feed spaced repetition, include an optional **Update progress file** flow:
  - require all questions to be checked first
  - use first-attempt correctness for promotion logic
  - prevent duplicate XP awards for the same quiz
  - if direct file writing is available, let the learner choose `english-progress.md` and update it in place
  - clearly tell the learner to open the quiz in Chrome through `localhost` for reliable direct-write support, instead of assuming a double-clicked `file://` page will behave the same

---

## Progress Report Template

Use this for polished reusable reports when the user asks for progress or a visual summary.

### Required sections

1. Hero with level / XP / streak
2. XP progress
3. Skill radar
4. Words & chunks learned
5. Due-for-review items
6. Common mistakes
7. Badges
8. Next focus

### Minimal HTML skeleton

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>English Progress Report</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
  <style>
    /* shared tokens + layout styles */
  </style>
</head>
<body>
  <main class="page">
    <header class="hero">
      <p class="eyebrow">Progress report</p>
      <h1>Level [N] — [Title]</h1>
      <p>[XP] XP · [N]-day streak</p>
    </header>

    <section class="card">
      <h2>XP progress</h2>
      <div class="progress-bar"></div>
    </section>

    <section class="card">
      <h2>Skill radar</h2>
      <canvas id="skillRadar"></canvas>
    </section>

    <section class="card">
      <h2>Words & chunks learned</h2>
      <!-- table/list -->
    </section>

    <section class="card">
      <h2>What to review next</h2>
      <!-- due items -->
    </section>

    <section class="card">
      <h2>Next focus</h2>
      <p>[Most important recommendation]</p>
    </section>
  </main>
  <script>
    // Chart.js radar config + optional local state
  </script>
</body>
</html>
```

### Progress-specific behavior

- Visualize truthfully; do not overstate progress
- Emphasize the next bottleneck, not just the highest score
- Show due-for-review chunks, not only aggregate counts
- Keep the recommendation specific enough to drive the next session
