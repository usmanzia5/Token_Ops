# WaferZero — Founder Prep: Usman's Sections (Investor-Ready Draft)

**Company:** WaferZero — vertical TokenOps for semiconductor verification.
**One-liner:** *We connect AI spend to verified engineering outcomes — regression failures resolved, root causes accepted, coverage closed — so chip teams can see which AI tools actually produce verified silicon, and what each result costs.*
**Category:** AI unit-economics / ROI measurement, verticalized for design verification (DV).
**Stage framing (external):** Pre-seed. Founder-market fit from inside the industry, with direct network access to the exact buyers; immediate motion is a structured validation program converting that access into read-only design partners. *(Never pitch "we're just an idea with no revenue" — pitch the insight, the wedge, and the validation plan you're executing.)*

> **Scope of this doc:** Usman owns pitch sections **2, 4, 5, 6, 8** and supplies the technical/product risks feeding **10**. Each section below has (a) the investor-ready answer/positioning and (b) a short **"Still to nail down"** — the honest open items a good pre-seed founder walks in already chasing. Gurinder owns 1, 3, 7, 9, 10-final; keep answers consistent with his.

---

## The spine (read this first)

Three decisions hold the whole story together. Everything downstream inherits from these.

1. **We sell the ROI *join*, not a gateway.** The gateway/metering layer is commodity (LiteLLM, Portkey, Cloudflare, Datadog). Our product is the **prebuilt verification outcome model** that maps AI spend to the real DV chain: *failure → triage → accepted root cause → fix → passing rerun → coverage gain.* A horizontal tool can add a connector; it cannot cheaply add the domain model.

2. **We phase the product from *report* to *control plane*.** Land read-only (ingest exports, produce cost-per-accepted-outcome — no rip-and-replace, fast pilots, and it starts compounding our proprietary spend→outcome dataset on day one). Then earn the path: route by value, gate value-blind agents, and cut off spinning agent loops mid-flight. **The report is the wedge; the control plane is the moat.**

3. **We are vendor-neutral across every agent — internal, Cadence, Synopsys, Siemens.** The EDA incumbents own the tools *and* profit from more agent usage. They are a conflicted meter. Our defensibility is neutrality + a cross-customer dataset no single vendor or customer can assemble.

**The 10× in one sentence:** not 10× cheaper tokens — **10× better at answering "which AI spend produced verified silicon"**, because we are the only neutral layer that speaks coverage closure and regression health instead of generic task IDs.

---

## Section 2 — Problem, Pain Point, and Unique Insight

### The problem (state it as a decision failure, not a cost complaint)
Enterprises are scaling their **fastest-growing, highest-variance cost** with **zero ability to tell value from waste**. They can neither cut safely nor invest confidently — so most freeze. "AI costs too much" is a complaint with an obvious dumb fix ("cap it"). The fundable problem is the **inability to act rationally**:

> **"Management cannot confidently decide where to cut AI spending and where to increase it — so they either let it run uncontrolled or throttle their best work with a blind cap."**

This is what moves us from a **vitamin** (cost-cutting, first thing deferred in a downturn) to a **painkiller** (a decision they're forced to make). Our real competitor is **inertia**, and inaction has a compounding, invisible bill.

### Why token cost alone is not the problem
Falling token prices don't kill the category — usage volume, agent autonomy, context size, and multi-step workflows are growing faster than unit prices fall. And the spend is **value-blind**: a July 2026 study of agentic coding found the *same task* varies up to **30× in tokens**, and accuracy often **peaks at intermediate cost and degrades at the highest** — excess spend is usually unproductive looping, not deeper reasoning. The industry's own conclusion: **cost per *successful task* is the true metric, not token price.** That is precisely the number nobody can compute today.

### The unique insight (why *us*, and why it's non-obvious)
The spend→outcome join is a **race in software** (PRs, tickets, deploys are clean, public, API-first — Harness, Pay-i, Atlassian/DX are already there) but a **frontier in silicon**. In chip verification, "World B" — the outcome data — lives in **proprietary regression databases, coverage tools, and bug trackers**, joined to nothing. It is structurally unclaimed.

Two AMD verification engineers can see what a horizontal founder can't:
- The **outcome that matters** in DV isn't "PR merged" — it's **coverage closure, bugs found, regression pass rate**, and we know how those are recorded and where.
- **Agentic verification just shipped** (Cadence, Synopsys, Siemens, all 2026), so DV token spend is inflecting *right now* — and nobody is measuring whether an overnight agent run that burned $9K closed coverage, found a bug, or looped on the same failing seed 400× producing nothing.

**Insight one-liner:** *"In software, tying AI spend to output is getting solved. In silicon it's untouched — because the outcome data lives in tools nobody has connected. That's our wedge."*

### The cost of doing nothing (the deal-closer)
Inaction feels free; make it visibly expensive. Four parts: **(1)** 20–40% direct waste on the AI line (mirrors ~30% early-cloud waste); **(2)** compounding as agentic scales calls 10–100×; **(3)** the bigger, invisible cost — the high-ROI work they're **too blind to fund**; **(4)** ground ceded to rivals who *can* tell value from waste. *"The status quo is not free — here's what it costs you every month you wait."*

### What would disprove the thesis (walk in already holding this)
- DV token spend is still a **rounding error** today → attribution is premature.
- A DV manager, shown token-cost-per-coverage-point per agent/team, **shrugs** and reallocates nothing → it's a vitamin. **This is the single most important thing to validate with a real DV leader.**
- Outcome data is **too noisy** to attribute a coverage gain to one agent run.

**Still to nail down:** the exact firsthand anecdote (sanitized, no AMD IP) that makes the "value-blind agent run" real for an investor; one credible dollar figure for current DV AI spend at a representative team.

---

## Section 4 — Product Wedge, Value Proposition, Technology, and Vision

### The wedge (what we build first)
**AI-assisted regression failure triage → root-cause → passing rerun.** One workflow, one join, one decision. Read-only, export-based, no gateway required.

**Product behavior:**
1. **Ingest AI usage** — customer gateway, provider billing APIs (OpenAI/Anthropic/Azure/Bedrock/Vertex), OpenTelemetry/SDK traces, or a local collector for on-prem inference. Capture model, agent/user, tokens, cost, session/run ID, project/block metadata.
2. **Ingest verification outcomes** — regression manager/log exports, failure DB, bug tracker (JIRA/Bugzilla), coverage DB, git/Perforce, engineer accept/reject state, rerun result.
3. **Correlate** into a domain workflow graph: *AI run → failure signature → proposed root cause → engineer accepted/rejected → bug/fix → rerun → resolution → coverage impact.*
4. **Produce decision metrics:** cost per accepted root cause, cost per resolved failure, cost per coverage gain, spend that produced **no** accepted outcome, and model/tool/agent/team comparisons.

**Example executive output:**
> *"The regression-triage assistant consumed $18,400 last quarter. It analyzed 312 failures, produced 96 engineer-accepted root causes, 74 of which led to passing reruns — $192 per accepted root cause, $249 per resolved failure. A second workflow consumed $7,800 and produced 4 accepted outcomes: pause it."*

### Value proposition (per audience)
- **Verification leader (first buyer):** for the first time, see **which AI tool/agent actually closes coverage and resolves failures**, and cut the ones that spin — in their own language.
- **Finance / management:** a defensible **cost-per-verified-outcome** number to justify renew / expand / cancel decisions.
The engineering leader must trust the outcome metric before finance trusts the ROI number — so we sell to engineering first.

### Why it's not "just a dashboard"
A dashboard is a mirror — it shows the problem and you still fix it yourself; that's how "AI cost" startups die (Datadog bolts a mirror on for free). The product must **observe → act → learn**:
- **Kill spinning loops live** — agent on its 50th retry of the same failing seed with zero new coverage → cut it off mid-flight, not report it tomorrow. In DV, waste is almost always an agent looping, and only the layer in the path can see and stop it.
- **Block duplicate work** — agent about to generate a test for already-closed coverage → don't run it.
- **Route by value** — boilerplate testbench → cheap model; hard triage → frontier model. Enforced, not suggested.
- **Gate value-blind agents** — an agent that consistently burns tokens with no coverage payoff gets capped until a human approves.

### Technology (how it's actually an AI company, not a report generator)
Two planes at two speeds — **you never put a slow LLM in the live token path:**
- **Data plane (the hands):** the deterministic gateway every agent call flows through. Microsecond metering, tagging, and enforcement of decisions the brain already made.
- **Intelligence plane (the brain):** LLM-as-judge + classifiers + loop detector + the **Value Bank** — runs near-real-time and in batch, slow is OK.

**Control loop — Sense → Judge → Decide → Act → Learn:**
- **Judge** = a measured half (did coverage move? did the bug DB change? — a SQL join on agent-run-ID + time, *not* AI) stitched to an **AI half** (LLM-as-judge scores the fuzzy part: "40 assertions written — substantive or trivial restatements?"). AI only does what measurement can't.
- **The Value Bank (the moat)** = a learned store of `(agent, action-type, context) → tokens spent vs outcome produced`. Over time it *knows*: "Vendor Agent X on testbench-gen closes coverage ~70% on the cheap model — no frontier needed"; "this shape (rising tokens, flat coverage) is a spin — 90% produces nothing." The compounding asset no competitor can copy.

**One-sentence architecture:** *AI does the judging and learning slowly, off to the side, and bakes it into policies; the gateway executes those policies instantly on the live token stream.*

### Vision (the expansion path, stated as direction not MVP)
Report (DV regression triage) → the **DV control plane** (route/gate/kill across every verification agent) → **all of verification** (assertions, stimulus, RTL drafting, coverage closure) → **the economic measurement layer for AI in complex engineering** (physical AI, aerospace) — the outcome layer is vertical-specific; the cost layer is reused. Present multi-vertical as horizon, never as the initial build.

**What we are explicitly NOT building:** a verification agent, an RTL/testbench generator, a model, a regression-selection engine (Synopsys VSO.ai owns that), an EDA-license optimizer, or a general cloud-FinOps tool. Scope is **AI token spend only** — compute/licenses are a separate, largely-solved utilization problem.

**Still to nail down:** which single design partner's export formats we build the first connectors against; the minimum data needed to compute a *credible* cost-per-accepted-outcome (what's the smallest honest join?).

---

## Section 5 — Customer Discovery, Validation, and Traction

### Traction framing (pre-seed, honest and confident)
We lead with **founder-market fit + a category inflection we can time**, and a **structured validation program we're executing** — not vanity metrics. The credible pre-seed claim is *"we know exactly which 12 questions decide whether this is real, we're inside the industry that has the answers, and our network gives us a direct path to read-only design partners."*

### Customer discovery plan (Phase 1: 15–20 interviews)
Interview verification directors, methodology leads, verification-infrastructure leads, and AI-enablement leaders — weighted to **small/mid fabless, IP vendors, and design-service firms** (less internal tooling, faster pilots). Never ask "would you use this?" Ask:
1. Which AI tools/agents are used in verification today? 2. Who pays? 3. Can usage be attributed by user/project/workflow? 4. Current monthly/annual spend? 5. How is renewal justified? 6. What's shown to management? 7. Can an AI run be linked to a regression/failure/bug/accepted result? 8. Where does that data live? 9. Customer-owned, vendor-owned, or on-prem model? 10. What decision would better unit economics change? 11. Who owns the budget? 12. Would you share sanitized exports for a pilot?

### Validation (Phase 2: one read-only design partner)
Do **not** start by replacing the gateway. Accept exports (AI usage, regression/failure logs, bug tracker, accept/reject state, rerun status) and hand back a static report: spend by workflow, cost per accepted root cause, cost per resolved failure, no-outcome spend, model/tool comparison, plus explicit **confidence / missing-data warnings**. This validates demand *and* seeds the dataset.

### Pilot success criterion (the only signal that counts)
Not "interesting idea." It's: **"We are deciding whether to renew/expand this AI tool, and your report would materially change that decision."** A design partner who reallocates or kills something based on our number = product-market pull.

### Kill criteria (state them — it builds credibility)
Reconsider if: no team has material AI spend; nobody owns the budget; teams can't access the usage data; outcomes can't be joined reliably; existing EDA/vendor reporting is deemed sufficient; or nobody will share sanitized pilot data.

**Still to nail down:** the target list of first ~10 named accounts and warm intros (founder network); whether an anchor design partner will commit to a read-only pilot; a signed data-handling/NDA template so pilots can move fast.

---

## Section 6 — Why Now and Market Timing

Four forces converge — and the DV-specific one is the sharpest.

1. **Enterprise AI moved from experiment to production spend.** Enterprise generative-AI spending hit **$37B in 2025, up from $11.5B in 2024 (3.2×)** — AI applications are now ~6% of the entire software market, the fastest growth in software history (Menlo Ventures). The economic buyer exists: **98% of FinOps teams now manage AI spend** (FinOps Foundation 2026).
2. **Agentic workloads make spend volatile and value-blind.** Up to **30× token variance on the same task**, with accuracy peaking at intermediate cost — so the category can't be priced away by cheaper tokens. The industry has already reframed around **cost per successful task**, which nobody can yet compute per workflow.
3. **Traditional FinOps can't see output value.** It was built for steady, rightsize-able cloud (cost per VM), not per-call volatility and un-measurable output quality. Measuring *value*, not just cost, needs a new data model — a report, not a lever.
4. **The DV-specific inflection (our timing edge):** the EDA majors *just* shipped agentic verification in 2026 — **Cadence ChipStack AI Super Agent** (pushed to Level-5 autonomy, running on NVIDIA Nemotron, with 40× faster RTL validation claims), **Synopsys AgentEngineer/VSO.ai**, **Siemens Fuse EDA / Questa One**. DV agent spend is inflecting *this year*. There's a ~12–24 month window before that spend is big enough that someone measures it. We ride the exact inflection with insider timing.

**Why not premature:** verification is ~70% of chip project effort, it's where AI-writable work + machine-observable outcomes (pass/coverage) overlap best, and the spend curve just turned up. **Why not too late:** no neutral, vertical outcome layer exists yet — the incumbents are racing to *sell* the agents, not to *meter* them.

**Still to nail down:** one concrete, quotable data point on how fast DV agent spend is actually growing at a real team (interview output feeds this).

---

## Section 8 — Competition, Differentiation, Positioning, and Defensibility

### The map (four converging fronts + the incumbents)
- **Horizontal AI ROI / cost-to-outcome:** **Harness** (AI DLC Insights + Cloud & AI Cost Management, May 2026 beta; cost per resolved ticket/workflow; $240M Series E at $5.5B) — validates the thesis and owns *software*. **Pay-i** (GenAI ROI pure-play, $4.9M seed, surfaces "failure spend") — closest to the original screenshot idea. **Atlassian + DX** (~$1B) — owns software-engineering measurement.
- **FinOps / cost allocation:** CloudZero, Finout, Ramp, PointFive, Vantage — own generic cost-to-unit joins; need the customer to define the metric.
- **Gateway / observability (commoditizing infra):** LiteLLM, Portkey, Cloudflare AI Gateway, Helicone, Langfuse, Datadog.
- **EDA incumbents:** Cadence, Synopsys, Siemens — own the simulators *and* the coverage/regression data.

### What's already commoditized (don't claim as differentiation)
Proxy/gateway, multi-provider access, key management, token counting, cost-by-model, team budgets, rate limits, spend alerts, caching, basic routing, LLM tracing, "cost per PR" dashboards, and LLM-as-judge *by itself*. Assume all of these are table stakes.

### What's still open (our position)
A **prebuilt, trusted, domain-specific outcome model** that understands how verification work actually progresses — *failure signature → triage → accepted root cause → fix → rerun → coverage/sign-off* — without the customer designing it from scratch. Horizontals can add a "Cadence" logo to a connector menu; they can't cheaply add the semantics.

### Differentiation vs each threat (attack the architecture, not the quality)
| Competitor class | Structural ceiling — why they *can't* just do this |
|---|---|
| Horizontal ROI (Harness, Pay-i, DX) | Built for software proxies (PRs/tickets); no concept of coverage closure or regression health. A connector ≠ a domain outcome model. |
| FinOps (CloudZero, Finout, Ramp) | Join cost to a unit the *customer* must define; no prebuilt verification ontology; finance-first, not trusted by DV engineers. |
| Gateways/observability | Infrastructure with no interpretation; they meter, they don't judge value. We can sit on top of them. |
| EDA incumbents (Cadence/Synopsys/Siemens) | **Conflicted meter** — they profit from more agent usage and license-hours; they'll measure only their *own* agents. Our counter is **neutrality across internal + all vendor agents**. |
| Internal build / spreadsheets | Lagging, generic, one-off; can't generate cross-customer benchmarks; no compounding data. |

### Defensibility — the moat compounds, difficulty is only the entry ticket
Causation-difficulty buys ~1–2 years of lead; we must *spend* it building durable moats:
1. **Data moat (strongest):** cross-customer `(AI spend → verified outcome)` pairs → benchmarks no single customer can generate. More customers → better Value Bank → more valuable to all; a new entrant starts at zero.
2. **Integration / outcome-ontology moat:** reusable connectors across regression DBs, coverage tools, bug trackers (standards like UCIS help) = real work + switching cost. (Datadog's true moat is 500 integrations, not the charts.)
3. **System-of-record lock-in:** once finance closes the books on our numbers, we're infrastructure, not a dashboard.
4. **Control-plane position:** once agent traffic routes/gates through us, we're in the critical path.

**Why this is a company, not a feature:** a feature reports cost per PR. A company owns the neutral, cross-vendor, cross-customer economic dataset for verified silicon and the control plane that acts on it — the trap is treating "it's hard" as the moat and getting lazy; the hard part is the entry ticket, the data + integrations are the durable moat.

**Incumbent risk (name it honestly):** an EDA vendor could ship native cost-to-outcome for its own agents; a horizontal could add EDA connectors. Both are real. Our answer is speed into the neutral position + the compounding dataset before either bothers — and the fact that a conflicted vendor's meter is not trusted by the buyer.

**Still to nail down:** confirm no stealth startup already owns "vertical AI ROI for chip verification" (periodic competitive sweep); pressure-test whether one anchor customer's data alone produces a benchmark worth paying for.

---

## Section 10 (input) — Technical & Product Risks (Usman owns these; Gurinder consolidates)

| Risk | Why it matters | Our mitigation / test |
|---|---|---|
| **Token spend not yet material in DV** | If it's a rounding error, there's no budget-level pain. | Interview questions 1–4; kill-criterion. Land where agentic DV is already live. |
| **EDA-vendor telemetry is closed** | If Cadence/Synopsys own the model account, we may not see raw tokens. | Support multi-mode ingestion (provider billing APIs, OTel/SDK, local collectors); target customer-owned & internal agents first. |
| **Horizontals add a connector** | Harness/CloudZero/Datadog could bolt on an EDA logo. | Depth of the outcome model + neutrality + dataset, not a logo in a menu. |
| **EDA vendors build it natively** | They own workflow context. | Conflicted meter (they profit from usage); we're neutral across internal + all vendors. |
| **Attribution ≠ causation** | An accepted root cause after AI involvement doesn't prove AI caused it. | Label metrics precisely: attributed / assisted / accepted / correlated; claim incremental impact only with a baseline. Honest correlation still beats today's zero. |
| **Outcome data too noisy to join** | Many runs/seeds touch coverage at once. | Time-windowing + per-agent-run isolation; ship confidence scores, not false precision. Validate the noise floor with real regression data. |
| **Market narrow / slow / secure** | Fewer buyers than software, long procurement, high security sensitivity. | Land-and-expand within large orgs; read-only pilots to lower the security bar. |
| **Buyer prefers internal tooling** | Big chip cos can build analytics. | Target mid-market first; win on neutral cross-vendor benchmarks they can't self-generate. |
| **Token prices fall** | Thesis needs volume/complexity to outrun price. | 30× variance + agentic growth + volume already outpace unit-price declines. |
| **Founder employment / IP (first-order)** | Both founders are at AMD. | **No AMD code, logs, architectures, confidential metrics, or employer-resourced work.** Independent legal review of employment/IP/outside-activity terms before building. Build only on public knowledge + design-partner data under NDA. |

---

## Common founder questions (both must answer identically — Usman's angle)

- **What does the company do?** Connects AI spend to verified verification outcomes so chip teams know which AI tools produce verified silicon and what each result costs.
- **What problem?** Chip teams are deploying AI across verification but can't tell which spend creates accepted outcomes — so they can't rationally renew, expand, or cut.
- **Initial customer & wedge?** VP/Director of Verification at small/mid fabless, IP, and design-service firms; wedge = read-only cost-per-accepted-outcome report for regression-triage.
- **Why now?** Enterprise AI in production ($37B, 3.2×), agentic spend is volatile/value-blind (30× variance), and agentic verification just shipped from every EDA major in 2026.
- **Why us?** Two AMD verification engineers — we know the outcome that matters and where it lives; we see the frontier a horizontal founder can't.
- **Biggest risk?** That DV AI spend isn't yet big enough to be a budget-level pain — which is exactly what our validation program tests first.
- **What we're raising / use of funds?** *(Gurinder owns the number.)* Keep the answer: fund the validation program + first connectors + one anchor design partner to the "materially changes a renewal decision" signal.

---

## Appendix A — Verified facts & figures (with sources)

- Enterprise GenAI spend **$37B in 2025**, up from **$11.5B in 2024 (3.2×)**; AI apps ≈ **6% of software market**, fastest growth in software history. — Menlo Ventures, *2025 State of Generative AI in the Enterprise*.
- **98%** of FinOps teams now manage AI spend; AI cost management is the top skill needed. — FinOps Foundation, *State of FinOps 2026*.
- Agentic coding: up to **30× token variance** on the same task; accuracy **peaks at intermediate cost, degrades at the highest**; **"cost per successful task is the true metric, not token price."** — Bai et al., arXiv 2604.22750; Forbes (Jul 13, 2026).
- **Harness:** AI DLC Insights + Cloud & AI Cost Management (May 2026 beta), cost per resolved ticket/workflow/customer; **$240M Series E at $5.5B**.
- **Pay-i:** GenAI ROI pure-play, **$4.9M seed**, surfaces "failure spend."
- **EDA agentic race (2026):** Cadence **ChipStack AI Super Agent** (Level-5 autonomy, NVIDIA Nemotron, ~40× faster RTL validation, up to 10× productivity claims); Synopsys **AgentEngineer / VSO.ai**; Siemens **Fuse EDA / Questa One**.
- **Verification ≈ 70% of chip project effort** — long-standing industry figure (Wilson Research); order-of-magnitude, verify before quoting a precise %.
- **N49P:** Fund IV first close **$25M USD** toward **$70M USD** target; first checks **~$500K–$1.5M** across ~27–30 companies. — BetaKit.

> Caveat: vendor pages describe intended capabilities, not independently verified customer results. Funding/product facts reflect public info as of July 2026.

## Appendix B — Open validation items (Usman's to-do)
1. One sanitized firsthand anecdote of a value-blind agent run (no AMD IP).
2. A credible current DV AI-spend figure from a representative team.
3. First ~10 named target accounts + warm intros.
4. One anchor read-only design partner committed; NDA/data-handling template ready.
5. Smallest honest join that yields a credible cost-per-accepted-outcome.
6. Competitive sweep: confirm no stealth "vertical AI ROI for chip verification" player.
7. Independent legal review of AMD employment/IP obligations before any build.
