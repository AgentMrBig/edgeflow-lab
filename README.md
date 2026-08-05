# EdgeFlow Lab

Live results dashboard for the USD/JPY MTF signal engine — a walk-forward test bench where the **master detector is held constant** and only the *execution* (entry timing, exit rule, cost) is varied, so we can see exactly what carries the edge.

**Live:** https://agentmrbig.github.io/edgeflow-lab/

## How it updates
1. `node campaign.js data.json <1m-history.csv...>` — runs the standard trial matrix against `detect.js`, writes `data.json`.
2. Commit + push `data.json`. The dashboard (`index.html`) reads it live.

The headline finding so far: **entry timing is the edge** — the identical 2-year signal set goes from PF 0.65 (entered late) → 0.81 (break entry) → 1.92 (entered on time, with spread). The job is recovering that on-time entry via the 1-minute executor.

*Nothing here is financial advice; research tooling only.*
