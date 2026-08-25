# AI Strategy One-Pager - Juno Automated Prioritization

## 1. Problem & Workflow

the bad decision it prevents is building a feature that only a vocal minority wants, mistaken for broad demand.

## 2. Target Metrics

The percentage of shipped roadmap items that are rolled back, deprioritized, or abandoned within 90 days of launch due to adoption or impact falling materially short of the projection made at the greenlight decision.

Formula: (# of features abandoned/rolled back within 90 days of launch ÷ total # of features shipped in the period) × 100

Target: Reduce from baseline by 50%+ within two quarters of Juno-informed prioritization going live (e.g., 35% → 15–17%).

## 3. Autonomy Level

_(missing)_

## 4. Data & Model Approach

Autonomy Level: Copilot

Juno surfaces evidence-weighted recommendations (aggregated signal, forecasted impact, drop-rate risk) at the moment of a prioritization or spec decision — but the PM makes and owns the final call.

Level rejected: Agent

I would not let Juno autonomously reprioritize the roadmap, greenlight features, or trigger launches on its own. Two reasons: first, accountability — if a shipped feature fails, leadership needs a human decision-owner to explain the call, not "the AI decided." An autonomous agent making that decision quietly reintroduces the exact problem Juno exists to prevent — a decision nobody can fully trace or defend, just automated instead of anecdotal. Second, prioritization is inherently political and contextual (stakeholder relationships, timing, competitive pressure) in ways that aren't fully captured in the data Juno ingests; full autonomy would optimize for what's measurable and miss what isn't, producing confidently wrong calls at machine speed.



## 5. Risks & Mitigations

make it into a two sentence

Risk & Guardrail: Juno's aggregation could quietly launder bias as authority — over-weighting the loudest, most-instrumented segment while burying a quiet but high-revenue account's dissent, leading a PM to kill a feature that account depends on and only discovering the churn months later, when it's irreversible. The guardrail: every recommendation must display its evidence composition and revenue-weighted dissent (e.g., "$X ARR disagrees"), and any decision touching an account above a revenue threshold requires mandatory human review of that dissent before the PM can act.

## 6. V1 Scope

No autonomous roadmap changes or ticket creation. Juno doesn't write to Jira/Linear, reprioritize backlogs, or auto-generate specs — it only surfaces the recommendation in-context. Write access is a trust and accountability line V1 hasn't earned yet.
No cross-team or cross-product-line synthesis. Juno scopes to a single product line's signal in V1 — it won't pull in or weight feedback across other teams' customers/segments. Cross-line aggregation multiplies the bias risk from the guardrail above before there's evidence the weighting model even works on one line.
