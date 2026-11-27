# Pricing-Structure---Hardware
It is used to calculate selling prices for items that are not entered in the system.

## Files

| File | What it contains |
|------|------------------|
| `Pricing Structure - Hardware 06-2026 with siegenia discounts.xlsx` | The pricing workbook (see sheets below). |
| `SP-Calculator-June-2026.html` | Standalone calculator. Download it and double-click to open it in any browser. |

### Sheets in the workbook

- **SP Calculator June-2026**: current calculator (row 8, with helper columns E, G and I) and the input factors table (freight, exchange rates, surcharges, margins, Siegenia discounts by material group).
- **EUR Supplier / CAD Supplier / USD Supplier**: worked examples per supplier currency.
- **SP Calculator Mar-2025, Oct-2023, Mar-2023, Aug-2022, Jan-2022, Apr-2021**: earlier versions, kept for reference.

## How the selling price is calculated (June-2026)

```
price - disc             = Purchase Price × (1 − Siegenia Discount)
price-discount+dutis     = price - disc × (1 + Surcharge %)
price after disc+fright  = price - disc × Freight %
Landed Cost (CAD)        = (price-discount+dutis + price after disc+fright) × Exchange Rate
Fabricator               = Landed Cost ÷ (1 − Profit Margin %)
Non Fabricator           = Fabricator × 1.25
End Customer             = Fabricator × 1.50
```

Surcharge (MTZ, Duties, Sima) and freight are both charged on the net purchase price (after Siegenia discount); the surcharge is not charged on freight. This matches the updated Excel sheet (row 8, columns E, G, I, K). In the online calculator the three helper fields are hidden and calculated in the background.

Selling price below box quantity: add a 20% upcharge.

## Input factors (June-2026)

**Freight %**

| Freight | % |
|---|---|
| EUR Consolidated Container | 10% |
| EUR Consolidated Container – Stadur Panels | 20% |
| EUR Consolidated Container – Foam Pads | 30% |
| EUR Reinforcement Container | 15% |
| EUR Airfreight | 12% |
| EUR Airfreight Jigs (Siegenia) | 17% |
| EUR Airfreight Wemaro (split cost with Wemaro) | 15% |
| EUR Airfreight (Tedee) | 10% |
| EUR Airfreight (CES) | 10% |
| US Supplier | 15% |
| CA Supplier | min 5% |

**Exchange rate**: EUR 1.60, USD 1.40. For dummy items, use the current exchange rate. Any other rate requires management approval.

**Surcharge (MTZ, Duties, Sima)**

| Supplier | % |
|---|---|
| CES | 6.94% |
| Siegenia + KFV | 3.5% |
| OnLevel | 3.4% |
| PHI | 3% |
| Spax | 1.8% |
| Stadur | 7% |
| OnLevel | 8% |
| Wemaro | to be checked |
| Gebhardt (tariffs) | 50% |

**Profit margin**

| Product group | Margin |
|---|---|
| General min margin | 40% |
| Reinforcements | 40% |
| Fasteners | 45% |
| Moulded parts (PHI) | 48% |
| CES cylinder (re-keying kits and knobs are different) | 45% |
| Tedee | 40% |
| Other | 40–65%, check with Management |

**Siegenia discount**: looked up by Siegenia material group (MG) in the June-2026 sheet, rows 14–78.

## Calculator (`SP-Calculator-June-2026.html`)

**Download:** right-click https://github.com/Doofchris/Pricing-Structure---Hardware/raw/main/SP-Calculator-June-2026.html and choose "Save link as…", then double-click the file to open it in any browser. Everything (logo, calculation) is built into the file; only the fonts need internet.

**Online version** (private link, ask the owner for access): https://claude.ai/artifact/SekFMpokdyJR2iDDDRGzYP

How it works:

- One row like the Excel sheet: Purchase Price, Siegenia MG, Siegenia Discount, Surcharge, Freight %, Exchange Rate, Landed Cost, Profit Margin %, then the Fabricator, Non Fabricator and End Customer selling prices in CAD.
- Enter the purchase price; choose Siegenia MG, Surcharge, Freight, Exchange Rate and Margin from the dropdowns. Surcharge, Freight and Margin also have "none" and a "Custom" option.
- Exchange rate is fixed to 1.60 EUR or 1.40 USD. Choosing "Other rate…" shows "Management approval required" and keeps the current rate.
- The hidden helper steps from the sheet (price − disc, price-discount+dutis, price after disc+fright) are calculated in the background.
- Each selling price has a Copy button (copies the number only).
- The calculator always opens with everything at 0.00 / "none" / 1.60 EUR. The Reset button returns to that view.

## Change log

| Date | Change |
|------|--------|
| 2026-06 | Workbook updated with June-2026 calculator and Siegenia discounts. |
| 2026-11 | README added with formula, input factors and calculator description. |
| 2026-11 | Calculator added (online and as `SP-Calculator-June-2026.html`): one row like the sheet, dropdowns, fixed exchange rates (other rates need management approval), Copy buttons and Reset. |
| 2026-11 | Workbook replaced with the updated version (helper columns E, G, I); surcharge is charged on the net purchase price only, not on freight. |
| 2026-11 | Calculator design based on fentro.com: Fentro Hardware Systems logo at the top left, grey Fentro arrow in the background, dark grey header row with Fabricator (green), Non Fabricator (blue) and End Customer (red). |
