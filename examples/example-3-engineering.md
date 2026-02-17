# Example: Engineering Manager — "Jordan"

> A new engineering manager inherits a team's knowledge base and runs the Initiative pipeline on it. 312 documents spanning design docs, post-mortems, RFCs, sprint retros, and team process notes accumulated over 2+ years by the previous EM and the team.

---

## Stage 1: Scan

# Initiative Scan

**Collection:** atlas-team-docs
**Total notes:** 312
**Date range:** 2023-11-02 to 2026-02-10
**Structure:** Nested — `/design-docs/`, `/rfcs/`, `/post-mortems/`, `/retros/`, `/roadmap/`, `/process/`, `/oncall/`, `/misc/`

### Naming conventions
Design docs follow `DD-[number] [title].md` (e.g., `DD-047 Event Pipeline Redesign.md`). RFCs follow `RFC-[number] [title].md`. Post-mortems are date-prefixed (`2025-03-14 Checkout Latency Incident.md`). Sprint retros are `retro-[sprint number].md`. Roadmap docs are quarterly (`Q3-2025 Roadmap.md`).

### Topic clusters
1. **Platform migration (Kafka → Pulsar)** (~54 docs) — design docs, migration plans, rollback procedures, risk assessments
2. **Feature delivery** (~72 docs) — specs, implementation notes, launch checklists for user-facing features
3. **Incidents and reliability** (~38 docs) — post-mortems, oncall runbooks, SLO dashboards
4. **Sprint process** (~48 docs) — retros, velocity tracking, planning notes
5. **Architecture and infrastructure** (~41 docs) — system design, dependency maps, capacity planning
6. **Team operations** (~29 docs) — hiring, onboarding, 1:1 templates, career ladder discussions
7. **Roadmap and strategy** (~18 docs) — quarterly plans, OKR drafts, stakeholder alignment docs
8. **Stalled/abandoned** (~12 docs) — RFCs and design docs with `[ABANDONED]` or `[ON HOLD]` prefixes

### Activity timeline
Steady cadence with retros every 2 weeks. Spikes: (1) Apr–Jun 2024 — Kafka-to-Pulsar migration planning (12 design docs in 10 weeks); (2) Sep–Nov 2024 — reliability push after the checkout latency incident (8 post-mortems, SLO framework introduced); (3) Aug–Oct 2025 — feature sprint for the enterprise launch. Notable gap: Q1 2025 has fewer docs than any other quarter — 14 total vs. an average of ~35.

### Note quality distribution
- **High-signal** (~40%) — design docs with decisions recorded, post-mortems with action items, RFCs with explicit status
- **Medium-signal** (~35%) — retros with recurring themes, roadmap docs, planning notes
- **Low-signal** (~25%) — stub design docs never completed, duplicate drafts, process docs that describe aspirational workflows never adopted

### Raw observations
Three RFCs and two design docs carry the `[ON HOLD]` prefix with no corresponding "resumed" or "cancelled" documents. The most recent quarterly roadmap (`Q4-2025 Roadmap.md`) lists 6 priorities; the sprint retros from the same period reference different work. The retros from sprints 38–44 (Jul–Oct 2025) all mention "migration fatigue" in the "what's not working" section.

---

## Stage 2: Goals

# Initiative Goals

**Derived from:** 96 docs read / 312 total
**Last updated:** 2026-02-10

### Motivations
1. **"Don't be the team that's always migrating"** — phrase from `retro-42.md`, echoed in multiple retros. The team values shipping user-visible work but feels trapped in infrastructure churn.
2. **Reliability as identity** — after the checkout latency incident, the team adopted SLOs and an oncall overhaul. Multiple retros frame reliability as "what Atlas is known for."
3. **Technical excellence with user impact** — the previous EM's notes consistently frame infra work as serving feature velocity, not as an end in itself.

### Goal tree

#### 1. Complete the Kafka-to-Pulsar platform migration [explicit]
> Evidence: 54 docs, 3 roadmap mentions, dedicated migration tracker. Started Apr 2024. Currently ~60% complete per `migration-status-jan-2026.md`.

**1.1 Migrate the remaining 12 producer services** [explicit]
- [ ] Complete batch 3 (services: OrderEvents, InventorySync, PricingEngine)
- [ ] Run load tests on Pulsar topic partitioning for high-throughput producers

**1.2 Decommission Kafka clusters** [explicit — but blocked]
- [ ] Validate zero-traffic on migrated topics for 30 days
- [ ] Get SRE sign-off on Pulsar monitoring coverage

