#  MOCK MASTERDB Registration Packet

**Candidate:** Shivam Verma
**Task:** BHIV Candidate Intake — Task 1
**Pack:** BHIV-SHIVAM-T1 v1.0
**Classification:** SYNTHETIC TRAINING DATA ONLY
**Registration Status:** MOCK / TRAINING EXERCISE ONLY

> This document is a mock registration proposal created for Task 1 training. No live MASTERDB registration, canonical ID creation, approval, or production change was performed.

---

## 1. Purpose

The proposed dataset is intended for synthetic training and demonstration of dataset profiling, deterministic quality validation, source traceability, schema/version awareness and measurement.

It is not intended to represent production BHIV data.

---

## 2. Proposed Dataset Identity

**Proposed dataset name:**

`Task1 Synthetic Environmental Observation Dataset`

**Dataset type:**

Synthetic training dataset

**Current observed schema versions:**

* Version 1.0
* Version 1.1

**Record count:**

20 records

**Field count:**

10 fields

**Proposed registration status:**

MOCK — NOT REGISTERED

No canonical MASTERDB dataset ID is claimed.

---

## 3. Source

The supplied source register contains six synthetic sources:

| Source ID | Source Name                      | Method                 | Refresh |
| --------- | -------------------------------- | ---------------------- | ------- |
| SRC-A     | Training nursery register        | Manual form simulation | Daily   |
| SRC-B     | Training water observations      | Mock sensor export     | Hourly  |
| SRC-C     | Training plantation log          | CSV simulation         | Weekly  |
| SRC-D     | Training coastal restoration log | Mock API export        | Daily   |
| SRC-E     | Training water observations 2    | Mock sensor export     | Hourly  |
| SRC-F     | Training nursery register 2      | Manual form simulation | Daily   |

All listed sources are identified as synthetic in the supplied source register.

---

## 4. Owner Role

**Proposed owner role:**

Synthetic custodian

The supplied source register identifies the owner role for all six sources as `Synthetic custodian`.

This is a proposed/mock ownership field and does not represent assignment of a real BHIV system owner.

---

## 5. Permission Basis

**Permission basis:**

Synthetic use only

The source register identifies the permission for the supplied sources as `Synthetic use only`.

No private BHIV data or restricted production data was used.

---

## 6. Classification

**Proposed classification:**

`SYNTHETIC TRAINING DATA ONLY`

This classification is applied because the supplied dataset is intended for the Task 1 training exercise.

It must not be interpreted as a production data classification or a live MASTERDB approval.

---

## 7. Proposed Schema

| Field            | Proposed Type    | Description                                     |
| ---------------- | ---------------- | ----------------------------------------------- |
| `record_id`      | String           | Unique record identifier                        |
| `source_id`      | String           | Identifier of the originating synthetic source  |
| `observed_at`    | Timestamp/String | Observation date and time                       |
| `district`       | String           | District associated with the observation        |
| `asset_type`     | String           | Type of environmental asset/observation         |
| `quantity`       | Numeric/String   | Observed quantity or measurement                |
| `unit`           | String           | Unit associated with quantity                   |
| `status`         | Enum/String      | Record quality/status indicator                 |
| `schema_version` | String           | Schema version associated with the record       |
| `source_ref`     | String           | Reference to the originating source observation |

---

## 8. Refresh

The supplied sources have different refresh frequencies:

* SRC-A — Daily
* SRC-B — Hourly
* SRC-C — Weekly
* SRC-D — Daily
* SRC-E — Hourly
* SRC-F — Daily

Therefore, the proposed dataset should not be assigned one universal refresh frequency without first defining how the multiple source refresh schedules are handled.

**Proposed registration note:**

`Refresh is source-dependent and requires confirmation of dataset-level refresh semantics.`

---

## 9. Quality State

The Day 3 validation identified seven records requiring quality attention.

| Disposition                                 | Count |
| ------------------------------------------- | ----: |
| No exception identified under defined rules |    13 |
| REVIEW                                      |     3 |
| REJECT                                      |     4 |
| Total records                               |    20 |

### REVIEW records

* R006 — ambiguous numeric representation (`7,1`)
* R009 — repeated source reference
* R014 — unusually large quantity (`99999`)

### REJECT records

* R008 — negative count (`-12`)
* R010 — missing quantity
* R011 — missing source reference
* R020 — malformed timestamp (`not-a-date`)

The original records were not modified.

---

## 10. Quality Limitations

The following limitations were identified from the supplied source information and Day 3 validation:

1. R006 contains a comma-formatted quantity (`7,1`) whose intended numeric representation requires confirmation.
2. R008 contains a negative count.
3. R009 shares source reference `SRC-C:007` with R007.
4. R010 has a missing quantity.
5. R011 has a missing source reference.
6. R014 contains an unusually large quantity (`99999`), but no hard maximum threshold is defined in the supplied information.
7. R020 contains a malformed timestamp.
8. Source-specific refresh frequencies differ.
9. The dataset contains both schema versions 1.0 and 1.1.
10. No live MASTERDB registration or approval has been performed.

---

## 11. Proposed Lifecycle

The following lifecycle is a proposed training workflow:

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

For this Task 1 exercise, the dataset should remain conceptually at the **DRAFT / MOCK** stage.

No `APPROVED`, `ACTIVE`, `DEPRECATED`, or `RETIRED` production status is being claimed.

---

## 12. Proposed Registration Decision

**Mock decision:**

`REVIEW REQUIRED BEFORE ANY REAL REGISTRATION`

Reason:

The dataset has identified quality exceptions, unresolved schema/version questions and source-dependent refresh behaviour.

This decision is part of the training exercise only.

---

## 13. Explicit Boundary Statement

This packet does not create or claim:

* A canonical MASTERDB dataset ID
* A production registration
* Production approval
* A live owner assignment
* A live permission grant
* A production lifecycle state
* Access to MASTERDB or InsightFlow
* Any modification to BHIV systems

All information in this packet is for synthetic training purposes only.
