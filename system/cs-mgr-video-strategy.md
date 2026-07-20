<!--
title: Full/cs-mgr Video — Narrative Strategy (record of planning discussion)
Status: strategy record, not a shot list — script drafting comes next
Related: OBX-glws-video-script.md is a DIFFERENT video (glws, practitioner-facing).
This doc is for the full demo video, audience = Enterprise Architects and Devs,
scripted from the cs-mgr README (build_and_test/genai-logic/README.md, gold
source org_git/Docs/docs/Manager-readme.md).
-->

# Full Demo Video — Narrative Strategy

Two videos exist, for two different audiences, and they should not converge:

- **glws video** — practitioner-facing (BAs/PMs, day-to-day users), tech
  explanation to support usage. See `OBX-glws-video-script.md`.
- **Full demo video** (this doc) — Enterprise Architects and Devs, aimed at
  **legitimizing the stack** — establishing credibility and inviting further
  investigation, not carrying the entire argument alone.

## The video's actual job

The video is a **credential that the argument exists**, not the argument
itself. Success condition: the viewer concludes "this deserves a closer
look," not "I am now fully convinced." This is what makes the light-touch
choice correct rather than a compromise — the package around the video (see
below) means the video is never anyone's only shot.

This reframes the tone problem. The two failure modes aren't opposite ends
of a volume dial:

- **Huckster**: claim exceeds evidence (e.g. asserting "governance" before
  it's earned, skipping the mechanism because the punchline sounds better
  without it).
- **Dull**: evidence exceeds claim (undeselling real proof — the reparenting
  bug, "no second door," 40 years of this paradigm actually winning once
  already at Versata — by over-hedging).

Both are calibration failures, not volume failures. The fix: match the
confidence of each line to what's actually been proven, exactly. A
claim that's been stress-tested (see the README rigor pass this session
produced) can be stated flatly, with full conviction and no hedging —
that flat, unadorned confidence is the register that reads as neither
dull nor hucksterish. "The save failed. Here's why." lands harder than
any amount of added enthusiasm, because nothing is propping it up
rhetorically.

## Depth level: light touch

Considered light vs. deep, chose light — not as a lesser version of a
complete pitch, but because the video and README are different media
doing different jobs. The README's `<details>` architecture exists so a
skeptical reader can pause, click, and verify at their own pace — video
can't replicate that interaction model. Cramming README-level depth into
the video just reads the footnotes aloud with worse pacing.

The redundancy of the full package is what makes light-touch safe, not
just acceptable:

- **Video** — earns attention, orients, shows the climax.
- **README** — verification and depth at the reader's own pace (the
  `<details>` layers this session hardened).
- **Working software** — press F5, watch the save fail yourself; nothing
  has to be taken on faith.
- **AI assistant** — answers whatever specific doubt the other three
  didn't anticipate, primed by the same CE.

A claim that doesn't land for a given viewer in the video gets a second
shot in the README, a third against the running system, a fourth from the
AI directly. No single layer has to be someone's only shot — which is what
lets the video stay light without being incomplete.

## "Answer the unasked question," not "name the diagnosis"

Gemini's independent read (see `gemini_assessment.md` in this session)
and this session's own conclusion agree: **governance is the key issue
holding AI back in the enterprise, and this stack solves it.** That
sentence is the mission — and it must never be said aloud in the video.

Not because it's false — because *naming* it up front makes the video's
job persuasion (convince them governance matters), when the stronger move
is recognition (show them the specific failure they've already lived —
unreadable code, a reparenting bug, a rule silently bypassed — and let
them supply the word "governance" themselves). A conclusion the viewer
reaches on their own is trusted more than one they were told. It also
avoids the vendor-speak reflex: "governance" is a word every enterprise
tool claims now: it triggers pattern-matching to marketing if used before
it's earned.

The README already proves this approach works: the "AI is great, but..."
section never opens with "governance gap" — it opens with a concrete claim
(half the effort, and the half that determines correctness), walks through
three named failures, and only reaches the word **governed** once, deep in
section 3, after the reader has already felt the "save fails" moment
themselves. Same discipline applies to the video script.

**Where "governance" CAN be said aloud:** later, after it's earned — see
the RTM/governance closing beat below. By that point it's a callback to
vocabulary the viewer already agreed to, not an opening claim.

## Four-part narrative arc

1. **AI is great, but has a logic governance gap** (shown, not named as
   such — see above)
2. **Rules make Logic Read, Trust, Maintain (RTM)** — the mechanism,
   cs-mgr README's "What Makes Rules Declarative" / "How Declarative
   Rules Make Logic Easy to Read, Trust, and Maintain" sections
3. **That enables Enterprise Systems from Requirements** — the climax
   (see ordering below)
