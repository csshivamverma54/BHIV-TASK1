# BHIV CANDIDATE INTAKE — TASK 1

## FOUNDATION — MASTERDB + InsightFlow

**Candidate:** Shivam Verma
**Pack Version:** BHIV-SHIVAM-T1 v1.0
**Task:** Task 1 — Foundation — MASTERDB + InsightFlow
**Status:** Completed
**Working Period:** 04-10-2026 to 06-10-2026
**Classification:** **SYNTHETIC TRAINING DATA ONLY**

---

## 1. Purpose

This project demonstrates beginner-level practical understanding of:

* Dataset profiling
* Data-quality validation
* Exception handling
* Mock dataset registration
* Schema and version discipline
* Dataset lifecycle concepts
* Data lineage
* Retrieval simulation
* Operational metrics
* Failure handling
* RL-style feedback and verification
* AI-assisted reasoning
* Reproducibility and documentation

All work was completed using the supplied synthetic training data.

---

## 2. Access Boundary

The following boundaries were maintained throughout the task:

* Only synthetic training data was used.
* No private BHIV data was accessed.
* No production MASTERDB access was performed.
* No production InsightFlow access was performed.
* No internal credentials were used.
* No private/internal endpoints were accessed.
* Original source files were preserved without modification.
* No production dataset was registered.
* No canonical production dataset ID was claimed.
* No production approval was claimed.
* No production lifecycle state was claimed.

**SYNTHETIC TRAINING DATA ONLY**

---

## 3. Project File Structure

```text
shivam_task1/
│
├── README.md
│
├── input_original/
│   ├── task1_source_register.csv
│   └── task1_synthetic_dataset.csv
│
├── work/
│   ├── data_dictionary.md
│   ├── profile_table.md
│   └── facts_vs_questions.md
│
├── output/
│   ├── mini_glossary.md
│   ├── quality_rule_catalogue.md
│   ├── exception_register.md
│   ├── quality_summary.md
│   ├── mock_registration_packet.md
│   ├── unresolved_questions.md
│   ├── schema_v1.0.md
│   ├── schema_change_log.md
│   ├── lifecycle_sketch.md
│   ├── lineage_trace.md
│   ├── mock_retrieval_response.md
│   ├── metric_dictionary.md
│   ├── static_measurement_report.md
│   ├── final_portfolio.md
│   ├── RL_log.md
│   └── time_log.md
│
├── evidence/
│   ├── completeness_check.md
│   ├── failure_tests.md
│   └── self_review.md
│
└── tests/
    ├── recalculation.md
    ├── quality_tests.md
    ├── schema_tests.md
    └── metric_tests.md
```

---

## 4. Input Data

The `input_original/` folder contains the supplied original synthetic files.

### `task1_source_register.csv`

Contains source-level metadata including:

* Source ID
* Source name
* Owner role
* Method
* Permission
* Refresh frequency
* Limitations

### `task1_synthetic_dataset.csv`

Contains the synthetic observation records used for:

* Profiling
* Quality validation
* Schema analysis
* Lineage
* Retrieval simulation
* Metric calculation

The original files were preserved without modification.

---

## 5. Work Folder

The `work/` folder contains the data-understanding and profiling artifacts.

### `data_dictionary.md`

Documents the dataset fields, their meaning, expected types and relevant constraints.

### `profile_table.md`

Contains the dataset profiling results including counts, missing values, distinct values and observed categories.

### `facts_vs_questions.md`

Separates directly observed facts from questions or assumptions that require further clarification.

---

## 6. Output Folder

The `output/` folder contains the main analysis and documentation artifacts.

### Initial Understanding

* `mini_glossary.md` — key Task 1 terminology.

### Data Quality

* `quality_rule_catalogue.md` — deterministic data-quality rules.
* `exception_register.md` — row-level quality exceptions.
* `quality_summary.md` — overall quality results.

### Registration and Schema

* `mock_registration_packet.md` — proposed registration information.
* `unresolved_questions.md` — questions requiring clarification.
* `schema_v1.0.md` — baseline schema.
* `schema_change_log.md` — compatible and breaking schema changes.
* `lifecycle_sketch.md` — proposed dataset lifecycle.

### Lineage and Measurement

* `lineage_trace.md` — traceability example.
* `mock_retrieval_response.md` — simulated retrieval response.
* `metric_dictionary.md` — metric definitions and formulas.
* `static_measurement_report.md` — measurement results.

