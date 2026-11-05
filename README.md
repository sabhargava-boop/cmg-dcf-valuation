# Chipotle (CMG) Discounted Cash Flow Valuation

A 5-year unlevered DCF of Chipotle Mexican Grill (NYSE: CMG), built in Excel with live formulas. Change any blue input cell and the whole model recalculates.

**File:** `CMG_DCF_Valuation.xlsx`

## Headline result (base case)

| Metric | Value |
| --- | --- |
| Enterprise value | $22.6B |
| Equity value | $23.5B |
| Implied value per share | $18.68 |
| Share price used (Nov 4, 2026) | $34.75 |
| Implied upside / (downside) | (46.2%) |
| Terminal value as % of EV | 77.2% |
| Implied terminal EV/EBITDA | 8.5x |
| Market EV / 2025A EBITDA | 18.7x |

Sensitivity range (WACC 8%-10%, terminal growth 2%-4%): **$14.54 - $26.92 per share**.

**Takeaway:** On conservative assumptions, the market price implies faster growth and stronger margin recovery than this base case. The gap between the 8.5x terminal multiple and the 18.7x multiple the market pays is the main thing to explain.

## How the model works

1. **Forecast free cash flow, 2026E-2030E.** Revenue x EBIT margin = EBIT; minus taxes = NOPAT; plus D&A; minus capex; minus change in working capital.
2. **Discount** each year's cash flow to today at the WACC.
3. **Terminal value** captures everything after 2030: FCF(2030) x (1 + g) / (WACC - g), then discounted back.
4. **Enterprise value** = PV of cash flows + PV of terminal value. **Equity value** = EV + cash - debt. Divide by diluted shares for value per share.
5. **Sensitivity table** recalculates value per share across WACC and terminal growth.

## Key assumptions

| Input | Value | Reasoning |
| --- | --- | --- |
| Revenue growth | 8.5% in 2026E, fading to 5.0% by 2030E | Management guides 350-370 new restaurants in 2026 plus low-single-digit comps; Q3 2026 revenue grew 9.6% |
| EBIT margin | 15.0% in 2026E, recovering to 16.0% | FY2025 was 16.2%, Q3 2026 fell to 13.7% on beef/chicken inflation, tariffs and wages |
| Tax rate | 25% | Management guides 24%-26% |
| D&A / Capex | 3.0% / 5.6% of revenue | FY2025 actuals (D&A $361.4M, capex $666.3M on $11,925.6M revenue) |
| WACC | 9.0% | My assumption for a large-cap consumer stock with no funded debt |
| Terminal growth | 3.0% | My assumption, near long-run nominal growth |
| Cash / debt | $902.0M / none | Balance sheet at Sep 30, 2026 |
| Diluted shares | ~1,259M | Q3 2026 net income $339.9M / $0.27 diluted EPS |

**Leases:** Chipotle leases nearly all of its restaurants. Rent is already deducted in EBIT, so lease liabilities are excluded from debt to avoid double counting.

## Limitations

- Year-end discounting (no mid-year convention), and 2026E is treated as a full first year even though the valuation date is in November.
- D&A and capex are held at constant percentages of revenue; capex at the terminal stage is probably higher than a mature business needs, which pushes the value down.
- Stock-based compensation is not adjusted for.
- No comparable-company or precedent-transaction cross-check yet.
- Some inputs come from third-party data pages and press releases. Verify against the SEC filings before relying on any figure.

## Sources

- Chipotle Q3 2026 earnings release and 10-Q (Oct 28, 2026)
- Chipotle Q4 and full-year 2025 earnings release (Feb 3, 2026)
- FY2025 D&A, capex and revenue from public financial data pages; share price from equibles.com

## Disclaimer

This is a student project for learning valuation. It is not investment advice.