**1.3 Update all oncall runbooks for Pulsar** [explicit]
- [ ] Rewrite 8 Kafka-specific runbooks
- [ ] Run a game day on the new stack

#### 2. Ship the enterprise dashboard (Q1 2026 commitment) [explicit]
> Evidence: `Q4-2025 Roadmap.md`, 3 design docs, product partnership notes. External deadline: March 30.

**2.1 Implement role-based access controls** [explicit]
- [ ] Finish DD-051 implementation (in progress)
- [ ] Write integration tests for SSO flow

**2.2 Build the analytics export feature** [explicit]
- [ ] Complete RFC-019 design review (pending since Dec)
- [ ] Implement CSV and API export paths

#### 3. Reduce oncall burden to sustainable levels [strong inference]
> Evidence: 7 consecutive retros mention oncall toil. Two engineers requested oncall exemptions. `oncall-health-Q4.md` shows page volume up 40% since migration began.

**3.1 Eliminate top 5 oncall noise sources** [strong inference]
- [ ] Tune alerting thresholds for the 3 Kafka-Pulsar dual-running services
- [ ] Fix the flaky InventorySync health check (mentioned in 4 post-mortems)

### Goal tensions
- **Platform migration vs. feature shipping:** The migration has consumed ~40% of team capacity for 22 months. Enterprise dashboard has a hard external deadline. Both are "top priority" in the roadmap, which means neither is.
- **Reliability investment vs. feature velocity:** The post-incident SLO framework added process (error budgets, SLO reviews) that competes with sprint capacity. Retros show the team values it but resents the time cost.
- **Previous EM's vision vs. current reality:** The roadmap and design docs reflect the previous EM's priorities. Jordan (new EM) hasn't yet articulated whether these are still the right priorities.

---

## Stage 3: Blockers

# Initiative Blockers

**Last updated:** 2026-02-10

### Unresolved questions
1. **"Do we finish the migration before enterprise launch, or pause it?"** — raised in `retro-44.md` (Oct 2025) by two engineers. No decision recorded. The migration and enterprise work continue in parallel, splitting focus.
   - Blocks: Goal 1, Goal 2
2. **RFC-019 (analytics export) design review** — submitted Dec 8, 2025. No review comments. No decision. Blocks enterprise dashboard feature work.
   - Blocks: Goal 2.2

### Revisited without resolution
1. **Migration timeline** — 6 planning docs over 22 months, each with revised completion dates. Original estimate: Q2 2025. Current estimate: "Q2 2026 at current pace." The scope hasn't changed; the pace is slower than planned. No doc addresses *why* the estimates keep slipping or what would change the trajectory.
   - Pattern: broadening (adding caveats and risk factors without reducing uncertainty)
   - Blocks: Goal 1

### Contradictions
1. **Q4-2025 Roadmap vs. actual sprint work** — the roadmap lists 6 priorities in ranked order: (1) enterprise dashboard, (2) Pulsar migration batch 3, (3) SLO review automation, (4) API versioning, (5) oncall runbook refresh, (6) tech debt sprint. Sprint retros from the same period show the team spent ~50% of capacity on items not on this list — incident response, unplanned Kafka firefighting, and cross-team support requests.
   - Status: unresolved — the roadmap was never updated
   - Blocks: Goal 1, Goal 2, Goal 3

### Stalled work
1. **RFC-012: Service Mesh Adoption** — `[ON HOLD]` since Aug 2024. No cancellation. No revisit. Originally motivated by the migration.
   - Blocks: potentially Goal 1.2 (decommissioning dependencies)
2. **DD-038: Event Schema Registry** — `[ON HOLD]` since Nov 2024. Was part of the Pulsar migration plan. Dropped without explanation.
   - Blocks: Goal 1
3. **RFC-015: Automated Rollback Framework** — `[ON HOLD]` since Mar 2025. Post-mortem from the checkout incident recommended it. Never started.
   - Blocks: Goal 3

### Meta-insights from change patterns
1. **Roadmap-reality divergence (systematic)** — This isn't a one-time miss; it's structural. In every quarter since Q2 2024, the roadmap lists priorities that don't match what the retros show was actually worked on. The gap is consistent: unplanned work (incidents, firefighting, cross-team requests) absorbs 40–50% of capacity, but roadmaps are planned as if the team has 100% of its time. No planning doc accounts for the interrupt load.
   - Evidence: `Q2-2024 Roadmap.md` through `Q4-2025 Roadmap.md` vs. `retro-31` through `retro-48`
   - Suggests: the planning process needs to explicitly budget for interrupt-driven work, or the interrupt sources need to be reduced. The current approach — aspirational roadmaps that everyone knows are fiction — erodes trust.
