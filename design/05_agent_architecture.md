# 05. Agent architecture, measurement and business model

## The agent loop (against the Agentic AI bar)

| The problem statement expects | How Bele meets it |
|---|---|
| Plans over many steps toward the user's goal | Goal: best take-home for this lot. Plan: invite bids, rank, offer match, settle, store or ship, collect payment |
| Acts in external systems | Buyer invites, truck booking, warehouse booking, loan request (simulated where no open interface exists) |
| Keeps memory of the case | One case file per lot: crop, quantity, buyers, bids, dues, approvals, payments |
| Recovers when something fails | Buyer backs out or truck cancels: re-offer to the next bidder and re-book, without starting over |
| Seeks human approval before money, legal commitment or personal data | Voice yes from the farmer before every sale, loan or payment; Cafe operator co-signs loans |

## Built for the conditions the problem statements set

- Voice first: speak and listen in Kannada, including mixed speech, on WhatsApp voice notes or a phone call.
- Works on entry-level Android phones and patchy networks; WhatsApp is the main channel.
- JanAI Cafe path: the operator lists the lot and handles documents for farmers who want help.
- Explicit consent; buyers never see the farmer's debt or phone number; only what the sale needs is stored.

## Tech stack

- Python and FastAPI backend, Postgres.
- Lyzr AI agents for planning and case handling.
- Sarvam and AI4Bharat models for Kannada speech in and out.
- Chronos-2 forecasting on Agmarknet data, with conformal calibration.
- WhatsApp as the farmer channel; a simple operator console for JanAI Cafes.

## How we will measure it (targets, not results)

| What | How | Target |
|---|---|---|
| Farmer gain | Rs per quintal over the local mandi price, replayed on past Agmarknet seasons | Positive and reported per crop and market |
| Forecast honesty | Empirical coverage of the 80% range on held-out seasons | About 80% |
| Forecast accuracy | MAPE vs seasonal naive and persistence baselines; published reference 10.6% tomato, 14.6% onion | Beat both baselines |
| Speech | Word error rate on the public IndicVoices benchmark (Kannada) | Reported, not assumed |
| Safety | Sales, loans or payments without the farmer's approval | 0 |
| Recovery | Injected buyer and truck failures handled end to end | All recovered or escalated to the farmer |

## Business model

- Farmers pay nothing to sell.
- Buyers pay a small fee per lot won; traders, FPOs and processors get ready lots without travelling village to village.
- Warehouse lenders and banks pay per loan sourced; each lot comes with a clean sale and repayment record.
- JanAI Cafe operators earn per lot handled.

## Jobs

- A JanAI Cafe operator becomes the village's sales and settlement agent (paperwork, grade photos, warehouse receipts): a new local job in every taluk.
- Truck pooling coordinators for shared trips.

## Rollout

Start with storable crops in Karnataka (onion, potato, grain), then fast selling for tomato. The same engine scales to FPOs, dairy and any village seller.

## Boundaries

- The farmer makes the call on when and where to sell.
- Every forecast states its uncertainty.
- No crop advisory or general chatbot (existing services cover that).
- Escrow, e-NAM and warehouse loan integrations are simulated in the prototype and labelled.

## Prototype plan (23 Nov to 15 Dec 2026)

- **Week 1:** Kannada voice listing, buyer bids, take-home ranking.
- **Week 2:** Match or release, forecast ranges with measured coverage, approval gates.
- **Week 3:** Warehouse loan flow, shared trucks, field test with farmers, demo.
