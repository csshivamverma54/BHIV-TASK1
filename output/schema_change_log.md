#  Schema Change Log

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Baseline

**Current schema:** v1.0

The v1.0 schema contains 10 fields:

`record_id`, `source_id`, `observed_at`, `district`, `asset_type`, `quantity`, `unit`, `status`, `schema_version`, `source_ref`

---

## Change 1 — Compatible Change

### Proposed version

`v1.1`

### Change

Add an optional field:

```text
observation_note
```

**Type:** String

**Required:** No

**Purpose:** Allows an optional explanatory note to accompany an observation.

### Why this is compatible

Existing records do not need to contain this field.

Existing consumers that only use the original v1.0 fields can continue operating without requiring the new field.

### Consumer Impact

**Expected impact: Low**

Existing consumers can ignore the new optional field.

Consumers that want the new information can be updated to read it.

### Historical Reconstruction

Historical v1.0 records remain identifiable as v1.0 records.

The new field should not be invented for historical records.

If a historical record has no observation note, it should remain absent rather than being populated with fabricated information.

### Proposed versioning decision

```text
v1.0 → v1.1
Compatible change
```

---

# Change 2 — Breaking Change

### Proposed version

`v2.0`

### Change

Rename:

```text
quantity
```

to:

```text
measurement_value
```

and make the new field the required field.

### Why this is breaking

Existing consumers expecting a field named `quantity` may no longer find that field.

Queries, validation rules, reports or applications that depend on `quantity` would require modification.

### Consumer Impact

**Expected impact: High**

Consumers using `quantity` would need to be updated.

Examples of potentially affected logic include:

* Quantity calculations
* Unit-aware validation
* Reports
* Data extraction
* Retrieval logic
* Downstream applications

### Historical Reconstruction

Historical records should not simply have their original field name overwritten.

The historical v1.0 representation should remain identifiable.

A controlled transformation could map:

```text
v1.0 quantity
        ↓
v2.0 measurement_value
```

but the transformation must be documented so that the historical representation can be reconstructed.

### Proposed versioning decision

```text
v1.0 → v2.0
Breaking change
```

---

## Comparison

| Change                                   | Version | Type       | Consumer Impact |
| ---------------------------------------- | ------- | ---------- | --------------- |
| Add optional `observation_note`          | v1.1    | Compatible | Low             |
| Rename `quantity` to `measurement_value` | v2.0    | Breaking   | High            |

## Important Rule

No schema change should silently overwrite the historical meaning of existing records.

The schema version and transformation history should remain traceable.
