# BHIV CANDIDATE INTAKE — TASK 1

## FOUNDATION — MASTERDB + InsightFlow

**Candidate:** Shivam Verma
**Pack:** BHIV-SHIVAM-T1 v1.0
**Task:** Task 1 — Foundation — MASTERDB + InsightFlow
**Classification:** SYNTHETIC TRAINING DATA ONLY

---

## 1. Task Overview

The objective of this task was to build practical beginner-level competence in dataset profiling, quality validation, schema and version discipline, registration concepts, lineage, retrieval, measurement and operational thinking using synthetic data.

No production MASTERDB or InsightFlow access was used during this task.

All analysis and outputs were performed using the supplied synthetic training dataset and source register.

---

## 2. Access and Data Boundary

The following boundaries were maintained throughout the task:

* Only supplied synthetic training data was used.
* No private BHIV data was accessed.
* No production MASTERDB access was performed.
* No production InsightFlow access was performed.
* No internal credentials or private endpoints were used.
* Original CSV files were preserved without modification.
* Registration outputs were clearly marked as mock/proposed.
* No canonical production dataset ID or approval was claimed.
* No production lifecycle state was claimed.

**Classification: SYNTHETIC TRAINING DATA ONLY**

---

## 3. Dataset Profiling

The supplied synthetic dataset contains:

| Measure                  | Result |
| ------------------------ | -----: |
| Records                  |     20 |
| Columns                  |     10 |
| Source IDs               |      6 |
| Districts                |      7 |
| Asset types              |      5 |
| Units                    |      2 |
| Status values            |      3 |
| Schema versions          |      2 |
| Unique record IDs        |     20 |
| Missing values           |      2 |
| Duplicate complete rows  |      0 |
| Unique source references |     18 |

Important observed data-quality cases included:

* Comma decimal value `7,1`
* Negative count `-12`
* Repeated source reference `SRC-C:007`
* Missing quantity
* Missing source reference
* Extreme value `99999`
* Malformed timestamp `not-a-date`

---

## 4. Quality Validation

Thirteen records had no exception identified under the defined rules.

Seven records were identified for exception handling:

### REVIEW

* R006 — quantity `7,1` requires interpretation/normalization policy.
* R009 — repeated source reference `SRC-C:007`.
* R014 — extreme count `99999` requires review because no hard maximum was defined.

### REJECT

* R008 — negative count `-12`.
* R010 — missing quantity.
* R011 — missing source reference.
* R020 — malformed timestamp `not-a-date`.

### Quality Reconciliation

Total records:

`20`

Records with exceptions:

`7`

Records with no identified exception:

`13`

Therefore:

`7 + 13 = 20`

The quality summary reconciles successfully.

---

## 5. Registration Proposal

A mock registration packet was prepared for:

**Proposed dataset name:**
Task1 Synthetic Environmental Observation Dataset

The packet documents:

* Purpose
* Source register
* Owner role
* Permission basis
* Classification
* Fields and types
* Refresh information
* Quality state
* Limitations
* Proposed lifecycle

The registration packet is explicitly a **MOCK / NOT REGISTERED** artifact.

No production registration or canonical dataset identity was claimed.

---

## 6. Schema and Version Discipline

A baseline schema version `1.0` was documented.

A compatible change was proposed for version `1.1`:

* Add optional `observation_note` field.

A breaking change was also demonstrated for version `2.0`:

* Rename `quantity` to `measurement_value`.

The compatible change should have low consumer impact because existing consumers can ignore the optional field.

The breaking change requires consumers depending on `quantity` to be updated.

Historical records should not be silently overwritten during a breaking schema transformation.

---

## 7. Lifecycle

The proposed lifecycle is:

**DRAFT → VALIDATION → APPROVED → ACTIVE → DEPRECATED → RETIRED**

This is a proposed conceptual lifecycle only and does not represent a production approval state.

---

## 8. Lineage and Retrieval

