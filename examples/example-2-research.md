# Example: Research Lead — "Dr. Vasquez"

> A computational biology research lead runs the Initiative pipeline on a multi-year project corpus. 214 notes spanning literature reviews, experiment logs, grant applications, collaborator meeting notes, and conference prep.

---

## Stage 1: Scan

# Initiative Scan

**Collection:** vasquez-lab-notes
**Total notes:** 214
**Date range:** 2024-03-11 to 2026-02-08
**Structure:** Nested — `/literature/`, `/experiments/`, `/grants/`, `/meetings/`, `/drafts/`, `/admin/`

### Naming conventions
Literature notes prefixed with first author and year (`Chen2024 - membrane dynamics review.md`). Experiment logs date-prefixed (`2025-06-14 GFP-tagged run 3.md`). Meeting notes follow `meeting - [person/group] - [date].md`. Grant drafts use version numbers (`NSF CAREER v4.md`).

### Topic clusters
1. **Protein folding dynamics** (~52 notes) — the core research question; computational models and experimental validation
2. **Membrane interaction modeling** (~38 notes) — secondary workstream; simulation frameworks and benchmarking
3. **Cryo-EM methodology** (~29 notes) — technique-specific notes on data collection and processing pipelines
4. **Grant writing** (~24 notes) — NSF CAREER, NIH R01 supplement, internal seed grants
5. **Collaborator communications** (~31 notes) — meeting notes with Dr. Okafor (Stanford), Dr. Lindström (KTH), and the Bhatt lab
6. **Publication drafts** (~18 notes) — manuscript sections, figure planning, reviewer response drafts
7. **Lab management** (~22 notes) — student onboarding, equipment, protocols

### Activity timeline
Steady baseline with three spikes: (1) Jun–Aug 2024 — initial cryo-EM method development, heavy literature review; (2) Mar–May 2025 — burst of experiment logs around the GFP-tagged membrane assay series; (3) Nov 2025–Feb 2026 — grant deadline push and publication drafting. Collaborator meetings are distributed evenly but shift from monthly to biweekly starting Oct 2025.

### Note quality distribution
- **High-signal** (~45%) — experiment logs with data, grant narratives, manuscript drafts, decision records
- **Medium-signal** (~35%) — literature notes, meeting summaries, brainstorming docs
- **Low-signal** (~20%) — admin notes, equipment logs, scheduling fragments

### Raw observations
The `/experiments/` folder has a gap: 11 GFP-tagged assay logs from Mar–May 2025, then nothing until a single note in Sep 2025 titled `GFP series - where we left off.md`. The phrase "force field parameterization" appears in 23 notes across all folders, often framed as an open question.

---

## Stage 2: Goals

# Initiative Goals

**Derived from:** 87 notes read / 214 total
**Last updated:** 2026-02-08

### Motivations
1. **"Bridge the resolution gap"** — recurring phrase in grants and talks; Vasquez believes computational prediction and experimental validation are too disconnected in the field and her lab can close that gap.
2. **Establish the lab's identity** — multiple notes about "what we're known for"; tension between being a methods lab vs. a biology lab.
3. **Mentor the next generation** — 4 notes on student development philosophy; this is personal, not just professional.

### Goal tree

#### 1. Publish the unified folding-membrane paper [explicit]
> Evidence: `drafts/unified-paper-outline-v3.md`, 6 meeting notes with Dr. Okafor discussing scope, and `journal/2025-12-01 the paper question.md` — "Do we publish the folding results alone or wait for the membrane connection?"

**1.1 Resolve the force field parameterization question** [explicit — but unresolved]
- [ ] Compare Amber ff19SB vs. CHARMM36m for the membrane-proximal region
- [ ] Run the benchmark suite Dr. Lindström proposed in the Jul 2025 meeting

**1.2 Complete the GFP-tagged validation series** [explicit — stalled]
- [ ] Restart the assay series (paused since May 2025)
- [ ] Process cryo-EM data from runs 1–3

**1.3 Write the manuscript** [explicit]
- [ ] Draft methods section (cryo-EM pipeline)
- [ ] Produce figures 3–5 (simulation vs. experiment overlays)

#### 2. Secure multi-year funding [explicit]
> Evidence: NSF CAREER application (v4, submitted), NIH R01 supplement (in prep), seed grant for cryo-EM time.

**2.1 Submit NIH R01 supplement** [explicit]
- [ ] Finalize preliminary data section with GFP results
- [ ] Get letter of support from Dr. Okafor

**2.2 Prepare for NSF CAREER review panel** [weak inference]
- [ ] Compile broader impacts evidence
- [ ] Prepare a 3-minute summary of preliminary results

