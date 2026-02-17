# Example: Solo Founder — "Meridian"

> A solo founder building a developer tools product runs the Initiative pipeline on 7 months of notes. 537 notes spanning product specs, investor conversations, user research, and strategy pivots.

---

## Stage 1: Scan

# Initiative Scan

**Collection:** meridian-vault
**Total notes:** 537
**Date range:** 2025-07-14 to 2026-02-12
**Structure:** Nested — `/product/`, `/investors/`, `/research/`, `/journal/`, `/misc/`

### Naming conventions
Mix of date-prefixed journal entries (`2025-11-03 standup thoughts.md`), topic-named specs (`CLI auth flow v3.md`), and meeting logs (`call - Redpoint - Nov 7.md`). Status prefixes `[DRAFT]` and `[WIP]` appear on ~40 notes.

### Topic clusters
1. **Product positioning** (~68 notes) — taglines, comparisons, one-pagers, pitch variants
2. **Architecture & technical specs** (~82 notes) — system design, API surface, CLI design
3. **User research** (~45 notes) — interview transcripts, feedback logs, persona drafts
4. **Investor relations** (~61 notes) — pitch decks, meeting notes, term sheet analyses
5. **Go-to-market** (~34 notes) — launch plans, pricing experiments, channel strategy
6. **Journal / working notes** (~180 notes) — daily reflections, standup logs, idea dumps
7. **Competitor analysis** (~28 notes) — feature comparisons, positioning maps
8. **Hiring / team** (~19 notes) — job descriptions, org chart thinking
9. **Misc / orphaned** (~20 notes) — fragments, one-off captures

### Activity timeline
Three distinct bursts: (1) Jul–Aug 2025 — initial product conception, architecture deep-dives; (2) Oct–Nov 2025 — investor outreach and pitch iteration; (3) Jan–Feb 2026 — product pivot toward "developer workflow engine." User research concentrated in Sep–Oct 2025, then drops sharply. Journal entries are continuous but thin from Dec 2025.

### Note quality distribution
- **High-signal** (~30%) — specs, pitch decks, interview transcripts, decision logs
- **Medium-signal** (~40%) — journal entries with partial reasoning, meeting summaries
- **Low-signal** (~30%) — AI-generated session recaps, stub notes, duplicate drafts

### Raw observations
The `/product/` folder contains 11 files with "positioning" in the title, spanning Jul 2025 to Feb 2026. At least three contain nearly identical opening paragraphs with different framings. The most recent user interview transcript is dated Oct 22, 2025 — nearly four months ago.

---

## Stage 2: Goals

# Initiative Goals

**Derived from:** 124 notes read / 537 total
**Last updated:** 2026-02-12

### Motivations
1. **"Make the CLI the IDE"** — a phrase repeated in 9 notes; the founder believes terminal-native developers are underserved by GUI-first tools.
2. **Own the workflow layer** — multiple notes argue that the opportunity is "below the editor, above the shell." This isn't a feature; it's a category belief.
3. **Ship before someone else does** — urgency language in 6+ journal entries: "window is closing," "Warp is getting closer to this."

### Goal tree

#### 1. Ship Meridian v1 to early adopters [strong inference]
> Evidence: "v1 scope" appears in 14 notes; 3 separate launch timeline drafts exist (Aug, Nov, Jan). No launch has occurred.

**1.1 Define v1 scope** [explicit — but unresolved]
- [ ] Write a scope exclusion document listing what v1 is NOT
- [ ] Freeze feature list for 30 days

**1.2 Build the core CLI experience** [explicit]
- [ ] Finish `meridian init` onboarding flow (WIP since Nov)
- [ ] Implement config sync (spec exists, no code)

**1.3 Create onboarding for first 10 users** [weak inference]
- [ ] Write quickstart guide
- [ ] Set up feedback channel

#### 2. Close pre-seed funding [explicit]
> Evidence: 61 investor-related notes, 4 pitch deck versions, active conversations with Redpoint and Amplify.

**2.1 Finalize pitch deck** [explicit]
- [ ] Update deck to reflect Jan 2026 pivot
- [ ] Add demo video or live walkthrough