A simulated retrieval was performed for record R012 using schema version `1.1`.

Trace:

**Synthetic Dataset → Schema 1.1 → R012 → SRC-D → SRC-D:012 → Training coastal restoration log**

The retrieval example recorded the requested version, record ID, source ID, source reference and transformation.

The simulated transformation was only record/version selection. No values were modified.

---

## 9. Measurement

Three deterministic measures were calculated.

### Record Count

Formula:

`Number of records`

Result:

**20**

### Flagged Rate

Formula:

`(Review + Invalid records) / Total records × 100`

Calculation:

`(5 + 1) / 20 × 100`

Result:

**30%**

### Source-Reference Completeness

Formula:

`Records with non-missing source_ref / Total records × 100`

Calculation:

`19 / 20 × 100`

Result:

**95%**

The 95% completeness result does not prove that source references are unique or valid. For example, `SRC-C:007` occurs more than once.

---

## 10. Failure Simulations

Three bounded failure cases were simulated.

### Missing Version

Requested version:

`2.0`

Available versions:

`1.0, 1.1`

Expected result:

`VERSION_NOT_FOUND`

The system should not silently substitute another version.

### Stale Input

An hourly-refresh source was considered without current freshness evidence.

Expected result:

`FRESHNESS_UNCONFIRMED`

Currentness should not be claimed without evidence.

### Unauthorized Request

A request for private/production BHIV data was considered.

Expected result:

`UNAUTHORIZED`

The request should be rejected without attempting access.

---

## 11. RL Learning Cycle

The task used a simple observe → hypothesize → act → measure → feedback → adjust → verify cycle.

Example:

**Observe:** A malformed timestamp was present.

**Hypothesis:** The value may fail timestamp validation.

**Bounded Action:** Inspect the affected row and apply the defined validation rule without modifying the original data.

**Measure:** Check the validation result.

**Feedback:** Confirm whether the observed value matches the rule outcome.

**Adjustment:** Record the exception instead of silently repairing the value.

**Verification:** Recheck the original record and test result.

This approach was used as RL literacy and feedback discipline, not as autonomous model training or deployment.

---

## 12. AI-Assisted Work

AI assistance was used for bounded tasks such as:

* Structuring documentation.
* Suggesting quality-rule wording.
* Explaining concepts.
* Reviewing edge cases.
* Preparing test and documentation templates.

Consequential results were independently checked using:

* Deterministic calculations.
* Direct row inspection.
* Reconciliation checks.
* Independent metric recomputation.

No confidential or private BHIV information was provided to AI tools.

---

## 13. Main Learning Outcomes

The main lessons from Task 1 were:

1. Preserve original data before analysis.
2. Profile data before making quality decisions.
3. Separate facts from assumptions and questions.
4. Never silently repair questionable records.
5. Make quality decisions traceable to explicit rules.
6. Keep schema versions explicit.
7. Treat registration as governed metadata rather than just a filename.
8. Record lineage from output back to source.
9. Define metrics with formulas and populations.
10. Do not claim production access or approval without evidence.

---

## 14. Final Reproducibility Check

The major calculations can be reproduced from the supplied synthetic dataset.

Key results:

**20 records**

**30% flagged**

**95% source-reference completeness**

Original source files were preserved.

The quality exception count reconciles:

`7 exceptions + 13 records without identified exceptions = 20 records`

---

## 15. Final Status

**Task 1 completed using synthetic training data.**

The work demonstrates practical understanding of:

* Dataset profiling
* Data-quality rules
* Exception handling
* Mock registration
* Schema/version discipline
* Lifecycle concepts
* Lineage
* Retrieval simulation
* Metrics
* Failure handling
* RL feedback discipline
* AI-assisted verification
* Documentation and reproducibility

**SYNTHETIC TRAINING DATA ONLY**

No production access, production approval, or live MASTERDB/InsightFlow operation is claimed.
