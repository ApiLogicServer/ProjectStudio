<!--
title: Full Demo Video — Storyboard (Show / Say)
Status: draft script, not yet recorded
Audience: Enterprise Architects and Devs — this video's job is to establish
credibility and invite further investigation, not to carry the entire
argument. See cs-mgr-video-strategy.md for the full reasoning behind every
structural choice here.
Source: build_and_test/genai-logic/README.md (gold: org_git/Docs/docs/Manager-readme.md)
-->

# Full Demo Video — Storyboard

**Target length:** ~6-7 minutes. Three real enterprise stories (Allocation,
Surtax, CLVS) each need genuine screen time to read as real, not staged —
this is not a video that can be cut down to 3 minutes without losing the
thing that makes it credible.

**Narrator:** First-person or voiceover, talking to camera + screen capture.
Confident, unhurried, no hype-voice. A serious business person addressing a
colleague, respectfully, as a peer — not a teacher, not AI trying to sound
hip. See cs-mgr-video-strategy.md's tone section: every line's confidence
level should match what's actually been proven, no more, no less. State
things flatly; let the evidence carry the weight.

**Core rule for every section:** no section repeats a phrase from another
section. Say each idea once, where it lands hardest, and move on. Never
read the README aloud — every line below is a compressed, spoken version of
a README idea, not a quotation of it.

**Never say "governance" until section 5.** Show the specific, concrete
failure (unreadable code, a bug, a bypass) and let the viewer arrive at the
word themselves. Section 5 is the one place it's earned and spoken aloud.

---

## 1. AI is great, but... (0:00–1:00)

| SHOW | SAY |
|---|---|
| cs-mgr README hero section, on screen. Click open "AI is great — but logic-as-code is hard to Read, Trust, and Maintain" briefly — not the full detail, just enough to establish the shape of the claim. Cut to the `credit_service.py` procedural file, scroll briefly — don't read it, just let the viewer see ~200 lines go by. | "AI is remarkable at writing code. Business logic is where it struggles — and business logic is usually half the effort on a real system, the half that decides whether it's actually correct. Left alone, AI writes this: two hundred lines, for five requirements. It shipped bugs. Not obvious ones — the kind that only show up when a customer's order gets reassigned to someone else." |

**Why this opens the video:** this is the "answer the unasked question"
section — the failure is shown concretely (the file, the bug), never
labeled "governance gap." An enterprise viewer who's lived this recognizes
it before being told what it is.

---

## 2. Rules make logic Read, Trust, Maintain (1:00–2:15)

| SHOW | SAY |
|---|---|
| Cut to `check_credit.py` — five lines, on screen, held long enough to actually read. Then a quick view of the running basic_demo system: F5, Admin App, an order. Trigger the "change quantity to something absurd, save" moment — real time, no narration during the click, hold on the failure dialog for a beat of silence. | "Same five requirements. This time: five rules, not two hundred lines. Watch what happens when I try something the rule doesn't allow." *(save happens, fails, hold silent)* "It fails. Every time, from every caller — API, an AI agent, this admin app, a partner system — because the rule fires at one commit point. There's no second door." |

**What NOT to include here:** the dependency-graph mechanism, the property
table, the two-blockquote takedown/rebuttal from the README's section 5.
That's README-depth content — verify-at-your-own-pace material. The video
only needs the felt result (readable, and it actually fires), not the
argument for why it's structurally guaranteed to.

---

## 3. That enables enterprise systems from requirements (2:15–5:15)

Three real stories, in escalating order — familiar, then astonishing, then
credible. Each one needs to breathe; don't compress these into a
highlight reel.

### 3a. Allocation — the recognizable pattern (2:15–3:15)

| SHOW | SAY |
|---|---|
| Allocation demo running — cascade allocation of costs to departments/GL. Show the prompt or requirements briefly, then the running result. | "Here's a system type you already know: allocating costs across departments and GL accounts. Built the same way — requirements in, a working system out. Nothing exotic about the business problem. What's different is how it got built." |

### 3b. Surtax — straight from the regulation (3:15–4:15)

