# BRL Exchange-Rate Misalignment (BEER + VECM)

**Status:** planned

## Question
Is the real BRL over/undervalued relative to its fundamentals-implied equilibrium, and how fast does it adjust?

## Premises
- Equilibrium real exchange rate (RER) is a function of fundamentals: terms of trade, net foreign assets, productivity differential, interest differential.
- Variables are I(1) and share a long-run relation.

## Method
1. Download series (BCB SGS, IBGE, FRED) with `src/01_download.py`.
2. Unit-root tests (ADF, KPSS), lag selection (AIC/SC).
3. Johansen trace/max-eigenvalue; identify cointegrating vector.
4. VECM; misalignment = RER − fitted equilibrium; speed of adjustment (α).
5. Diagnostics: residual autocorrelation, normality, stability; robustness to lag and deterministic terms.

## Deliverables
`outputs/misalignment.png`, `outputs/johansen_table.csv`, short write-up of limitations (structural breaks, small sample).

## Stack
Python (statsmodels `coint_johansen`, `VECM`) or R (`urca`, `vars`).