#### 3. Resolve the core methodological question: force field parameterization [strong inference]
> Evidence: Raised in `literature/Chen2024 - membrane dynamics review.md` (Jun 2024), appears in 23 notes. Three workstreams depend on it. Never resolved.

**3.1 Synthesize the competing approaches in the literature** [strong inference]
- [ ] Write a comparison of the 4 main parameterization strategies
- [ ] Identify which approach aligns with available compute budget

### Goal tensions
- **"Publish incremental" vs. "wait for the complete story":** The folding results alone are publishable. The unified folding-membrane paper would be higher impact but requires resolving force field parameterization first. Vasquez has oscillated on this since Dec 2025 — 4 notes argue each side.
- **Methods lab vs. biology lab identity:** The grants lean "methods" (novel cryo-EM pipeline), the publications lean "biology" (protein dynamics insights). These attract different reviewers and different funding panels.

---

## Stage 3: Blockers

# Initiative Blockers

**Last updated:** 2026-02-08

### Unresolved questions
1. **Force field parameterization for membrane-proximal simulations** — first raised in `Chen2024 - membrane dynamics review.md` (Jun 2024), revisited in 23 notes over 20 months. Three workstreams (folding paper, membrane modeling, GFP validation) all depend on this choice. No decision made.
   - Blocks: Goal 1.1, Goal 1.2, Goal 3
2. **Publish incremental or wait?** — first explicit mention in `journal/2025-12-01 the paper question.md`. Four notes argue both sides. No resolution.
   - Blocks: Goal 1.3

### Revisited without resolution
1. **Force field parameterization** — 23 notes, 20 months. The thinking has broadened (more approaches considered) but not deepened (no benchmarks run, no commitment to test). Each new literature note adds another option without evaluating existing ones.
   - Pattern: broadening without deepening
   - Blocks: Goal 1.1, Goal 3
2. **Lab identity (methods vs. biology)** — surfaces in grant framing, publication targeting, and student project design. Never explicitly addressed as a strategic question.
   - Pattern: implicit oscillation
   - Blocks: Goal 2 (grant positioning)

### Stalled work
1. **GFP-tagged membrane assay series** — 11 experiment logs Mar–May 2025, then a single "where we left off" note in Sep 2025 and silence. Partial data from runs 1–3 exists but hasn't been processed.
   - Blocks: Goal 1.2, Goal 2.1 (preliminary data for NIH)
2. **Cryo-EM processing pipeline documentation** — started in Aug 2024, last touched Nov 2024. Pipeline is reportedly functional but undocumented, creating a bus-factor risk.
   - Blocks: Goal 1.3 (methods section)

### Meta-insights from change patterns
1. **Broadening without deepening: Force field parameterization** — 23 notes over 20 months have added 4 competing approaches without benchmarking any of them. This is the textbook pattern: scope expanding faster than decisions are made. The question doesn't need more literature review. It needs a benchmark — even an imperfect one.
   - Evidence: `literature/` folder contains 6 force-field-related reviews added in 2025; zero corresponding entries in `/experiments/`
   - Suggests: a time-boxed computational experiment (72-hour benchmark) that directly compares 2 top candidates on the lab's actual system
2. **Burst-then-silence: GFP-tagged assay series** — 11 logs in 10 weeks, then 9 months of silence. The "where we left off" note from Sep suggests the work was paused, not abandoned, but no reactivation occurred. The most likely explanation: the force field question made the results hard to interpret, so the experimental work stalled waiting for a computational answer that never came.
   - Evidence: `experiments/2025-09-08 GFP series - where we left off.md` — "Results from runs 1–3 are ambiguous without knowing which force field to use for the overlay"
   - Suggests: the force field blocker is upstream of the experimental stall; resolving it reactivates both workstreams simultaneously
3. **Oscillation: Publish-now vs. wait** — 4 notes in Dec–Jan alternate between "the folding data stands alone" and "but the full story is so much better." This oscillation tracks a values tension (pragmatic career move vs. scientific ambition), not a missing data point. New data won't resolve it; a decision framework will.
   - Evidence: `journal/2025-12-01`, `journal/2025-12-19`, `journal/2026-01-06`, `drafts/paper-scope-options.md`
   - Suggests: an explicit decision with a deadline — e.g., "If force field is unresolved by March 15, publish the folding results alone"

### Blocker severity
| Blocker | Goals affected | Severity |
|---------|---------------|----------|
| Force field parameterization unresolved (20 months) | 1.1, 1.2, 3 | Critical |
| GFP assay series stalled (9 months) | 1.2, 2.1 | Critical |
| Publish-now vs. wait unresolved | 1.3 | Moderate |
| Lab identity not explicitly decided | 2 | Low |

---

## Stage 4: Actions

# Initiative Actions