2. **Stalled work accumulation** — Three initiatives put on hold with no triage. Each was motivated by a real need (service mesh, schema registry, automated rollbacks). None was explicitly cancelled. They linger in the backlog, creating ambiguity: are these still planned? Should new work account for them? The absence of a "we are not doing this" decision is itself a blocker.
   - Evidence: RFC-012, DD-038, RFC-015 — all `[ON HOLD]`, none revisited
   - Suggests: a one-time triage session: for each stalled item, explicitly cancel, reschedule, or decompose into something achievable
3. **Migration fatigue signal** — 7 consecutive retros (sprints 38–44) mention "migration fatigue" or equivalent. The team's energy for the Pulsar migration is depleted. Continuing at the current pace risks both the migration quality and team morale. The retros are saying this clearly; nothing in the planning docs acknowledges it.
   - Evidence: `retro-38.md` through `retro-44.md`, "what's not working" sections
   - Suggests: either pause the migration with an explicit restart date, or create a forcing function (dedicated migration sprint, temporary staffing) that changes the trajectory

### Blocker severity
| Blocker | Goals affected | Severity |
|---------|---------------|----------|
| Migration vs. enterprise — no prioritization decision | 1, 2 | Critical |
| Roadmap-reality divergence (structural) | 1, 2, 3 | Critical |
| Three stalled initiatives unresolved | 1, 3 | Moderate |
| RFC-019 review pending (7 weeks) | 2.2 | Moderate |
| Migration fatigue (team morale) | 1 | Moderate |

---

## Stage 4: Actions

# Initiative Actions

**Last updated:** 2026-02-10
**Derived from:** 3 goals, 7 blockers, 3 meta-insights

### Do now
1. **Write a "state of Atlas" document** — an honest assessment of where the team is: what's actually in progress, what's stalled, what the real capacity is (including interrupt load), and what the priorities should be for Q1 2026. This is Jordan's first act as new EM.
   - Serves: All goals
   - Unblocks: Roadmap-reality divergence, migration-vs-enterprise question
   - Why now: Jordan inherited priorities set by the previous EM. The team needs to hear "I see the actual situation" before any reprioritization will have credibility. This document creates the foundation for every subsequent decision.

2. **Triage the three stalled initiatives (RFC-012, DD-038, RFC-015)** — for each, decide: cancel, reschedule with a date, or decompose into a smaller deliverable. Write the decision down. Remove `[ON HOLD]` status.
   - Serves: Goal 1, Goal 3
   - Unblocks: Stalled work ambiguity
   - Why now: These have been in limbo for 6–18 months. The cost of leaving them unresolved is ambiguity that infects every planning conversation. The decisions are individually small; the collective clarity is significant.

3. **Make the migration-vs-enterprise prioritization decision explicit** — write a one-page decision doc: either pause migration for Q1 to hit the enterprise deadline, or accept enterprise slippage to finish migration. Include the reasoning. Share with the team.
   - Serves: Goal 1, Goal 2
   - Unblocks: The critical split-focus blocker
   - Why now: The enterprise deadline is March 30. At current pace, both the migration and the dashboard are at risk. Continuing to do both at 50% capacity produces two 50% results. The decision needs to be made this week.

4. **Review and approve/reject RFC-019 (analytics export)** — it's been pending for 7 weeks. Either approve it and unblock the implementation, or reject it with specific feedback.
   - Serves: Goal 2.2
   - Unblocks: Enterprise dashboard feature work
   - Why now: A pending RFC with no feedback is a silent signal that reviews don't matter. The team will stop writing RFCs if they sit unreviewed.

5. **Introduce an interrupt budget in sprint planning** — based on retro data, explicitly allocate 40% of sprint capacity to unplanned work. Plan features and migration against the remaining 60%.
   - Serves: All goals
   - Unblocks: Roadmap-reality divergence
   - Why now: The pattern is 8 quarters old. Every roadmap ignores interrupt load. The fix is simple: plan realistically. Doing this in the next sprint planning meeting immediately improves the team's relationship with its own commitments.