**2.2 Advance Redpoint conversation** [explicit]
- [ ] Send follow-up with updated metrics after Dec call

#### 3. Resolve product positioning [strong inference]
> Evidence: 68 positioning notes, 11 files with "positioning" in title, rewritten continuously since July.

**3.1 Commit to a single positioning frame** [strong inference]
- [ ] Write one paragraph, get 3 external reactions
- [ ] Kill competing drafts

### Goal tensions
- **Ship fast vs. get positioning right:** The founder wants to launch but keeps rewriting the pitch framing. Shipping would force positioning to settle; waiting to "get it right" delays shipping.
- **Investor timeline vs. product readiness:** Active investor conversations imply a demo is expected. No demo exists.

---

## Stage 3: Blockers

# Initiative Blockers

**Last updated:** 2026-02-12

### Unresolved questions
1. **"CLI-first or CLI-also?"** — first raised in `product strategy Aug 9.md`, revisited in 5 subsequent notes without resolution. Blocks: Goal 1.1 (v1 scope), Goal 3 (positioning).
2. **Pricing model** — three options floated (usage-based, seat-based, open-core) across 6 notes. No decision. Blocks: Goal 2.1 (pitch deck).

### Revisited without resolution
1. **Product positioning** — 68 notes, 11 title-level rewrites spanning 7 months. The framing oscillates between "developer workflow engine," "CLI copilot," and "terminal-native IDE." Each rewrite adds nuance but doesn't converge.
   - Pattern: oscillation
   - Blocks: Goal 3, Goal 2.1

### Stalled work
1. **User research program** — burst of activity Sep–Oct 2025 (12 interviews, 3 persona drafts). Last interview Oct 22. No research since the Jan pivot. The pivot invalidated some prior findings, but no new research replaced them.
   - Blocks: Goal 1.3, Goal 3.1
2. **`meridian init` onboarding flow** — marked `[WIP]` since Nov 14, 2025. Two partial implementations referenced but not completed.
   - Blocks: Goal 1.2

### Meta-insights from change patterns
1. **Rewrite cluster: Positioning (11 rewrites)** — Classic sign that the framing needs a forcing function. Writing another positioning doc won't resolve it. What would: committing to 10 specific users and describing Meridian *to them*, or writing the anti-positioning ("here's what we're NOT").
   - Evidence: `positioning v1.md` through `positioning - new frame Feb.md`
   - Suggests: a scope exclusion document or a concrete user commitment
2. **Burst-then-silence: User research** — 12 interviews in 6 weeks, then nothing for 4 months. The pivot created a clean break, but the research muscle atrophied. The product is now being designed from first principles with no external input.
   - Evidence: `/research/` folder, last modified Oct 22
   - Suggests: even 2–3 lightweight conversations with target users would break the isolation
3. **Convergence: Technical architecture** — Architecture notes are getting shorter and more confident. The system design is nearly settled. This is the healthiest workstream.
   - Evidence: `system design v4.md` is half the length of v1 and twice as precise
   - Suggests: one more implementation push closes this

### Blocker severity
| Blocker | Goals affected | Severity |
|---------|---------------|----------|
| Positioning unsettled (11 rewrites) | 1.1, 2.1, 3 | Critical |
| User research silent since Oct | 1.3, 3.1 | Moderate |
| v1 scope undefined | 1, 2.1 | Critical |
| Pricing model unresolved | 2.1 | Moderate |

---

## Stage 4: Actions

# Initiative Actions

**Last updated:** 2026-02-12
**Derived from:** 3 goals, 6 blockers, 3 meta-insights

### Do now
1. **Write the v1 scope exclusion document** — one page listing what Meridian v1 is NOT (not an IDE, not a GUI, not multi-language at launch, not team features). Commit to it for 30 days.
   - Serves: Goal 1.1
   - Unblocks: Positioning oscillation, scope creep, undefined demo
   - Why now: This is the keystone. Positioning can't settle without a boundary. The pitch deck can't be updated without knowing what you're pitching. Architecture is ready; the gap is scope, not design.

