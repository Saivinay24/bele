# Bele: research and design notes

**Every buyer bids. The farmer keeps the difference.**

Tech4Bharat 2026 | Theme 6: Agriculture and Food Processing | Problem Statement 6.1: Farmers sell at the wrong time, place and price | Agentic AI | Team davinciable

Bele is a voice-first AI agent that sells a small farmer's harvest for him. Buyers send sealed bids on his lot, ranked by what he actually takes home. The trader who advanced his inputs gets one chance to match the best bid, and is paid first either way. For storable crops, a forecast that states its uncertainty and a warehouse loan let the farmer wait for a better price. Nothing happens without the farmer's yes.

This repository holds the research behind the idea. It is idea-stage work: every number below is either sourced or labelled as a target, never a result.

## Contents

| File | What it covers |
|---|---|
| [research/01_problem_evidence.md](research/01_problem_evidence.md) | The problem in data: losses, the commission-agent credit tie, interest rates, why debt decides the sale |
| [research/02_existing_systems.md](research/02_existing_systems.md) | e-NAM, Agmarknet, Bharat-VISTAAR, ONDC, aggregators, warehouse receipt finance, and the gap each leaves |
| [research/03_price_forecasting.md](research/03_price_forecasting.md) | State of the art in Indian mandi price forecasting, achievable accuracy, and why we forecast ranges |
| [design/04_match_or_release.md](design/04_match_or_release.md) | The core mechanism: sealed bids, the trader's right to match, debt settled first, store and borrow |
| [design/05_agent_architecture.md](design/05_agent_architecture.md) | Agent loop, India conditions, tech stack, measurement plan, business model, boundaries, build plan |
| [deck/Bele_Tech4Bharat_2026.pdf](deck/Bele_Tech4Bharat_2026.pdf) | Idea submission deck |

## How the design maps to Problem Statement 6.1

| What the problem statement says | Where Bele answers it |
|---|---|
| Farmers sell at local mandi rates without knowing better nearby prices | Sealed bids from many nearby buyers, ranked by take-home |
| Often the same person who advanced inputs on credit | Match or release: the trader can match, and his dues are cleared first |
| 20 to 30% post-harvest loss from poor storage and timing | Sell now or store: price range plus warehouse receipt loan for storable crops |
| Any useful outcome depends on coordinating many parties | One agent and one case file across farmer, buyers, trader, transporter, warehouse and lender |
| The farmer makes the call; every forecast states its uncertainty | Voice approval before every sale, loan or payment; calibrated forecast ranges with measured coverage |
| Would he wait if he could borrow against stored produce? | First loan payout clears the trader, so waiting becomes affordable |

## Honesty rules we follow

- Every figure carries a source. Company-sourced or secondary figures are marked as such.
- Accuracy and impact numbers are targets until the prototype measures them on public data.
- Escrow, e-NAM and warehouse loan integrations are simulated in the prototype and labelled.
