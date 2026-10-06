# Schema Change Log

**Classification:** SYNTHETIC TRAINING DATA ONLY
**Dataset:** Task1 Synthetic Environmental Observation Dataset

## 1. Baseline

| Version | Status           | Description                                            |
| ------- | ---------------- | ------------------------------------------------------ |
| 1.0     | Baseline / Draft | Initial schema documenting the supplied dataset fields |

## 2. Compatible Change

| Item              | Detail                                                     |
| ----------------- | ---------------------------------------------------------- |
| Change Type       | Compatible                                                 |
| From Version      | 1.0                                                        |
| To Version        | 1.1                                                        |
| Change            | Add optional `observation_note` field                      |
| Data Type         | String                                                     |
| Required          | No                                                         |
| Consumer Impact   | Existing consumers can continue using the original fields  |
| Historical Impact | Existing historical records remain valid                   |
| Reconstruction    | Missing `observation_note` is acceptable for older records |

### Reasoning

Adding an optional field does not require existing consumers to change their existing field usage. Therefore, this is treated as a compatible schema change.

## 3. Breaking Change

| Item              | Detail                                                        |
| ----------------- | ------------------------------------------------------------- |
| Change Type       | Breaking                                                      |
| From Version      | 1.1                                                           |
| To Version        | 2.0                                                           |
| Change            | Rename `quantity` to `measurement_value`                      |
| Consumer Impact   | Consumers using `quantity` must update their field references |
| Historical Impact | Existing historical records must not be silently overwritten  |
| Reconstruction    | Original v1.x representation must remain traceable            |

### Reasoning

Renaming an existing field changes the interface expected by consumers. Therefore, the change is considered breaking.

## 4. Versioning Rules

1. Every record must identify its `schema_version`.
2. Schema changes must be explicitly documented.
3. Compatible and breaking changes must be distinguished.
4. Historical records must remain reconstructable.
5. Existing data must not be silently rewritten to a new schema.
6. Production approval or registration must not be claimed for this training exercise.

## 5. Validation Status

| Check                                  | Result |
| -------------------------------------- | ------ |
| Baseline schema documented             | PASS   |
| Compatible change documented           | PASS   |
| Breaking change documented             | PASS   |
| Consumer impact explained              | PASS   |
| Historical reconstruction explained    | PASS   |
| Silent historical overwrite prohibited | PASS   |

**Status:** PASS — documentation-level schema/version requirements addressed.

**SYNTHETIC TRAINING DATA ONLY**