4. **Scaling to the Enterprise** — light-touch infrastructure checklist,
   framed as evidence for RTM/governance, not a fresh feature dump

Sections 3 and 4 are not swapped from the README's existing structure —
confirmed the README already has this right: "Scaling to the Enterprise"
contains the light-touch EAI/MCP/AI-Rules/Custom-UI list *and* transitions
directly into the three requirement-driven stories as its payoff. One
continuous section, light touch setting the stage for the climax.

## The climax: three enterprise stories, in escalating order

Two proof shapes, doing different rhetorical jobs:

- **Prompt → entire system** (Allocation, Surtax): proves the
  **compression** claim — plain description or cited regulation in, full
  system out. The more magical-looking demo; risks reading as "cool AI
  demo, doesn't apply to us" if shown without grounding.
- **Existing DB + real integration formats** (CLVS — XML-by-example):
  proves the **fits-into-my-world** claim — messy reality, not a curated
  example. Answers the skeptical architect's real unspoken objection:
  "will it survive contact with my actual systems?"

Chosen order — familiar → astonishing → credible:

1. **Allocation** — a recognizable enterprise pattern (cost allocation to
   depts/GL). Establishes "yes, this handles real business logic" without
   also asking the viewer to process something novel.
2. **Surtax** — "wait, straight from the actual regulation text??" Lands
   harder once the viewer is already oriented from #1.
3. **CLVS** — closes on "this is ready for the real world." Existing
   schema, real XML integration, the messiest and most credible of the
   three. Natural handoff into section 4's infrastructure reassurance.

(README's demo-catalog table reordered to match: Allocation → Surtax →
CLVS, in `build_and_test/genai-logic/README.md` and gold source
`org_git/Docs/docs/Manager-readme.md`.)

## The RTM/governance closing beat (new — not yet in the README)

The thing that most specifically resolves the viewer's underlying anxiety
(named in this session as "Wynford's fear" — the AI magic itself is what
increases anxiety, not what resolves it) hasn't been placed anywhere yet.
Insight: AI producing a system is impressive but does not, by itself,
reassure someone worried about control and correctness. What reassures is
that **after the AI's work is done, something durable and ordinary is left
behind** — plain rules, in a plain file, inspectable without the AI in the
loop at all.

Planned treatment:
- Occurs once, briefly, after the three stories — a quiet turn from awe to
  relief, not a fourth story.
- Any one of the three stories' rule files can carry it (whichever reads
  cleanest on camera) — not a specific fourth demo.
- Visual: cut to one plain rule file. No chat window. Near-silent. Contrast
  in energy from the three loud proof points is the point.
- Line (as refined in discussion): **"That's the governance the enterprise
  needs — to read, trust, and maintain the system."** RTM is the
  enterprise's own act (reads it, trusts it, maintains it), not a property
  the software earns — deliberately not phrased as "that's governance"
  (label slapped on afterward), but as what the enterprise does with what
  it's been given.
- This is the one place "governance" is said aloud — earned by this point,
  a callback to section 2's RTM payoff, not a new claim.

Section 4 (Scaling to the Enterprise) then follows as: **"RTM is the core
of governance — and here's proof it's fully addressed"** — reframing the
EAI/MCP/AI-Rules/custom-UI/reports list as evidence for the claim just
made, not a cold restart into a feature dump. This is also the bridge that
keeps the tone from resetting after the quiet RTM/governance moment.

Open item: whether section 4 needs any visual/tonal pause after the RTM
beat so the checklist doesn't bleed into and flatten that quiet landing,
or whether staying brief/low-key is sufficient on its own. Not resolved —
worth checking once the actual script is drafted and timed.

## What NOT to include in the video (keep in README only)

Identified during this session as genuinely strong material that risks
bogging the video down if shown rather than mentioned:

- The three governance reports (logic flow diagram, ad-libs report, health
  check) — proof-on-demand content, rewards someone already convinced.
- The two-funnels architecture diagram (design + runtime converging on one
  engine).

Decision: **mention, don't unpack** — same one-breath treatment as
EAI/MCP/AI-Rules in section 4, explicitly framed as evidence for RTM
(see closing-beat section above), not skipped and not elaborated on.
"Come back and study it" is the correct disposition for this content, not
"leave it out."

## Session artifacts referenced

- `gemini_assessment.md` — independent external read (Gemini) of the
  cs-mgr README, arrived at the same governance-gap/BRMS-vs-agentic-
  framework positioning without being fed it. Used here as corroboration,
  not narrated in the video.
- This session's README rigor pass (cs-mgr `README.md` sections "AI is
  great, but..." and "How Declarative Rules Make Logic Easy to Read,
  Trust, and Maintain") is the source material this video compresses —
  every claim in the video should be traceable to something in the README
  that has already survived the same scrutiny test.
