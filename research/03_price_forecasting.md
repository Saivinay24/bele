# 03. Mandi price forecasting: state of the art and our approach

## Published results

| Work | Data and crops | Result |
|---|---|---|
| Wang and Zhang, [arXiv 2601.06371](https://arxiv.org/abs/2601.06371) (Jan 2026) | USDA monthly prices 1997-2025, 17 methods | Zero-shot time-series foundation models beat statistical, ML and deep models trained from scratch. Time-MoE was best, then Chronos, then Chronos-2. The authors warn of possible pretraining leakage |
| GRU on Agmarknet data (Kolar-area literature) | Onion, tomato | MAPE 14.59% for onion, 10.58% for tomato (single paper; forecast horizon not confirmed) |
| Patil, [arXiv 2604.01792](https://arxiv.org/html/2604.01792) (2026) | Kolar tomato, weekly, 2010-2024 | SARIMA to LSTM capture average seasonality, but errors exceed 20% in volatile spells; seasonal patterns drift year to year |
| Manogna et al., [Scientific Reports 2025](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12215695/) | 23 commodities including tomato, onion, potato; daily Agmarknet | Comparison of statistical, ML and deep learning models by MAE and MAPE |
| [Scientific Reports, July 2024](https://doaj.org/article/3c3f82bed9ae413d868a2b0d8830f1de) | Tomato, onion, potato with weather | Weather inputs improve forecasts |
| FedChronos, [arXiv 2608.01290](https://arxiv.org/pdf/2608.01290) | Agmarknet potato and onion | Federated fine-tuning of Chronos for commodity prices |

## What is honestly achievable

- Horizon of 7 to 14 days on daily or weekly modal prices.
- About 10 to 15% error in normal weeks for tomato and onion.
- More than 20% error in shock weeks, which are exactly the weeks that matter most to a farmer.

A single-number forecast is therefore weak. The defensible product is a **calibrated range**.

## Our approach

1. Chronos-2 quantile forecasts on Agmarknet history for each market and crop.
2. Split conformal calibration on a rolling backtest, so the ranges are corrected using past errors.
3. Report **empirical coverage** as the headline number. Target: an 80% range should contain the real price about 80% of the time on held-out past seasons.
4. Baselines shown alongside: seasonal naive and last-week persistence. If we cannot beat them, we say so.

This meets the problem statement's rule that "every forecast states its uncertainty" with a measured number instead of a claim.

## Decision rule built on the range, not the point

- **Store** only if the low end of the range for (future net price minus storage, interest and shrinkage) still beats today's best firm bid.
- **Sell now** if it does not.
- **Split the lot** (sell part, store part) when the range straddles today's best bid.
