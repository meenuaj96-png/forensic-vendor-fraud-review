# Workpaper: Transaction Analysis

Source: `data/vendor_payments_fictional.csv` (48 payments, INR 1,16,85,178) | Workbook: `data/Meridian_Transaction_Analysis.xlsx` | Prepared by: Meenu A J

## Spend by vendor
| Vendor | Payments | Amount (INR) | Share |
|---|---|---|---|
| Sterling Marine Consultants LLC | 10 | 49,84,000 | 42.7% |
| Southern Steel Traders | 9 | 23,14,348 | 19.8% |
| Kaveri Packaging Pvt Ltd | 10 | 14,64,949 | 12.5% |
| Orion Clearance Associates | 5 | 14,50,000 | 12.4% |
| Coastal Freight Carriers | 6 | 6,85,659 | 5.9% |
| Brightline IT Services | 7 | 6,01,222 | 5.1% |
| Harbourview Events & Hospitality | 1 | 1,85,000 | 1.6% |

## Tests and results
Parameters (editable on the Assumptions sheet): approval limit INR 5,00,000; near-threshold band 2%; round-number divisor INR 50,000; home country IN.

| Test | Payments flagged | Amount (INR) | Comment |
|---|---|---|---|
| Near approval limit | 10 | 49,84,000 | All Sterling |
| Round numbers | 5 | 14,50,000 | All Orion |
| Weekend payments | 17 | 58,34,891 | 10 Sterling; 7 from established vendors, likely false positives |
| Duplicate invoice numbers | 2 | 6,24,900 | Overpayment is INR 3,12,450 (repeat only) |
| Offshore account | 10 | 49,84,000 | All Sterling (UAE) |

Ten payments carry two or more flags (3 each), all Sterling.

## Vendor onboarding check
| Vendor | Created | First payment | Days between |
|---|---|---|---|
| Sterling | 20 Dec 2024 | 18 Jan 2025 | 29 |
| Orion | 28 Dec 2024 | 10 Feb 2025 | 44 |
| Other vendors | 2017 to 2023 | 2025 | 900+ |

## Observations
- A single flag is often innocent. The weekend test alone would have pointed at four vendors. Clustering of several independent flags on one vendor with one approver is what justifies escalation.
- Threshold avoidance is only visible because the band is set by judgement (2%). A wider band would capture more normal payments, a narrower one could miss splitting.

## Limitations
Small clean dataset with built-in anomalies. In practice, data would need extraction, reconciliation to the general ledger, sampling decisions and false-positive handling.
