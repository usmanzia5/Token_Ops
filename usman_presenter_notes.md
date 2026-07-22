# Usman Presenter Notes

Repo-only prep notes for the current 16-slide GitHub Pages deck. Do not add these to
`index.html`. Gurinder-owned slides are intentionally omitted: 09 Customer, 10 Market,
12 Business Model and GTM, 14 Team, and 15 The Ask.

---

## Slide 01: Title

- Open with the one-liner slowly: "WaferZero is the economic layer for AI in chip verification."
- If asked what it is: "It is TokenOps for chip verification. We turn AI spend into cost per verified engineering outcome."
- Name the category: AI unit economics is becoming real, and we are the vertical wedge where horizontal tools do not understand the outcome data.
- Keep this slide short. Do not explain the whole company yet.

## Slide 02: Problem

- Do not pitch "AI costs too much." That sounds like a cost-cutting feature.
- The real problem is decision failure: teams cannot tell value from waste, so they cannot safely cut or confidently invest.
- The 30x variance point proves the problem is structural. More tokens do not automatically mean better work.
- Strong line: "They are forced to choose between throttling productivity and bleeding money, so most just freeze."

## Slide 03: The Insight

- This is the most important early slide. It explains why the wedge is semiconductor verification, not generic AI spend.
- In software, outcome data is easy to reach: PRs, tickets, deploys. In silicon, the outcome data lives inside regression systems, coverage tools, and bug trackers.
- Founder-market fit line: "We know the outcome that matters is not a merged PR. It is coverage closing, bugs found, failures resolved, and passing reruns."
- Strong line: "In software, this is a race. In silicon, it is open ground."

## Slide 04: Solution

- Define the product plainly: WaferZero reads AI usage and verification outcomes, then reports what each verified result actually cost.
- Emphasize read-only first: exports in, ROI report out. No gateway swap on day one.
- The hard part is the verification outcome model, not the dashboard.
- Strong line: "We turn 'we spent X on AI' into 'this agent produced 96 accepted root causes at $192 each, and this other one should be paused.'"

## Slide 05: Product Map

- Explain the diagram left to right: AI spend and outcome data go into WaferZero, and WaferZero produces ROI decisions.
- The inputs are internal agents, vendor EDA copilots, and verification data like failures, accepted root causes, reruns, and coverage movement.
- The middle block is the join: meter tokens, link outcomes, score value.
- The output is not just visibility. It is budget moves, vendor decisions, internal benchmarks, and later agent controls.

## Slide 06: What Teams Do

- This slide answers the "so what?" objection.
- WaferZero lets teams reallocate AI budget, renew or cancel tools, benchmark workflows, and identify no-outcome spend.
- Say clearly that this is not a "good to know" dashboard. The product creates operating decisions.
- Strong line: "The outcome is budget confidence: know what to expand, what to pause, and what actually moves verification forward."

## Slide 07: How It Works

- Keep the sequence clear: ROI report first, control plane later.
- Phase 1 is a data product: ingest exports, join AI runs to DV outcomes, report cost per accepted outcome.
- Phase 2 earns the right to sit in the path: routing, capping, and stopping wasteful agent behavior.
- Explain the LLM simply: most value is measured directly; the LLM only grades fuzzy artifacts like whether an explanation or generated assertion is substantive.
- Strong line: "The brain judges and learns off to the side. The hands enforce fast rules only after teams trust the signal."

## Slide 08: Why Now

- The timing edge is that enterprise AI budgets are now real, and agentic verification is arriving now.
- Emphasize that token price falling does not kill the thesis because autonomy, volume, context, and retries can grow faster than unit cost falls.
- The strongest DV-specific point: every major EDA vendor is pushing agentic verification, but no neutral layer is measuring ROI across all agents.
- Strong line: "The spend is inflecting before anyone is measuring whether it produced verified silicon."

## Slide 11: Competition and Moat

- Attack structure, not quality. The point is not that competitors are bad; it is that they see the wrong data.
- Horizontals see software proxies like PRs and tickets. FinOps tools see cost allocation. Gateways meter calls. EDA vendors are conflicted and vendor-specific.
- Our edge is a neutral verification outcome model: coverage, regression health, accepted root causes, passing reruns.
- Strong line: "A connector is not a domain model. A cost dashboard is not proof of verified value."

## Slide 13: Traction, Validation and Roadmap

- Be honest: the company is not pretending to have fake traction. The proof is founder-market fit plus a concrete validation plan.
- The only signal that matters is whether a DV leader would change a renewal, expansion, or budget decision based on our report.
- Mention kill criteria confidently: if teams do not have material AI spend, cannot access the data, or do not act on the metric, the wedge is not real yet.
- Strong line: "Each step turns a belief into evidence: interviews prove pain, the read-only report proves value, and the control plane proves the moat."

## Appendix A1: Risks

- Use this only if asked or if the room pushes on risk.
- The biggest risk is not technical magic. It is whether DV AI spend is already large enough and whether teams will act on the metric.
- For attribution, avoid overclaiming causation. Use labels like attributed, assisted, accepted, correlated, and confidence score.
- For IP and data, keep the answer strict: no employer IP, no raw customer design data used for shared learning, and deployment can be customer-controlled.
- Strong line: "We would rather show you the failure modes than pretend they do not exist."
