# Vendor Payment Fraud and Bribery Risk Review

A self-directed case study in forensic investigations and compliance.

**Note on scope:** Meridian Components Pvt Ltd, its people, vendors and every transaction are fictional. This is a learning exercise built to practise method. It is not professional forensic experience and not legal advice.

## Objective
Work through the first phase of an investigation from allegation to recommendations: scope the review, test a year of vendor payments, document evidence, assess anti-bribery exposure under the FCPA, UK Bribery Act and Indian law, and report findings with appropriate caution.

## Scenario
An anonymous tip alleges that a Procurement Manager approved payments to vendors connected to him and arranged "facilitation" payments for customs clearance. The review covers 48 vendor payments totalling INR 1,16,85,178 for calendar year 2025.

## Repository contents
| File | Description |
|---|---|
| `01_investigation_report.md` | Findings, timeline, conclusions and recommendations |
| `02_transaction_analysis_workpaper.md` | Test design, results and limitations |
| `03_fcpa_ukba_gap_review.md` | Anti-bribery control gap assessment |
| `04_evidence_log.md` | Evidence register and handling notes |
| `data/Meridian_Transaction_Analysis.xlsx` | Formula-driven workbook (flags, vendor summary, test summary) |
| `data/vendor_payments_fictional.csv` | Source payment data |
| `data/vendor_master_fictional.csv` | Source vendor master |

## Method in brief
Five rule-based tests (near-threshold amounts, round numbers, weekend payments, duplicate invoices, offshore accounts) run through formulas in Excel, followed by vendor-level review of onboarding records. Test parameters sit on the Assumptions sheet and can be changed.

## Limitations
The dataset is small, clean and built to contain red flags. Real engagements involve interviews, email and document review, forensic data collection, legal privilege considerations and much noisier data. Findings here are indicators for follow-up, not conclusions of wrongdoing.