### Finalization

* `final_portfolio.md` — consolidated Task 1 portfolio.
* `RL_log.md` — RL-style learning and feedback log.
* `time_log.md` — focused working-time record.

---

## 7. Evidence Folder

The `evidence/` folder contains supporting verification and review artifacts.

### `completeness_check.md`

Documents the completeness check of the mock registration packet.

### `failure_tests.md`

Documents simulated failure scenarios including:

* Missing schema version
* Stale input
* Unauthorized request

### `self_review.md`

Contains the final review of the completed Task 1 work.

---

## 8. Tests Folder

The `tests/` folder contains reproducibility and validation checks.

### `recalculation.md`

Contains independent recalculation checks for profiling results.

### `quality_tests.md`

Contains validation checks for the quality rules and exception handling.

### `schema_tests.md`

Contains checks related to schema and version discipline.

### `metric_tests.md`

Contains independent checks of the calculated metrics and failure simulations.

---

## 9. Dataset Profile

The supplied synthetic dataset contains:

| Measure                  | Result |
| ------------------------ | -----: |
| Records                  |     20 |
| Columns                  |     10 |
| Unique record IDs        |     20 |
| Source IDs               |      6 |
| Districts                |      7 |
| Asset types              |      5 |
| Units                    |      2 |
| Status values            |      3 |
| Schema versions          |      2 |
| Missing values           |      2 |
| Duplicate complete rows  |      0 |
| Unique source references |     18 |

### Status Distribution

| Status  | Count |
| ------- | ----: |
| Valid   |    14 |
| Review  |     5 |
| Invalid |     1 |

---

## 10. Main Quality Findings

The following data-quality cases were identified:

* **R006** — quantity `7,1`
* **R008** — negative count `-12`
* **R009** — repeated source reference `SRC-C:007`
* **R010** — missing quantity
* **R011** — missing source reference
* **R014** — extreme value `99999`
* **R020** — malformed timestamp `not-a-date`

No values were silently changed in the original dataset.

### Quality Results

| Result                  |  Count |
| ----------------------- | -----: |
| REVIEW                  |      3 |
| REJECT                  |      4 |
| No exception identified |     13 |
| **Total**               | **20** |

Reconciliation:

```text
7 exception records + 13 records with no identified exception = 20 records
```

---

## 11. Mock Registration

A mock registration packet was prepared for:

**Task1 Synthetic Environmental Observation Dataset**

The packet documents:

* Purpose
* Proposed identity
* Source information
* Owner role
* Permission basis
* Classification
* Fields and types
* Refresh information
* Quality state
* Limitations
* Proposed lifecycle

The packet is explicitly marked:

**MOCK / NOT REGISTERED**

No production registration or approval was claimed.

---

## 12. Schema and Version Discipline

A baseline schema **v1.0** was documented.

### Compatible Change — v1.1

An optional field:

`observation_note`

was proposed.

This is considered compatible because existing consumers can continue using the original fields.

### Breaking Change — v2.0

The field:

`quantity`

was proposed to be renamed to:

`measurement_value`

This is considered breaking because consumers depending on `quantity` would require changes.

Historical data should not be silently overwritten during schema transformation.

---

## 13. Lifecycle

The proposed conceptual lifecycle is:

```text
DRAFT
   ↓
VALIDATION
   ↓
APPROVED
   ↓
ACTIVE
   ↓
DEPRECATED
   ↓
RETIRED
```

This is a conceptual proposal only and does not represent a production lifecycle state.

---

## 14. Lineage

A simulated retrieval was performed for record **R012**.

The trace is:

```text
Synthetic Dataset
      ↓
Schema Version 1.1
      ↓
Record R012
      ↓
Source SRC-D
      ↓
Source Reference SRC-D:012
      ↓
Training coastal restoration log
```

No value modifications were performed during the simulated retrieval.

---

## 15. Key Metrics

### Record Count

**Result: 20**

### Flagged Rate

```text
(Review + Invalid) / Total Records × 100

(5 + 1) / 20 × 100 = 30%
```

**Result: 30%**

### Source-Reference Completeness

```text
Records with non-missing source_ref / Total records × 100

19 / 20 × 100 = 95%
```

**Result: 95%**

### Metric Caveat

The 95% completeness value only indicates whether the source-reference field is populated.