### Do next
1. **Address migration fatigue with the team** — acknowledge it explicitly in a team meeting. Either announce a migration pause, a dedicated sprint to close batch 3, or a timeline to completion. The team has been saying "this isn't working" for 7 retros; they need to hear that someone listened.
   - Serves: Goal 1
   - Why not now: Depends on the prioritization decision (Do Now #3).

2. **Rewrite the Q1 2026 roadmap** — after the state-of-Atlas doc and the prioritization decision, create a realistic plan that reflects actual capacity.
   - Serves: All goals
   - Why not now: Depends on Do Now #1, #3, and #5.

### Backlog
1. **Run a game day on the Pulsar oncall stack** — Goal 1.3. Important but not urgent until more services are migrated.
2. **Refresh career ladder documentation** — Goal (unlisted, team health). Previous EM's notes suggest this was planned for Q4 2025 and didn't happen.
3. **Reconcile post-mortem action items with the backlog** — 3 post-mortems have action items marked "TODO" with no corresponding tickets.

---

## Stage 5: Brief

# Initiative Brief

**Collection:** atlas-team-docs
**Updated:** 2026-02-10
**Previous brief:** first run

### Where you are

New EM, inherited team. The team has been productive — 312 documents in 2 years, consistent retro cadence, a real reliability culture built after a painful incident. But the inherited state has a structural problem: priorities on paper don't match work in practice, and three initiatives were shelved without resolution. A 22-month platform migration is at 60% completion with declining team energy, while an externally-committed enterprise feature has a hard March 30 deadline. Both are listed as "top priority." The previous EM's departure left a prioritization vacuum that Jordan hasn't yet filled.

### The critical path

**Keystone blocker: The team has two top priorities and no decision about which one wins.** The Kafka-to-Pulsar migration has consumed 22 months and is 60% done. The enterprise dashboard has a hard external deadline of March 30. Sprint retros show the team splitting capacity roughly 50/50, and both tracks are falling behind. Seven consecutive retros have flagged "migration fatigue." The roadmap says both are #1. No one has made the call.

**Dependency chain:** Write the state-of-Atlas document (honest assessment of capacity and status) → make the explicit migration-vs-enterprise prioritization call → introduce interrupt budgeting in sprint planning → the roadmap finally reflects reality → team trust recovers → stalled initiatives get triaged → Q2 planning starts from a real baseline instead of an aspirational one.

**Highest-leverage action: Write the "state of Atlas" document.** Jordan's first act as new EM should be demonstrating that they see the real situation — not the roadmap fiction. This document names the roadmap-reality gap, the migration fatigue, the stalled initiatives, and the prioritization vacuum. It's the precondition for every other fix. Without it, any reprioritization will feel arbitrary because the team hasn't agreed on a shared picture of where they are. The document itself isn't the decision; it's what makes decisions possible.

### Active goals
1. **Complete Kafka-to-Pulsar migration** — 60% done, 22 months in, team fatigued, no revised completion date.
2. **Ship enterprise dashboard by March 30** — design docs in progress, RFC-019 review pending for 7 weeks, capacity split with migration.
3. **Reduce oncall burden** — page volume up 40% due to dual-running systems, 7 retros flagging the issue.

### Critical blockers
1. **No explicit prioritization between migration and enterprise** — resolve by making the call and writing it down.
2. **Roadmap-reality divergence (8 quarters running)** — resolve by introducing interrupt budgeting and planning against realistic capacity.
3. **Three stalled initiatives in limbo** — resolve by one-time triage: cancel, reschedule, or decompose each.

### Observations
- **The team has been telling leadership the answer for 7 months.** Retros 38–44 all say "migration fatigue." Retros consistently show 40–50% of capacity going to unplanned work. The signal is clear and persistent. What's missing isn't data — it's someone acting on the data. Jordan's arrival is the opportunity.

- **The roadmap is aspirational, not operational.** Every quarterly roadmap since Q2 2024 has listed more work than the team could complete, and none has accounted for interrupt load. The team has learned to treat the roadmap as a wish list, not a commitment. This erodes planning credibility and makes prioritization conversations feel performative.

- **Stalled initiatives create a hidden cost: ambiguity.** RFC-012, DD-038, and RFC-015 are not consuming resources, but they are consuming decision space. Every planning conversation implicitly asks "are we still doing the service mesh thing?" without anyone answering. Explicitly cancelling or rescheduling them is nearly free and disproportionately clarifying.

- **The reliability culture is real but under strain.** The post-incident SLO adoption was genuine and well-executed. But the SLO review process competes with an already-overloaded sprint, and oncall page volume is up 40% because of dual-running systems that exist only because the migration is half-done. Finishing or pausing the migration is also a reliability decision.

---

## Stage 6: Proposals

# Initiative Proposals

**Last updated:** 2026-02-10
**Derived from:** goals, blockers, actions, brief
**Critical path reference:** No explicit prioritization between migration and enterprise — write the state-of-Atlas document

### Do immediately

1. **Produce a capacity analysis from the retro data**
   - Type: analysis
   - Effort: medium (~45 min)
   - Serves: All goals (via the state-of-Atlas document)
   - Unblocks: Roadmap-reality divergence — provides the data Jordan needs to make the interrupt-budget argument
   - Why now: Jordan is about to write the state-of-Atlas doc. The strongest version of that document includes hard numbers, not just impressions. The retros contain enough data to compute approximate planned-vs-actual capacity utilization for the last 4 quarters.
   - Spec: Read retros 31–48 (18 retros, ~18 months). For each sprint, extract: (1) what was planned, (2) what was completed, (3) what unplanned work was mentioned. Calculate planned-vs-actual completion rate per sprint. Compute the average interrupt load as a percentage. Present as a simple table plus a one-paragraph summary: "Over the last 18 months, the team completed X% of planned work per sprint, with ~Y% of capacity going to unplanned work."
   - Output: `process/capacity-analysis-retro-data.md`

2. **Compile a stalled-work triage document for the three ON HOLD initiatives**
   - Type: analysis
   - Effort: medium (~30 min)
   - Serves: Goal 1, Goal 3
   - Unblocks: Stalled work ambiguity — gives Jordan a one-page summary to make triage decisions from
   - Why now: Jordan shouldn't need to read 3 full RFCs and 2 design docs to triage these. A one-page summary of each (why it started, why it stalled, what depends on it, what cancelling it would mean) makes the triage meeting 10 minutes instead of an hour.
   - Spec: For each stalled initiative (RFC-012 Service Mesh, DD-038 Schema Registry, RFC-015 Automated Rollbacks), read the original doc and any related notes. Produce a one-page summary per initiative: original motivation, current relevance (has anything changed since it was shelved?), what depends on it, and the three options (cancel / reschedule / decompose) with tradeoffs for each.
   - Output: `process/stalled-work-triage-prep.md`

3. **Build a timeline visualization of the Kafka-to-Pulsar migration**
   - Type: analysis
   - Effort: medium (~35 min)
   - Serves: Goal 1
   - Why now: The migration has 54 documents but no single-page timeline showing what happened when. For the state-of-Atlas document, Jordan needs to see (and show the team) the full arc: when it started, when estimates slipped, when energy dropped, where it is now.
   - Spec: Read the migration-related docs chronologically. Produce a timeline: key milestones, original vs. revised estimates, batch completion dates, and retro sentiment about the migration over time. Format as a markdown timeline with dates and one-line descriptions. Add a "current status" section with the concrete remaining work items.
   - Output: `process/migration-timeline.md`

### Propose to human

1. **Draft the "state of Atlas" document**
   - Type: draft
   - Effort: deep (~1.5 hours)
   - Serves: All goals
   - Why propose: This is Jordan's first major communication to the team. It needs Jordan's voice and judgment. But the blank-page problem is real — a first draft that synthesizes the pipeline findings would let Jordan edit and own it rather than starting from scratch.
   - Brief: A 2–3 page document covering: team capacity reality (citing the retro analysis), migration status and fatigue, enterprise deadline risk, stalled initiatives, and the prioritization question. Honest tone. Ends with "here's what I propose we decide together" rather than unilateral mandates. Positioned as Jordan's "I've read everything, here's what I see" document.

2. **Draft a sprint planning template that includes interrupt budgeting**
   - Type: draft
   - Effort: quick (~20 min)
   - Serves: All goals (roadmap-reality fix)
   - Why propose: Changes team process — needs EM buy-in and team discussion.
   - Brief: A modified sprint planning template that starts with "available capacity" (total minus historical interrupt rate), plans work against the reduced number, and includes a "buffer" section for anticipated unplanned work. Simple enough to adopt without a process overhaul.

### Queue for later
1. **Cross-reference post-mortem action items with the team backlog** — 3 post-mortems have untracked TODOs. After the state-of-Atlas doc settles priorities, these should be triaged. Not urgent until the team has a realistic roadmap to add them to.
2. **Summarize the SLO framework adoption and its impact on oncall** — the reliability culture is an asset worth documenting clearly, especially as the new EM evaluates what's working. After the immediate prioritization crisis is resolved.