2. **Write one positioning paragraph constrained by the exclusion list** — a single paragraph describing Meridian v1 to a terminal-native developer. No aspirational language. What it does today.
   - Serves: Goal 3.1
   - Unblocks: Pitch deck, positioning rewrite cycle
   - Why now: Once the exclusion list exists, this becomes a constrained problem instead of an open-ended one.

3. **Update pitch deck to reflect Jan 2026 pivot** — replace the "developer workflow engine" framing with whatever the exclusion-constrained paragraph says. Add the architecture diagram from `system design v4.md`.
   - Serves: Goal 2.1
   - Unblocks: Redpoint follow-up, Amplify next steps
   - Why now: Investor conversations are active. Stale deck = missed window.

4. **Schedule 3 conversations with target users about the pivoted product** — reach out to the most engaged interviewees from Oct (Dara K., Tomás R., and the Vercel contact) with the new framing.
   - Serves: Goal 1.3, Goal 3.1
   - Unblocks: User research silence
   - Why now: Four months without external input. Even brief conversations break the echo chamber.

### Do next
1. **Finish `meridian init` onboarding flow** — the WIP implementation from Nov. Revisit, decide what to keep, ship it.
   - Serves: Goal 1.2
   - Why not now: Depends on v1 scope being frozen first.

2. **Decide on pricing model** — pick one, test it with the 3 user conversations above.
   - Serves: Goal 2.1
   - Why not now: Lower leverage than scope and positioning. Can ride behind the user conversations.

### Backlog
1. **Write quickstart guide for first 10 users** — Goal 1.3
2. **Record a 2-minute demo walkthrough** — Goal 2.1
3. **Reconcile competing architecture notes from Aug vs. Nov** — Goal 1.2

---

## Stage 5: Brief

# Initiative Brief

**Collection:** meridian-vault
**Updated:** 2026-02-12
**Previous brief:** first run

### Where you are

Seven months in, mid-pivot, pre-launch. The technical architecture is nearly converged — the system design is sound and getting crisper. But the product wrapping (positioning, scope, pitch) has been rewritten continuously without settling. Active investor conversations with Redpoint and Amplify are creating pressure for a demo and a coherent story, but neither exists yet because v1 scope was never frozen. The product is being designed in isolation — no user input since October.

### The critical path

**Keystone blocker: v1 scope is undefined.** Positioning can't settle because the product boundary keeps moving. The pitch deck can't be updated because there's no stable product to pitch. A demo can't be built because there's no agreement on what to demonstrate. User conversations can't happen productively because there's nothing concrete to react to.

**Dependency chain:** Freeze v1 scope (write exclusion list) → positioning becomes a constrained problem → pitch deck tells one story → demo becomes buildable → investor conversations advance → user research restarts with a concrete artifact to test.

**Highest-leverage action: Write the v1 scope exclusion document.** Not a spec. Not a roadmap. A one-page list of what Meridian v1 is *not*. This resolves the positioning oscillation (11 rewrites become unnecessary when the boundary is fixed), unblocks the pitch deck update, and makes the first user conversations productive. One document, written in an afternoon, that unblocks four months of accumulated stuckness.

### Active goals
1. **Ship Meridian v1** — scope undefined; architecture ready; no launch date set.
2. **Close pre-seed funding** — active conversations; deck is stale; no demo.
3. **Resolve positioning** — 11 rewrites in 7 months; oscillating, not converging.

### Critical blockers
1. **v1 scope undefined** — resolve by writing a scope exclusion document.
2. **Positioning unsettled** — resolve by constraining to whatever v1 actually is.
3. **User research silent since Oct** — resolve by scheduling 3 conversations with prior interviewees.

### Observations
- **The architecture is ready; the narrative isn't.** Technical notes are converging while product notes are diverging. The founder knows what to build but can't describe it to anyone else. This is a communications problem disguised as a product problem.

- **User research stopped exactly when it was most needed.** The Jan pivot invalidated prior positioning research, but instead of talking to people about the new direction, the founder went inward. Four months of solo ideation produced 68 positioning notes and zero external data points.

