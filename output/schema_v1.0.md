# Schema v1.0

**Classification:** SYNTHETIC TRAINING DATA ONLY
**Schema Status:** DRAFT / TRAINING USE ONLY
**Dataset:** Task1 Synthetic Environmental Observation Dataset

## 1. Purpose

This schema defines the expected fields, data types, required status, and basic constraints for the supplied synthetic environmental observation dataset.

The schema is a documentation and validation proposal only. It is not a production MASTERDB schema and does not represent production approval.

## 2. Schema Definition

| Field Name       | Data Type     | Required | Constraint / Expected Format                    | Description                                     |
| ---------------- | ------------- | -------- | ----------------------------------------------- | ----------------------------------------------- |
| `record_id`      | String        | Yes      | Unique identifier                               | Unique identifier for each observation record   |
| `source_id`      | String        | Yes      | Must match a registered source ID               | Identifies the originating source               |
| `observed_at`    | Timestamp     | Yes      | ISO-8601 timestamp                              | Date and time when the observation was recorded |
| `district`       | String        | Yes      | Non-empty text                                  | District associated with the observation        |
| `asset_type`     | String / Enum | Yes      | Known asset category                            | Type of environmental asset or observation      |
| `quantity`       | Numeric       | Yes      | Numeric value; interpretation depends on `unit` | Measured quantity or count                      |
| `unit`           | String / Enum | Yes      | `count` or `pH` in supplied dataset             | Unit associated with quantity                   |
| `status`         | Enum          | Yes      | `valid`, `review`, or `invalid`                 | Current quality status of the record            |
| `schema_version` | String        | Yes      | Controlled version value                        | Schema version associated with the record       |
| `source_ref`     | String        | Yes      | Non-empty source reference                      | Reference back to the originating source record |

## 3. Field-Level Validation Rules

### `record_id`

* Required.
* Must be unique.
* Must not be blank.

### `source_id`

* Required.
* Must correspond to a source in the source register.
* Must not be blank.

### `observed_at`

* Required.
* Expected to be a valid timestamp.
* ISO-8601 timestamp format is the expected representation.

### `district`

* Required.
* Must contain a non-empty text value.

### `asset_type`

* Required.
* Must contain a recognized asset type.

Observed asset types in the supplied dataset are:

* `seedling`
* `sapling`
* `water_sample`
* `plantation`
* `mangrove`

### `quantity`

* Required.
* Expected to be numerically interpretable.
* For `count`, the value must be greater than zero.
* For `pH`, the value must be within the range 0–14.

### `unit`

* Required.
* Expected values in the supplied dataset are:

  * `count`
  * `pH`

### `status`

* Required.
* Allowed values:

  * `valid`
  * `review`
  * `invalid`

### `schema_version`

* Required.
* Supplied dataset versions are `1.0` and `1.1`.

### `source_ref`

* Required.
* Must be present for a complete source trace.
* Repeated references require review rather than silent correction.

## 4. Schema Violations Observed in Supplied Data

The following records do not fully conform to the expected schema or require schema/quality review.

| Record | Field         | Expected                     | Actual       | Result                                                 |
| ------ | ------------- | ---------------------------- | ------------ | ------------------------------------------------------ |
| R006   | `quantity`    | Numeric                      | `7,1`        | REVIEW — numeric representation requires clarification |
| R008   | `quantity`    | Positive numeric for `count` | `-12`        | REJECT — violates count constraint                     |
| R010   | `quantity`    | Required numeric value       | Missing      | REJECT — required field missing                        |
| R011   | `source_ref`  | Required string              | Missing      | REJECT — required field missing                        |
| R014   | `quantity`    | Numeric count                | `99999`      | REVIEW — extreme value requires policy review          |
| R020   | `observed_at` | Valid timestamp              | `not-a-date` | REJECT — invalid timestamp                             |

R009 also requires quality review because its `source_ref` is repeated:

| Record | Field        | Actual      | Result                             |
| ------ | ------------ | ----------- | ---------------------------------- |
| R009   | `source_ref` | `SRC-C:007` | REVIEW — repeated source reference |

No original values were silently changed.

## 5. Schema Version Discipline

### Current Baseline

**Schema version:** `1.0`

The baseline schema represents the fields present in the supplied dataset.

### Compatible Change — Version 1.1

Proposed addition:

```text
observation_note : String
```

The field is optional.

**Reason:** Existing consumers can continue using all existing v1.0 fields without modification.

**Consumer impact:** Low. Existing consumers can ignore the new optional field.

**Historical reconstruction:** Existing v1.0 records remain valid. The new field may be absent from historical records.

### Breaking Change — Version 2.0

Proposed change:

```text
quantity → measurement_value
```

The field name `quantity` would be renamed to `measurement_value`.

**Reason:** Consumers that currently depend on `quantity` would no longer find the original field.

**Consumer impact:** Existing consumers must update their field references.

**Historical reconstruction:** Historical records must preserve the original v1.x representation or use an explicitly documented transformation. Historical data must not be silently overwritten.

## 6. Schema Status

```text
Schema Version: 1.0
Status: DRAFT
Purpose: Synthetic training and validation
Production Approval: NOT CLAIMED
Production Registration: NOT CLAIMED
```

**SYNTHETIC TRAINING DATA ONLY**
