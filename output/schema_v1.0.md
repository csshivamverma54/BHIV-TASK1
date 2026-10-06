#  Synthetic Dataset Schema v1.0

**Candidate:** Shivam Verma
**Task:** BHIV Candidate Intake — Task 1
**Pack:** BHIV-SHIVAM-T1 v1.0
**Classification:** SYNTHETIC TRAINING DATA ONLY
**Schema Status:** DRAFT — TRAINING EXERCISE

> This schema is a draft for the Task 1 training exercise. It is not a canonical MASTERDB schema and has not been approved for production use.

## 1. Schema Purpose

The schema defines the expected fields, data types and basic meaning of records in the synthetic environmental observation dataset.

The schema is based on the fields present in the supplied synthetic dataset.

## 2. Schema Definition

| Field            | Type           | Required | Description                                             |
| ---------------- | -------------- | -------- | ------------------------------------------------------- |
| `record_id`      | String         | Yes      | Unique identifier for the record                        |
| `source_id`      | String         | Yes      | Identifier of the source that produced the record       |
| `observed_at`    | Timestamp      | Yes      | Date and time associated with the observation           |
| `district`       | String         | Yes      | District associated with the observation                |
| `asset_type`     | String         | Yes      | Type of environmental asset or observation              |
| `quantity`       | Numeric/String | Yes*     | Quantity or measurement associated with the observation |
| `unit`           | String         | Yes      | Unit associated with the quantity                       |
| `status`         | Enum/String    | Yes      | Quality/status indicator                                |
| `schema_version` | String         | Yes      | Version of the schema used by the record                |
| `source_ref`     | String         | Yes      | Reference to the source observation                     |

* `quantity` is required according to the Day 3 quality rules, although the source dataset contains one missing quantity that was identified as an exception.

## 3. Allowed Status Values

The observed dataset uses:

```text
valid
review
invalid
```

These are treated as the allowed status values for this draft schema.

## 4. Unit Logic

The dataset contains two observed units:

```text
count
pH
```

The draft validation logic keeps these measurement types separate.

* `count` is used for counted assets.
* `pH` is used for water sample observations.

Unit-aware validation should therefore be applied instead of treating all quantities as the same type of measurement.

## 5. Version

**Schema version:** `1.0`

This is the baseline schema against which later compatible or breaking changes can be discussed.

## 6. Versioning Principle

Historical records should retain the schema version associated with the record.

A schema change should not silently rewrite the meaning of historical records.

## 7. Draft Status

```text
DRAFT
```

The schema requires validation and review before it could conceptually move to an approved or active state.

No production approval is claimed.