| SHOW | SAY |
|---|---|
| The actual CBSA prompt file on screen — short, ~9 lines, held long enough to read. Then the resulting rules file, briefly. | "This one's different. This is the actual prompt that built a working steel-tariff duty calculator for Canada Customs — CBSA. Not a paraphrase of the regulation. The regulation, cited by section number, in nine lines. That's what became the system you're looking at." |

### 3c. CLVS — the real world (4:15–5:15)

| SHOW | SAY |
|---|---|
| CLVS system — show it working against an existing database schema, and a partner XML message being mapped in. | "No magic left in this one — just a system meeting the world as it actually is. A partner sends data in their own XML format, not ours — mapped straight in, against an existing database, the kind you already have, not a clean slate. A team had been building this the conventional way, for months. The governed version caught a compliance exposure in the eight figures that they'd missed." |

**⚠️ Before recording:** the duration claim ("built in TIME") is a live
discrepancy across published materials — Sierra pitch says one day, the Gov
By Arch article says two days. Do not speak a number in this section until
that's resolved and one source is corrected to match the other. As
scripted above, no duration is spoken — keep it that way until fixed.

**Why this order:** Allocation earns trust with something familiar before
asking the viewer to process something novel (Surtax). CLVS closes the
climax because it's the one that answers "will this survive contact with
our actual systems" — the natural handoff into section 5's infrastructure
reassurance.

---

## 4. The rule file, quiet (5:15–5:35)

| SHOW | SAY |
|---|---|
| Cut to one plain rule file from any of the three stories above — whichever reads cleanest on screen. No chat window. No narration for a beat. Just the file. | *(silence, 2-3 sec)* "That's the governance the enterprise needs — to read, trust, and maintain the system." |

**This is the emotional turn of the video** — from awe (three systems, one
from a regulation) to relief (and here's what's actually left, plain and
ordinary, once the AI is done). Brief. Do not explain the rule file's
contents — the point is that it doesn't need explaining. This is the one
place "governance" is spoken aloud — it's a callback to what the viewer
just watched, not a new claim.

---

## 5. Scaling to the enterprise (5:35–6:15)

| SHOW | SAY |
|---|---|
| Fast cuts — a few seconds each — across: Kafka/EAI integration, MCP discovery, AI Rules, a custom UI, and a generated health-check report. Checklist pace, not demo pace — nothing here gets its own explanation. | "Read, Trust, Maintain is the core of governance. The rest of the platform is built around it. Enterprise integration. AI agents can find and query it through MCP. Custom UIs built safely against the same governed API. And reports generated from the running system, so a compliance reviewer can check the work in minutes, not by reading code." |

**Deliberately excluded from the video, README-only:** the two-funnels
architecture diagram, and any detail on what the three governance reports
actually contain. Mentioned, not unpacked — see strategy doc.

---

## 6. Close (6:15–6:45)

| SHOW | SAY |
|---|---|
| Back to the README hero section, or a simple end card with the repo/Codespaces link. Hold ~5 sec. | "Everything you just watched is real, running software — not a mockup. The README goes deeper. The AI assistant sitting in that workspace will answer anything it didn't cover. Open it, and see what it builds from your own requirements." |

**Note:** do not restate "Read, Trust, and Maintain" or "governance"
again — both are spent, in sections 2 and 4. This close is explicitly
inviting further investigation (per the video's actual job — a credential,
not the whole case), not summarizing what was just proven.

---

## Timing Notes

- Running total as scripted: ~6:45. The three-story section (2:15–5:15) is
  three minutes of the roughly seven — that's intentional, it's the climax,
  and each story needs real screen time to read as genuine rather than a
  highlight reel.
- Section 2's trigger/fail moment must run in real time, unhurried, same
  discipline as the glws script's equivalent moment — the credibility of
  the whole video rests on the viewer seeing it happen, not an edited trick.
- Section 4 is the shortest and quietest section in the video by design.
  Resist the temptation to explain it, extend it, or add narration beyond
  the single line — the silence before it is doing real work.
- If the runtime needs to come down, trim words per section, not sections
  themselves — every section here was chosen deliberately against a "cut or
  keep" decision during planning (see cs-mgr-video-strategy.md).
