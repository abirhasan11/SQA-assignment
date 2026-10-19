# CSE 442 – Software Quality Assurance | Assignment 1

**Industry Requirements, ID-Personalized Test Engineering & Defect Triage**
Domain: SkyBound Airways Flight Booking System (v3.0)

| | |
|---|---|
| Course | CSE 442 – Software Quality Assurance (3 Credits) |
| Student ID | 0242310005101162 |
| Personalization | Last digit is **2 (EVEN)** → detailed test cases for **REQ-02** and **REQ-04** |
| Scope | Lessons 11–14 |
| Total Marks | 13 |

## Repository Contents

```
.
├── 0242310005101162_CSE442_Assignment1.xlsx   # Submission workbook (4 tabs)
├── CSE442_Assignment_1_FlightBooking.pdf      # Assignment brief
└── README.md
```

## Workbook Structure

| Tab | Task | Marks | What it contains |
|---|---|---|---|
| `RTM` | Task 1 | 3 | REQ-01 to REQ-04 extracted from the client transcript, mapped to test scenarios, test level and execution status |
| `TestCases` | Task 2 | 4 | 8 high-level test scenarios (TS-01 to TS-08) and 3 detailed test cases (Positive, Negative, Boundary) for REQ-02 and REQ-04 |
| `DefectReports` | Task 3 | 4 | Bug A (High Severity / Low Priority) and Bug B (Low Severity / High Priority) |
| `DefectLifecycle` | Task 4 | 2 | Re-test decision (close and log a linked bug), state transition and developer Jira comment |

## Requirements Summary

| ID | Requirement |
|---|---|
| REQ-01 | Block checkout when the passport expires within 6 months of the flight, or the profile has an active security hold |
| REQ-02 | Hold a selected seat for 10 minutes; issue a `CONFIRMED` ticket on successful payment; release the seat if the hold expires |
| REQ-03 | Place passengers on a Standby List when economy hits 200/200; cap the list at 15; reject the 16th with "Flight & Standby Full" |
| REQ-04 | Admin cancel/override requires a secondary confirmation pop-up with a mandatory reason |

## Detailed Test Cases (EVEN rule)

| ID | Type | Requirement | Summary |
|---|---|---|---|
| TC-01 | Positive | REQ-02 | Seat held, payment on time, ticket becomes `CONFIRMED` |
| TC-02 | Boundary | REQ-02 | Payment just before vs. just after the 10-minute cutoff |
| TC-03 | Negative | REQ-04 | Override blocked when the reason field is empty |

## Defects

| ID | Severity | Priority | Summary |
|---|---|---|---|
| BUG-2210 | High | Low | Database deadlock with a special character in the middle name at midnight UTC rollover |
| BUG-2211 | Low | High | Brand name misspelled as "SkyBoud Airways" in the search-page header |

## Defect Lifecycle Outcome

`BUG-2210`: `RESOLVED - FIXED` → re-test → `CLOSED (VERIFIED)`
`BUG-2214` (new, linked to BUG-2210): `OPEN / TO DO` – confirmation email not dispatched
