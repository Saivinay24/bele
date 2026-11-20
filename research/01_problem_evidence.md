# 01. The problem in data

## What Problem Statement 6.1 says

- Farmers sell at local mandi rates without knowing better nearby prices, losing Rs 5,000 to 20,000 per cycle.
- 20 to 30% post-harvest losses come from poor storage and timing.
- Most sell to the local commission agent or trader, often the same person who advanced inputs on credit, at whatever price is quoted that day.
- Farmers stay tied to a trader through debt and absorb the spoilage when they cannot store or move produce in time.

## The commission-agent credit tie

| Fact | Source |
|---|---|
| More than 50% of farm credit comes from informal sources; the most common (modal) interest rate for small and marginal farmers is 36% a year (NSSO 70th round, 2012-13) | [RBI study](https://www.rbi.org.in/Scripts/PublicationsView.aspx?id=18781) |
| Commission agents charge 24 to 36%, compared with about 12.5 to 12.8% from a warehouse-receipt lender and about 11 to 12% from banks (company-sourced) | [TechCrunch](https://techcrunch.com/?p=3079406) |
| Over 50% of agricultural households were in debt in 2019; average outstanding loan Rs 74,121 (NSO SAS 77th round) | [DT Next via PressReader](https://www.pressreader.com/india/dt-next/20210911/282046215218449) |
| In Punjab, 44% of farmers deal with the same arhtiya for more than one generation, partly because of the debt cycle (PAU 2011) | [ThePrint](https://theprint.in/india/easy-money-cycle-of-debt-why-punjabs-farmers-cant-get-out-of-the-clutches-of-arhatiyas/584102) |
| PAU study (Singh and Dhaliwal 2010): high interest creating a debt trap, malpractice in weighing and pricing | [Governance Now](https://www.governancenow.com/views/think-tanks/arhtiyas-no-good-punjab-agriculture-study) |
| Interlocked credit and marketing is documented in the agricultural economics literature | [Chahal, AgEcon Search](https://ageconsearch.umn.edu/record/204359/files/09-sschahal.pdf) |
| Commission of 2 to 3% on grain sales in Punjab (charged to the buyer); fruit and vegetable mandis in the south commonly deduct about 10% from the farmer (field claim, to be verified at Kolar APMC) | [Scroll](https://scroll.in/article/828159/scroll_in) |

## Reading the evidence

The cost of the debt to the farmer has two layers:

1. **Explicit interest** of 24 to 36% on input advances.
2. **A hidden price discount.** The farmer is obliged to sell through the lender at the lender's quote, weighment and deductions.

The second layer is the root cause the problem statement points at ("often the same person who advanced inputs"), and no public dataset measures it per lot. A price app does not fix it: a farmer who owes the trader cannot take a better price elsewhere even when he sees one.

**Design consequence:** Bele must settle the debt as part of the sale, not around it. Every lot also produces a data point, the trader's opening quote against the best competing bid, which measures the hidden discount for the first time.

## Crop split we respect

- **Tomato** spoils in days and cannot be pledged against a warehouse receipt. For tomato, the problem is routing, timing and bidding.
- **Onion, potato and grains** can be stored in registered warehouses. For these crops, store-and-borrow is possible.
