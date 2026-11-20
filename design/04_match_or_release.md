# 04. The core mechanism: match or release

## The idea in one line

Buyers compete for the farmer's lot. The trader who advanced his inputs can match the best bid. Either way, the trader is paid first, and the farmer is free to take the market price.

## Flow

1. **Declare the lot.** The farmer states crop, quantity and readiness by voice, with an optional grade photo. With his consent, the agent records his outstanding advance to trader T (amount, rate, date).
2. **Sealed bid round.** The agent invites 5 to 15 buyers: other mandi traders, FPOs, bulk and institutional buyers (simulated and labelled in the prototype).
3. **Rank by take-home.** Bids are ranked on net realisation at the farm gate: price minus pooled transport, commission, weighment norms, payment-delay cost and spoilage during transit.
4. **Match or release.** Trader T gets a last look and can match the best firm bid within a set window (for example, 2 hours).
   - **Match:** the farmer sells to T at the market-best price. T deducts his dues transparently on a voice and written settlement slip. The relationship is kept; the hidden discount is gone.
   - **Release:** the winning buyer pays into a three-way settlement. T's principal plus the agreed interest is paid off the top directly to T, and the balance goes to the farmer. T is made whole in cash, the same day.
5. **Store and borrow (storable crops only).** If the forecast range says waiting pays, the agent books a registered warehouse, opens an electronic warehouse receipt, and requests a pledge loan. The **first loan payout clears T's dues**. The crop is sold later and the loan is repaid from the proceeds, tracked by the agent.
6. **Approval gates.** Every step that moves money or creates a commitment waits for the farmer's voice yes. Loans also need a JanAI Cafe operator co-sign.

## Why this design

- **It removes the real blocker.** A farmer who owes the trader cannot accept a better price elsewhere. Settling the debt inside the sale removes that lock.
- **The trader stays in the game.** He never loses his money, only his monopoly. He is a bidder like everyone else.
- **Lenders get a clean takeout.** A pledge loan whose first use is to clear an informal 24 to 36% debt with a known, tracked sale is a refinancing that banks understand.
- **It measures the invisible cost.** Every lot records the gap between T's opening quote and the best competing bid. Aggregated, this is a per-lot measure of the interlocked-credit discount, which no public dataset has today.
- **It is a known market design pattern** (right of first refusal combined with a sealed-bid auction), applied to a new setting.

## Risks and how we handle them

| Risk | Handling |
|---|---|
| Buyers stop bidding if they expect T to match every time | Publish the match rate; T pays a small winner's fee to the platform when he matches |
| Buyer backs out or truck cancels | The agent re-offers to the next-ranked bidder and re-books transport, logged in the case file |
| Price drops below the farmer's reserve | The agent asks the farmer before doing anything; storage or a later round are offered |
| Disputes over weight or grade | Grade photo and weighment recorded at pickup; settlement slip read back by voice |
| Escrow and loans are not open systems today | Simulated and clearly labelled in the prototype |