It does not prove that the references are unique or valid.

---

## 16. Failure Simulations

Three failure cases were simulated.

### Missing Version

Requested version: `2.0`

Available versions: `1.0`, `1.1`

Expected result:

`VERSION_NOT_FOUND`

Another version should not be silently substituted.

### Stale Input

A source requiring hourly refresh was considered without current freshness evidence.

Expected result:

`FRESHNESS_UNCONFIRMED`

Currentness should not be claimed without evidence.

### Unauthorized Request

A request for private or production BHIV data was considered.

Expected result:

`UNAUTHORIZED`

The request should be rejected without attempting access.

---

## 17. RL / Feedback Learning

The task followed:

```text
Observe
   ↓
Hypothesize
   ↓
Bounded Action
   ↓
Measure
   ↓
Feedback
   ↓
Adjust
   ↓
Verify
```

The RL log documents observations, hypotheses, bounded actions, measurements, feedback, adjustments and verification across the three working days.

The activity represents RL literacy and feedback discipline rather than autonomous model training or deployment.

---

## 18. AI-Assisted Work

AI assistance was used for bounded activities including:

* Documentation structure
* Quality-rule wording
* Concept explanations
* Edge-case discussion
* Critique of proposed outputs
* Test and report organization

Important results were independently verified using:

* Deterministic calculations
* Row-level inspection
* Reconciliation
* Dataset review
* Independent metric calculations

No confidential or private BHIV information was provided to AI tools.

---

## 19. Time Log

The work was completed across **three focused working days**.

| Working Day | Date       | Start Time | End Time |    Focused Time |
| ----------- | ---------- | ---------- | -------- | --------------: |
| Day 1       | 04-10-2026 | 2:00 PM    | 3:45 PM  |     1 hr 45 min |
| Day 2       | 05-10-2026 | 3:15 PM    | 5:15 PM  |            2 hr |
| Day 3       | 06-10-2026 | 1:30 PM    | 3:30 PM  |            2 hr |
| **Total**   |            |            |          | **5 hr 45 min** |

### Day 1 — Setup and Profiling

* Task orientation
* Access boundaries
* Folder setup
* Original data preservation
* Dataset inspection
* Ecosystem understanding
* Initial profiling

### Day 2 — Quality, Registration and Schema

* Quality rules
* Exception handling
* Quality reconciliation
* Mock registration
* Schema/version discipline
* Lifecycle proposal

### Day 3 — Lineage, Metrics and Final Review

* Lineage
* Retrieval simulation
* Metric calculation
* Failure simulations
* Independent verification
* Final portfolio
* Self-review and handover

Detailed activity-level timing is available in:

`output/time_log.md`

---

## 20. Reproducibility

The main calculations can be reproduced using:

```text
input_original/task1_synthetic_dataset.csv
```

Key results:

```text
Total records = 20
Flagged rate = 30%
Source-reference completeness = 95%
Quality exceptions = 7
Records with no identified exception = 13
```

Quality reconciliation:

```text
7 + 13 = 20
```

The relevant validation and recalculation files are stored in the `tests/` folder.

---

## 21. Key Learning Outcomes

The main lessons from this three-day task were:

1. Preserve original data before analysis.
2. Profile data before making quality decisions.
3. Separate observed facts from assumptions.
4. Define quality rules explicitly.
5. Never silently repair questionable data.
6. Make quality decisions traceable.
7. Maintain schema and version discipline.
8. Record lineage from output back to source.
9. Define metrics with clear formulas and populations.
10. Verify AI-assisted results independently.
11. Do not claim production access or approval without evidence.
12. Use feedback to improve and verify the final work.

---

## 22. Final Status

**TASK 1 — FOUNDATION — MASTERDB + InsightFlow: COMPLETED**

**Working Period:** 04-10-2026 to 06-10-2026
**Total Focused Time:** 5 hours 45 minutes

The submission demonstrates practical understanding of:

* Dataset profiling
* Data quality
* Exception handling
* Mock registration
* Schema/versioning
* Lifecycle concepts
* Lineage
* Retrieval
* Metrics
* Failure handling
* RL-style feedback
* AI-assisted verification
* Reproducibility
* Documentation

**SYNTHETIC TRAINING DATA ONLY**

**No production MASTERDB or InsightFlow access, registration, approval, or live operation is claimed.**
