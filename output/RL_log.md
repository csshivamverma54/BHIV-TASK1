# BHIV CANDIDATE INTAKE — TASK 1

## RL / Feedback Log

**Candidate:** Shivam Verma
**Pack:** BHIV-SHIVAM-T1 v1.0
**Classification:** SYNTHETIC TRAINING DATA ONLY

---

# Day 1 — Observation and Profiling

## RL Cycle

| Step                 | Entry                                                                                                                                                  |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Observe**          | I observed the supplied synthetic dataset structure, source register, fields, values and several potential data-quality issues.                        |
| **Hypothesis**       | Systematic profiling would help identify missing values, distinct values, duplicates and unusual records before applying quality rules.                |
| **Bounded Action**   | I inspected the headers and sample rows, calculated basic profile statistics and reviewed individual records without modifying the original CSV files. |
| **Expected Result**  | The dataset structure and major data-quality observations should become clear while preserving the original data.                                      |
| **Actual Result**    | The dataset was identified as containing 20 records and 10 columns, with missing values and several values requiring further quality review.           |
| **Feedback / Check** | Profile results were checked against individual rows and the original input files.                                                                     |
| **Mismatch**         | Some observations could not yet be classified as accepted or rejected because explicit quality rules had not been defined at that stage.               |
| **Adjustment**       | I separated observed facts from questions and deferred final quality decisions until deterministic rules were defined.                                 |
| **Verification**     | The profiling results and observations were documented without modifying the original dataset.                                                         |

## Day 1 Learning

I learned that profiling should happen before making quality decisions. An unusual value should first be observed and documented rather than immediately corrected or rejected.

---

# Day 2 — Quality, Registration and Schema

## RL Cycle

| Step                 | Entry                                                                                                                                                                          |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Observe**          | The profiling results showed several quality cases including a negative count, missing values, a malformed timestamp, a repeated source reference and a comma decimal.         |
| **Hypothesis**       | Explicit deterministic rules would make quality decisions more consistent and traceable.                                                                                       |
| **Bounded Action**   | I created quality rules, applied them to the records, documented exceptions and then prepared mock registration and schema/version artifacts.                                  |
| **Expected Result**  | Each quality decision should have a clear rule, affected record and reason. Registration and schema artifacts should also clearly distinguish proposals from production facts. |
| **Actual Result**    | Seven records were identified with quality exceptions: three for review and four for rejection. The quality results reconciled to all 20 records.                              |
| **Feedback / Check** | I checked the exception decisions against the defined rules and reviewed the registration and schema artifacts for unsupported production claims.                              |
| **Mismatch**         | The extreme value `99999` did not have a defined hard maximum, so it could not be rejected solely on that basis.                                                               |
| **Adjustment**       | R014 was classified as REVIEW instead of REJECT, with the need for a future policy decision documented.                                                                        |
| **Verification**     | The quality reconciliation was checked as `7 + 13 = 20`, and schema/version changes were documented as compatible or breaking.                                                 |

## Day 2 Learning

I learned that a quality decision should come from a defined rule rather than intuition. When a rule does not exist, the correct approach is to record the ambiguity instead of inventing a threshold.

---

# Day 3 — Lineage, Metrics and Final Verification

## RL Cycle

| Step                 | Entry                                                                                                                                              |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Observe**          | The completed work needed final verification for lineage, metrics, failure handling, reproducibility and documentation consistency.                |
| **Hypothesis**       | Independent recalculation and final review should identify any remaining mismatch or misleading interpretation before handover.                    |
| **Bounded Action**   | I traced R012 through its schema and source reference, calculated the main metrics, simulated failure cases and reviewed the final portfolio.      |
| **Expected Result**  | The final results should be reproducible and clearly explain what each metric proves and what it does not prove.                                   |
| **Actual Result**    | The main results were 20 records, 30% flagged rate and 95% source-reference completeness.                                                          |
| **Feedback / Check** | The calculations were independently checked against the supplied dataset and the quality results were reconciled.                                  |
| **Mismatch**         | The 95% source-reference completeness metric could potentially be misunderstood as proving reference validity or uniqueness.                       |
| **Adjustment**       | I added a caveat explaining that completeness only measures whether the field is populated and does not prove uniqueness or validity.              |
| **Verification**     | The final metrics, lineage example, failure simulations and quality reconciliation were checked before preparing the final portfolio and handover. |

## Day 3 Learning

I learned that final verification is not only about checking whether a number is mathematically correct. It is also important to verify that the meaning and limitations of the number are communicated correctly.

---

# Overall RL Learning

The three-day task followed the overall cycle:

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

The main learning from the task was that good data work requires both **correct calculations and traceable reasoning**.

I learned to:

* Observe data before making assumptions.
* Define rules before making quality decisions.
* Record exceptions instead of silently changing data.
* Separate facts from unresolved questions.
* Keep schema versions explicit.
* Trace outputs back to their source.
* Verify metrics independently.
* Add caveats when a metric has limitations.
* Treat AI assistance as bounded support and independently verify consequential results.
* Avoid making unsupported claims about production systems.

