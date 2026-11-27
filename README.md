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

## Online calculator

A web version of the June-2026 calculator is available (private link, ask the owner for access):
https://claude.ai/artifact/SekFMpokdyJR2iDDDRGzYP

It shows the calculation in one row like the sheet, with dropdowns for Siegenia MG, Freight, Exchange rate, Surcharge and Margin. Freight, Surcharge and Margin have a "Custom" option for values not in the list. The exchange rate is fixed to 1.60 EUR or 1.40 USD; choosing "Other rate…" shows "Management approval required" and keeps the current rate.

A standalone copy (`SP-Calculator-June-2026.html`, in this repository) can be opened in any browser by double-clicking it.

## Change log

| Date | Change |
|------|--------|
| 2026-06 | Workbook updated with June-2026 calculator and Siegenia discounts. |
| 2026-11 | README expanded with formula and input factors; online calculator added. |
| 2026-11 | Calculator: Purchase Price is a typed field; exchange rate fixed to EUR 1.60 / USD 1.40 (other rates need management approval). |
| 2026-11 | Calculator: removed the "below box quantity" option and the calculation breakdown panel (20% upcharge below box qty is applied manually). |
| 2026-11 | Calculator: tried an old-school green-on-black look, then returned to the previous spreadsheet look. |
| 2026-11 | Calculator: column order is now Purchase Price, Siegenia MG, Siegenia Discount, Freight %, Surcharge, Exchange Rate, Landed Cost, Profit Margin %, Fabricator, Non Fabricator, End Customer. |
| 2026-11 | Calculator: surcharge now charged on the net purchase price only (added to freight %), no longer on top of freight. |
| 2026-11 | Calculator rebuilt on the updated sheet: helper fields "price - disc", "price-discount+dutis" and "price after disc+fright" are hidden and used in the background. Column order now matches the sheet: Purchase Price, Siegenia MG, Siegenia Discount, Surcharge, Freight %, Exchange Rate, Landed Cost, Profit Margin %, Fabricator, Non Fabricator, End Customer. |
| 2026-11 | Workbook replaced with the updated version (helper columns for discount, duties and freight). Standalone calculator `SP-Calculator-June-2026.html` added to the repository. |
| 2026-11 | Calculator: removed the small info text under the fields (supplier currency, MG, freight/surcharge names, rate note, margin note). |
| 2026-11 | Calculator: Landed Cost and selling prices shown as "CAD 18.16" instead of "$18.16". |
| 2026-11 | Calculator: removed the "Selling Price / CAD" headers; Fabricator, Non Fabricator and End Customer are now the column headers in the same row as the other fields. |
| 2026-11 | Calculator: "Reset" button (and opening the calculator) sets Purchase Price to 0.00 and Siegenia MG, Surcharge, Freight and Margin to "none"; exchange rate stays at EUR 1.60. Added "none" option to Freight and Margin. |
| 2026-11 | Calculator: always starts with the Reset values when opened, reloaded or returned to (browser no longer restores old entries). |
| 2026-11 | Calculator: removed the sentence "For dummy items, use the current exchange rate." from the intro text. |
| 2026-11 | Calculator: text centered in every field (headers, entries and results). |
| 2026-11 | Calculator: new design based on fentro.com (Fentro green #5F9032, light greys, Montserrat and Inter fonts, green Reset button and tier headers). |
| 2026-11 | Calculator: Fentro Hardware Systems logo in the header and a large, faint green Fentro arrow in the background (both built into the file, no internet needed). |
| 2026-11 | Calculator: more contrast (darker text and borders, stronger entry-field shading, darker green prices, bolder headers, stronger background arrow). |
| 2026-11 | Calculator: bigger Fentro Hardware Systems logo, smaller headline. |
| 2026-11 | Calculator: logo reduced by 10%. |
| 2026-11 | Calculator: large, faint Fentro Hardware Systems logo in the background (replaces the green background arrow). |
| 2026-11 | Calculator: logo removed from the top; it now appears only in the background. |
| 2026-11 | Calculator: removed the empty white row under the fields; Copy buttons moved under each selling price. |
| 2026-11 | Calculator: header row changed to dark grey (#353535) with white text; price headers stay green. |
| 2026-11 | Calculator: whole header row dark grey (#353535); tier names in colour: Fabricator green, Non Fabricator blue, End Customer red. |
| 2026-11 | Calculator: all text in the value row (entries, Landed Cost, prices, Copy buttons) in black. |
| 2026-11 | Calculator: value row all one colour; fields you type in or choose from are dark grey with white text (hint now reads "Enter figures in dark fields only"). |
| 2026-11 | Calculator: dark entry boxes removed; whole value row is Fentro green, entry fields have white text, calculated values black. Hint now reads "Enter values only in the fields with white text". |
| 2026-11 | Calculator: value row back to the earlier light green; entry fields keep white text. |
| 2026-11 | Calculator: value row filled brighter (#F1F8EA); all text in that row very light grey (#E6E6E6). |
| 2026-11 | Calculator: text in the value row set to #D8DAD8 (same light grey as the background logo). |
| 2026-11 | Calculator: value row white with dark grey text; Fabricator, Non Fabricator and End Customer prices in green, blue and red like their headers. Hint now reads "Type the purchase price and choose the other values from the dropdowns". |
| 2026-11 | Calculator: Fentro Hardware Systems logo back at the top left with more space below it; intro sentence removed. Background logo stays. |
| 2026-11 | Calculator: large background logo replaced by the Fentro arrow alone, in grey. |
| 2026-11 | Calculator (just for fun): pressing Reset makes the page explode for about 2 seconds, then after 2 more seconds it rebuilds in the reset view. Skipped for users who turn off animations in their system settings. |