**Last updated:** 2026-02-08
**Derived from:** 3 goals, 6 blockers, 3 meta-insights

### Do now
1. **Run a 72-hour benchmark comparing Amber ff19SB vs. CHARMM36m on the lab's membrane-proximal test system**
   - Serves: Goal 3 (force field resolution), Goal 1.1
   - Unblocks: The keystone blocker — every other workstream waits on this
   - Why now: Twenty months of literature review haven't resolved this. The question needs empirical data, not more reading. The compute budget can absorb a 72-hour run. Dr. Lindström proposed this benchmark in July; the only missing step is running it.

2. **Process cryo-EM data from GFP-tagged runs 1–3**
   - Serves: Goal 1.2, Goal 2.1 (preliminary data for NIH)
   - Unblocks: GFP series stall, NIH supplement preliminary data
   - Why now: This data exists and hasn't been touched. Even with force field ambiguity, the raw structural data has standalone value for the grant application.

3. **Set a publication decision deadline: "If force field benchmark doesn't converge by March 15, publish the folding results alone"**
   - Serves: Goal 1.3
   - Unblocks: Publish-now vs. wait oscillation
   - Why now: The oscillation has run for 2 months without new information. A deadline converts it from an open-ended values question to a time-bounded pragmatic one.

4. **Draft the methods section for the cryo-EM pipeline while the pipeline is still fresh**
   - Serves: Goal 1.3
   - Unblocks: Stalled documentation
   - Why now: The pipeline is functional but undocumented. The longer this waits, the harder it gets. And the methods section is needed regardless of which publication path is chosen.

