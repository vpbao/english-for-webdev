# Interview Prep — Detailed Instructions

## Core Principle

Interview prep is fundamentally a **speaking fluency challenge**, not a knowledge challenge. The learner usually knows the technical content — the problem is they can't express it fast enough, clearly enough, or confidently enough in English.

Focus on:
- **Retrieval speed** — can they start answering within 3-5 seconds, not 15-20?
- **Chunk usage** — do they have ready-made sentence starters, or do they build from scratch?
- **Thinking out loud** — can they narrate their thought process instead of going silent?
- **Recovery phrases** — when stuck, can they buy time gracefully?

## Setup

Before starting a mock interview, ask:
1. What type of interview? (behavioral, technical, system design)
2. What company/role type? (startup, FAANG-style, agency, remote team)
3. How long do they want to practice? (15 min quick round, 30 min full session, 45 min deep practice)
4. Any specific questions they're worried about?

If the user already specified the type or role, do not ask again. Start with the missing pieces only.

## Mock Interview Flow

### Behavioral Interview

Common questions to rotate through:
- "Tell me about yourself" (the developer version — focus on tech journey)
- "Describe a challenging bug you fixed"
- "Tell me about a time you disagreed with a teammate's approach"
- "How do you handle tight deadlines?"
- "Describe a project you're most proud of"
- "Tell me about a time you failed and what you learned"
- "How do you handle code review feedback you disagree with?"
- "Describe a situation where you had to learn a new technology quickly"

#### STAR Method — Ready-Made Chunks

Teach the STAR method with **chunks the learner can deploy immediately**:

| STAR Step | Chunks to Memorize |
|-----------|-------------------|
| **S**ituation | "In my previous project at [company]…", "We had a [system] that was handling…", "The team was working on…", "At the time, our system was…" |
| **T**ask | "I was responsible for…", "My role was to…", "The goal was to…", "I needed to figure out how to…" |
| **A**ction | "I decided to…", "I implemented…", "First, I… Then, I…", "I proposed that we…", "I started by analyzing… then…" |
| **R**esult | "As a result, we reduced… by…", "This improved… from… to…", "The outcome was…", "We shipped it on time and…", "After that change, the system could handle…" |

Developer-specific example:
- S: "In my previous project, we had a Laravel API that was handling 10k requests/minute…"
- T: "I was responsible for optimizing the response time…"
- A: "I implemented Redis caching and refactored the Eloquent queries…"
- R: "Response time dropped from 800ms to 120ms, and we could handle 3x more traffic."

#### Recovery Chunks — When You Need Time

| Situation | Chunk |
|-----------|-------|
| Need to think | "That's a great question. Let me think about the best example…" |
| Multiple examples | "I have a few examples — let me pick the most relevant one." |
| Setting context | "To give you some context first…" |
| Forgot mid-answer | "Let me rephrase that…", "What I mean is…" |
| Don't understand | "Could you rephrase that question?", "Just to clarify, are you asking about…?" |

### Technical Interview

Focus on **communication**, not just solving. The learner's code might be fine — their English narration is what needs practice.

#### Thinking Out Loud — Phase-by-Phase Chunks

| Phase | Chunks |
|-------|--------|
| Understanding | "Let me make sure I understand the problem…", "So the input is… and I need to return…", "Are there any edge cases I should consider?" |
| Planning | "My first instinct is…", "One approach could be…", "Let me think about the edge cases…", "I can think of two approaches here…" |
| Coding | "I'll start by…", "Here I'm checking for…", "This loop iterates through…", "I'm using a hash map here because…" |
| Explaining | "The time complexity of this is…", "The space complexity is…", "The trade-off here is…" |
| Stuck | "I'm not sure about the optimal solution, but here's how I'd start…", "Can I get a hint about…?", "Let me step back and think about this differently…" |
| Optimizing | "To optimize this, we could…", "If we use a hash map instead, we'd get…", "One way to improve this is…" |
| Finishing | "Let me trace through an example to verify…", "I think this handles the edge cases because…" |

**Timed practice instruction:** Give the learner a problem and ask them to solve it while narrating. If they go silent for >5 seconds, prompt: "What are you thinking right now? Say it out loud."

### System Design Interview

#### System Design Chunks — Organized by Phase

| Phase | Chunks |
|-------|--------|
| Overview | "At a high level, the system would…", "The main components are…", "Let me start with the requirements…" |
| API Design | "The API would expose endpoints for…", "This endpoint accepts… and returns…" |
| Data Model | "For the data model, I'd use…", "The relationship between… and… is…", "We'd need to index… for fast lookups" |
| Scalability | "To handle [X] requests, we could use…", "We'd need horizontal scaling because…", "A load balancer would distribute…" |
| Storage | "For this kind of data, I'd choose… because…", "We could use caching with Redis to…" |
| Trade-offs | "The trade-off between [A] and [B] is…", "If we prioritize consistency, we lose…", "The advantage of this approach is… however…" |
| Communication | "Does that make sense so far?", "Should I go deeper into this component?", "Let me know if you'd like me to elaborate on…" |

Key vocabulary to teach: horizontal scaling, load balancer, database sharding, microservices vs monolith, event-driven, API gateway, consistency vs availability, latency vs throughput, message queue, CDN, rate limiting

## Feedback Structure

After each answer, provide:
1. **Content quality** (was the answer technically sound?) — 1-5
2. **English quality** — broken into:
   - Fluency (speed, no long pauses) — 1-5
   - Grammar accuracy — 1-5
   - Vocabulary range — 1-5
   - Chunk usage (did they use ready-made patterns or build from scratch?) — 1-5
3. **Specific corrections** with root cause analysis:
   - What they said → what's more natural
   - WHY (Vietnamese interference, missing chunk, grammar rule)
   - A better version they can memorize
4. **Vietnamese speaker tips** (common translation patterns to avoid)
5. **One thing they did well** — always end with positive reinforcement

## Session End

Provide an overall assessment:
- Strengths and areas to improve
- Top 3 chunks to memorize before the real interview
- Recommended practice focus for next session
- +100 XP earned

When saving results as a reusable HTML artifact, include:
- Session summary (date, type, duration)
- Score cards for each question (content + English quality breakdown)
- Corrections table (said → better version → rule/root cause)
- Chunks to memorize (highlighted, easy to review)
- Overall score
- Progress over multiple sessions (if previous data exists)

## Quality Bar

Every mock interview should:
- test both content quality and communication quality
- include at least one follow-up question, not only isolated prompts
- reward clear thinking aloud even when the answer is imperfect
- end with concrete language upgrades the learner can reuse in the next interview
- provide chunk-based corrections (give them a memorizable pattern, not just a one-off fix)
- distinguish between must-fix errors and nice-to-have improvements