- **Investor conversations are creating useful pressure, but the wrong kind.** The urgency is "update the deck" when the real urgency is "decide what you're building." Updating a deck without settling scope produces another positioning variant, not clarity.

- **The competitor anxiety ("Warp is getting closer") appears in journal entries but not in the product specs.** The competitive pressure is felt emotionally but isn't being channeled into concrete differentiation decisions.

---

## Stage 6: Proposals

# Initiative Proposals

**Last updated:** 2026-02-12
**Derived from:** goals, blockers, actions, brief
**Critical path reference:** v1 scope undefined — write the exclusion document

### Do immediately

1. **Research competitor positioning and v1 scopes**
   - Type: research
   - Effort: medium (~45 min)
   - Serves: Goal 3 (positioning), Goal 1.1 (v1 scope)
   - Unblocks: Positioning oscillation — seeing how competitors scoped *their* v1 provides a frame of reference
   - Why now: The exclusion document needs input. Knowing what Fig, Warp, and Charm shipped in their v1s — and what they explicitly left out — gives the founder concrete comparables instead of speculating in a vacuum.
   - Spec: Search for Fig, Warp, Charm, and Atuin. For each, find: (1) what their public v1/launch included, (2) what they explicitly said was out of scope, (3) their one-sentence positioning at launch vs. now. Write a 1-page comparison. Focus on scope boundaries, not features.
   - Output: `research/competitor-v1-scopes.md`

2. **Draft a v1 scope exclusion document**
   - Type: draft
   - Effort: medium (~30 min)
   - Serves: Goal 1.1
   - Unblocks: Keystone blocker — scope definition
   - Why now: This is the highest-leverage action in the pipeline. The Collaborator can produce a first draft that the founder edits, rather than the founder facing a blank page. Pull from the 14 notes that mention "v1 scope" to extract what the founder has already implicitly excluded.
   - Spec: Read all notes containing "v1", "scope", "not yet", "later", "post-launch." Extract every instance where the founder said something is out of scope, deferred, or not-for-now. Compile into a clean exclusion list with the format: "Meridian v1 is NOT: [item] — [why, with source note]." Include a one-paragraph summary of what v1 IS, derived from the exclusion boundaries.
   - Output: `product/v1-exclusion-draft.md`

3. **Synthesize the 11 positioning rewrites into a comparison table**
   - Type: analysis
   - Effort: medium (~40 min)
   - Serves: Goal 3 (positioning)
   - Why now: The founder has written 11 positioning attempts but never compared them side-by-side. Seeing the evolution — what changed, what stayed constant — may reveal the stable core that all versions share.
   - Spec: Read all 11 positioning documents chronologically. For each, extract: the one-sentence tagline, the target user, the key differentiator, and the competitive frame. Present as a table. Add a section at the bottom: "What never changed across all 11 versions" and "What changed every time."
   - Output: `product/positioning-evolution.md`

### Propose to human

1. **Draft outreach messages to Dara K., Tomás R., and the Vercel contact**
   - Type: draft
   - Effort: quick (~15 min)
   - Serves: Goal 1.3 (user research restart)
   - Why propose: These are external communications. The founder should review tone and decide whether to send.
   - Brief: Write three short, personal outreach messages referencing prior conversations and introducing the pivoted product direction. Keep them casual — "Hey, we talked in October about X, we've since shifted to Y, would love 20 minutes of your time."

2. **Prepare a "state of Meridian" one-pager for investor conversations**
   - Type: preparation
   - Effort: medium (~45 min)
   - Serves: Goal 2 (funding)
   - Why propose: Touches investor relations — needs founder review before any use.
   - Brief: A one-page document summarizing where Meridian is: what's built, what's changed since the last investor update, what the v1 scope is (once the exclusion doc is done), and what the ask is. Not a pitch deck — a status update for warm contacts.

### Queue for later
1. **Audit and deduplicate the `/product/` folder** — 68 positioning notes include significant redundancy. After scope freezes, archive superseded drafts. Not urgent until the exclusion doc settles things.
2. **Build a user research tracker** — if the founder restarts conversations, a simple log (who, date, key takeaways) prevents the burst-then-silence pattern from recurring.
