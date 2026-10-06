#  Lineage Trace

**Candidate:** Shivam Verma
**Task:** BHIV Candidate Intake — Task 1
**Classification:** SYNTHETIC TRAINING DATA ONLY

> This is a local training simulation. No live MASTERDB retrieval was performed.

## 1. Simulated Retrieval Request

**Requested dataset:** Task1 Synthetic Environmental Observation Dataset

**Requested schema version:** 1.1

**Requested record:** R012

## 2. Source Record

| Field          | Value                |
| -------------- | -------------------- |
| record_id      | R012                 |
| source_id      | SRC-D                |
| observed_at    | 2026-09-05T12:00:00Z |
| district       | Mumbai               |
| asset_type     | mangrove             |
| quantity       | 450                  |
| unit           | count                |
| status         | valid                |
| schema_version | 1.1                  |
| source_ref     | SRC-D:012            |

## 3. Source Information

| Field       | Value                            |
| ----------- | -------------------------------- |
| source_id   | SRC-D                            |
| source_name | Training coastal restoration log |
| owner_role  | Synthetic custodian              |
| method      | Mock API export                  |
| permission  | Synthetic use only               |
| refresh     | Daily                            |
| limitation  | Extreme value for review         |

## 4. Transformation Trace

For this simulated retrieval:

```text
Synthetic CSV
     ↓
Select schema_version = 1.1
     ↓
Select record_id = R012
     ↓
Return matching record
```

**Transformations performed:** Filtering only.

No value was modified.

## 5. Lineage Chain

```text
Task1 Synthetic Dataset
        ↓
schema_version = 1.1
        ↓
record R012
        ↓
source_id = SRC-D
        ↓
source_ref = SRC-D:012
        ↓
Training coastal restoration log
```

## 6. Traceability Result

**Result: PASS**

The simulated record can be traced from the dataset record to its source identifier and source reference.

## Boundary

This trace demonstrates local lineage discipline only. It does not prove that a corresponding live MASTERDB record, endpoint or production lineage exists.