### Do next
1. **Write the NIH R01 supplement preliminary data section** — depends on processing the cryo-EM data (Do Now #2).
   - Serves: Goal 2.1
2. **Restart GFP-tagged assay series (runs 4+)** — depends on force field benchmark results to guide experimental design.
   - Serves: Goal 1.2

### Backlog
1. **Write the lab identity memo** — explicitly address "methods lab vs. biology lab" for grant strategy alignment. Goal 2.
2. **Document cryo-EM pipeline for student handoff** — Goal 1.3, lab sustainability.

---

## Stage 5: Brief

# Initiative Brief

**Collection:** vasquez-lab-notes
**Updated:** 2026-02-08
**Previous brief:** first run

### Where you are

Two years into a multi-workstream research program with strong foundations (functional cryo-EM pipeline, promising preliminary data, active collaborations) but a single unresolved methodological question that has quietly stalled three workstreams. The lab is productive — grants submitted, collaborations active, students supervised — but the core scientific output (the unified paper) has been blocked for months by a decision that keeps getting deferred in favor of more literature review. Funding pressure is mounting: the NIH supplement needs preliminary data that exists but hasn't been processed.

### The critical path

**Keystone blocker: The force field parameterization question has been open for 20 months.** First raised in a literature review in June 2024, it now appears in 23 notes across every folder. Three workstreams depend on it: the unified paper can't be written without it, the GFP experimental series stalled because results were uninterpretable without it, and the membrane modeling workstream is waiting on it. Twenty months of reading have *broadened* the options (4 competing approaches) without *deepening* any of them (zero benchmarks run).

**Dependency chain:** Run a force field benchmark (72 hours of compute) → interpret the GFP-tagged runs 1–3 → restart the experimental series → produce the simulation-vs-experiment overlay figures → write the unified paper OR decide to publish folding results alone → strengthen the NIH supplement with published or in-press results.

**Highest-leverage action: Run the benchmark.** Not another literature review — a computational experiment. Dr. Lindström proposed the protocol in July 2025; the compute is available; the test system is defined. 72 hours of wall-clock time that has been deferred for 8 months. This single action un-dams three stalled workstreams simultaneously.

### Active goals
1. **Publish the unified folding-membrane paper** — blocked by force field question and stalled experiments. Publication path undecided.
2. **Secure multi-year funding** — NSF CAREER submitted; NIH R01 supplement needs preliminary data.
3. **Resolve force field parameterization** — the silent dependency underneath everything else.

### Critical blockers
1. **Force field parameterization unresolved (20 months)** — resolve by running the Lindström benchmark protocol.
2. **GFP assay series stalled (9 months)** — resolve by processing existing data and restarting runs after benchmark.
3. **Publication path undecided** — resolve by setting a decision deadline tied to the benchmark timeline.

### Observations
- **Literature review has become a form of productive procrastination.** Six force-field literature notes were added in 2025 with zero corresponding experiments. Each review adds options without eliminating any. The question left the "needs more reading" phase a year ago; it's been in the "needs empirical data" phase ever since.

- **The experimental stall is downstream of the computational stall, not independent.** The "where we left off" note from September explicitly says the GFP results are uninterpretable without the force field decision. This means the experimental pause wasn't about lab capacity or student availability — it was about a decision that wasn't made. Resolving the computational question reactivates the experimental work automatically.

- **The publish-now-or-wait oscillation is a values question wearing a data costume.** The 4 notes debating it don't introduce new evidence; they re-weigh the same tradeoffs (career pragmatism vs. scientific ambition). More data won't resolve this. A deadline will.

- **Collaborator meeting frequency doubled in October, right when internal progress slowed.** Meeting notes with Okafor, Lindström, and Bhatt shifted from monthly to biweekly. The content shifted too: more "status update" and less "working session." This may indicate the collaborators are compensating for stalled internal momentum with more communication overhead.

---

## Stage 6: Proposals

# Initiative Proposals

**Last updated:** 2026-02-08
**Derived from:** goals, blockers, actions, brief
**Critical path reference:** Force field parameterization unresolved for 20 months — run the Lindström benchmark

### Do immediately

1. **Synthesize the 4 competing force field parameterization approaches into a decision-ready comparison**
   - Type: analysis
   - Effort: deep (~2 hours)
   - Serves: Goal 3 (force field resolution)
   - Unblocks: Force field benchmark design — clarifies which 2 candidates to benchmark first
   - Why now: The founder of this stall is information overload. 23 notes contain overlapping and sometimes contradictory assessments of the approaches. A side-by-side comparison — same criteria applied to each — has never been produced. The benchmark can't be designed well without it.
   - Spec: Read all 23 notes mentioning force field parameterization. For each of the 4 approaches (Amber ff19SB, CHARMM36m, OpenMM custom, hybrid Lindström protocol), extract: stated strengths, stated limitations, compute cost, compatibility with the lab's cryo-EM pipeline, and which collaborator advocates for it. Present as a comparison table. Add a section: "What would a decisive benchmark need to test?" pulling from Dr. Lindström's July proposal.
   - Output: `literature/force-field-comparison-synthesis.md`

2. **Search for recent publications (2025–2026) on membrane-proximal force field benchmarks**
   - Type: research
   - Effort: medium (~40 min)
   - Serves: Goal 3, Goal 1.1
   - Unblocks: Possible that the field has moved since the last literature note (Oct 2025) — new benchmarks may narrow the options
   - Why now: Four months since the last literature check. The field moves fast; someone may have published exactly the comparison the lab needs.
   - Spec: Search PubMed, bioRxiv, and Google Scholar for force field benchmarking papers published after Oct 2025 with terms: membrane protein, force field, benchmark, CHARMM36m, ff19SB. Summarize any relevant findings in 1 page. Flag if any paper directly compares the approaches on a similar system.
   - Output: `literature/force-field-recent-2025-2026.md`

3. **Trace the GFP-tagged assay series: compile a status document from the 12 experiment logs**
   - Type: analysis
   - Effort: medium (~30 min)
   - Serves: Goal 1.2
   - Why now: Before the series can restart, someone needs to know exactly where it left off. The "where we left off" note is vague; the actual experiment logs contain the precise state.
   - Spec: Read all 12 GFP-tagged assay notes chronologically. Produce a one-page status document: what was run, what data was collected, what was processed, what remains unprocessed, and what the "where we left off" note's question about force field interpretability specifically refers to. Include a "restart checklist" of what's needed to resume.
   - Output: `experiments/gfp-series-status-summary.md`

### Propose to human

1. **Draft a publication decision memo with a March 15 deadline**
   - Type: draft
   - Effort: quick (~20 min)
   - Serves: Goal 1.3
   - Why propose: This is a strategic decision for the PI. The Collaborator can draft the framework, but the decision is the human's.
   - Brief: A one-page memo laying out both options (publish folding alone vs. wait for unified paper), the criteria for choosing, and a decision deadline of March 15. Structured as: "If [condition] by [date], then [path A]; otherwise [path B]." Framed to make the decision mechanical rather than agonizing.

2. **Prepare a 1-page preliminary data summary for the NIH R01 supplement**
   - Type: preparation
   - Effort: medium (~45 min)
   - Serves: Goal 2.1
   - Why propose: Grant content is high-stakes and needs PI review.
   - Brief: Pull the strongest preliminary results from the experiment logs and cryo-EM data. Organize into a 1-page narrative suitable for the preliminary data section. Flag where GFP processing (once completed) would strengthen the case.

### Queue for later
1. **Compile a "state of collaborations" summary** — meeting frequency doubled but content thinned. A summary of what each collaborator is contributing and what's needed from them would clarify whether the biweekly cadence is productive. After the benchmark runs.
2. **Audit the cryo-EM pipeline documentation gap** — once the methods section is drafted, compare it against what a new student would need to independently run the pipeline. Lab sustainability issue, not urgent.
