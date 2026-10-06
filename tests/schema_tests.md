# Schema Tests

**Classification:** SYNTHETIC TRAINING DATA ONLY
**Dataset:** Task1 Synthetic Environmental Observation Dataset

## 1. Purpose

These tests verify schema conformance and schema/version discipline using the supplied synthetic dataset.

The tests do not modify the original dataset.

## 2. Schema Conformance Checks

| Test ID | Check                     | Expected Result        | Actual Result                   | Status           |
| ------- | ------------------------- | ---------------------- | ------------------------------- | ---------------- |
| ST01    | `record_id` present       | All records have ID    | 20/20 present                   | PASS             |
| ST02    | `record_id` unique        | No duplicate IDs       | 20 unique IDs                   | PASS             |
| ST03    | `source_id` present       | All records populated  | 20/20 present                   | PASS             |
| ST04    | `observed_at` valid       | Valid timestamp        | R020 invalid                    | FAIL / VIOLATION |
| ST05    | `district` present        | All records populated  | 20/20 present                   | PASS             |
| ST06    | `asset_type` present      | All records populated  | 20/20 present                   | PASS             |
| ST07    | `quantity` present        | All records populated  | R010 missing                    | FAIL / VIOLATION |
| ST08    | `quantity` numeric        | Numeric representation | R006 requires clarification     | FAIL / REVIEW    |
| ST09    | `count` quantity positive | Value > 0              | R008 = -12                      | FAIL / VIOLATION |
| ST10    | `pH` within range         | 0–14                   | Supplied pH values within range | PASS             |
| ST11    | `unit` allowed            | `count` or `pH`        | Supplied values conform         | PASS             |
| ST12    | `status` allowed          | valid/review/invalid   | All values conform              | PASS             |
| ST13    | `schema_version` present  | All records populated  | 20/20 present                   | PASS             |
| ST14    | `source_ref` present      | All records populated  | R011 missing                    | FAIL / VIOLATION |

## 3. Detailed Schema Violations

### ST04 — Invalid Timestamp

**Record:** R020
**Field:** `observed_at`
**Expected:** Valid ISO-8601 timestamp
**Actual:** `not-a-date`
**Disposition:** REJECT

Reason: The value cannot be interpreted as a valid timestamp.

---

### ST07 — Missing Required Quantity

**Record:** R010
**Field:** `quantity`
**Expected:** Required numeric value
**Actual:** Missing
**Disposition:** REJECT

Reason: `quantity` is required by the baseline schema.

---

### ST08 — Numeric Representation Review

**Record:** R006
**Field:** `quantity`
**Expected:** Numerically interpretable value
**Actual:** `7,1`
**Disposition:** REVIEW

Reason: The supplied value uses a comma decimal representation. The intended numeric interpretation requires clarification before any transformation.

No silent conversion was performed.

---

### ST09 — Negative Count

**Record:** R008
**Field:** `quantity`
**Expected:** Positive value for `unit=count`
**Actual:** `-12`
**Disposition:** REJECT

Reason: Negative count violates the defined count constraint.

---

### ST14 — Missing Source Reference

**Record:** R011
**Field:** `source_ref`
**Expected:** Required source reference
**Actual:** Missing
**Disposition:** REJECT

Reason: The record cannot provide a complete source-reference value.

---

### Repeated Source Reference

**Record:** R009
**Field:** `source_ref`
**Actual:** `SRC-C:007`
**Related Record:** R007
**Disposition:** REVIEW

Reason: The same source reference occurs more than once. The assignment does not define whether this is an allowed correction/revision pattern, so it is retained for review rather than silently removed.

---

### Extreme Value Review

**Record:** R014
**Field:** `quantity`
**Expected:** Numeric count
**Actual:** `99999`
**Disposition:** REVIEW

Reason: The value is unusually high compared with nearby records. No hard maximum count was defined in the supplied requirements, so this is not automatically rejected.

## 4. Schema Version Tests

| Test                                   | Expected | Result |
| -------------------------------------- | -------- | ------ |
| Baseline v1.0 documented               | Yes      | PASS   |
| Compatible v1.1 change documented      | Yes      | PASS   |
| Breaking v2.0 change documented        | Yes      | PASS   |
| Consumer impact explained              | Yes      | PASS   |
| Historical reconstruction explained    | Yes      | PASS   |
| Silent historical overwrite prohibited | Yes      | PASS   |

## 5. Final Test Summary

```text
Total records checked: 20

Schema/quality issues requiring attention:
R006
R008
R009
R010
R011
R014
R020

Original dataset modified: NO

Schema violations silently repaired: NO

Schema version tests: PASS

Schema conformance result: REVIEW REQUIRED
```

## 6. Conclusion

The supplied dataset contains records that do not fully conform to the proposed baseline schema.

The violations are explicitly recorded rather than silently corrected.

The original source data remains unchanged.

**SYNTHETIC TRAINING DATA ONLY**
