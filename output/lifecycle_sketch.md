# Schema and Dataset Lifecycle

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Proposed Lifecycle

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

## 1. DRAFT

The schema or dataset definition is being prepared.

For this Task 1 exercise, the synthetic schema is currently treated as:

**DRAFT**

No production approval is claimed.

## 2. VALIDATION

The schema is checked against:

* Field names
* Data types
* Required fields
* Allowed values
* Unit logic
* Existing records
* Compatibility implications

Issues identified during validation should be documented before approval.

## 3. APPROVED

A schema would conceptually reach this state after the required review and approval process.

**Task 1 does not perform this approval.**

## 4. ACTIVE

An approved schema can conceptually become active for supported consumers.

The active version should be identifiable so that consumers know which schema they are using.

## 5. DEPRECATED

A schema can become deprecated when a newer compatible or replacement version is introduced.

Consumers should receive enough information to transition to the newer version.

The old schema should remain traceable for historical interpretation.

## 6. RETIRED

A schema is retired when it is no longer supported for new use according to the applicable lifecycle rules.

Retirement should not mean that historical evidence is silently deleted or rewritten.

## Version Discipline

A lifecycle transition should not silently change historical records.

For example:

```text
v1.0
  ↓
v1.1
```

does not mean that old v1.0 records suddenly become v1.1.

The version associated with historical records should remain traceable.

## Task 1 Boundary

The lifecycle above is a proposed training model.

No real MASTERDB schema was approved, activated, deprecated or retired during this exercise.
