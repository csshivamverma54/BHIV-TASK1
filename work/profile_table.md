# Day 2 — Data Profile

**Dataset:** task1_synthetic_dataset.csv
**Classification:** SYNTHETIC TRAINING DATA ONLY

| Profiling Item              |      Result |
| --------------------------- | ----------: |
| Total rows                  |          20 |
| Total columns               |          10 |
| Unique record IDs           |          20 |
| Missing values              |           2 |
| Duplicate complete rows     |           0 |
| Unique source IDs           |           6 |
| Unique districts            |           7 |
| Unique asset types          |           5 |
| Unique units                |           2 |
| Unique statuses             |           3 |
| Schema versions             | 1.0 and 1.1 |
| Unique source references    |          18 |
| Distinct observed_at values |          20 |

## Missing Values

| Field          | Missing Count |
| -------------- | ------------: |
| record_id      |             0 |
| source_id      |             0 |
| observed_at    |             0 |
| district       |             0 |
| asset_type     |             0 |
| quantity       |             1 |
| unit           |             0 |
| status         |             0 |
| schema_version |             0 |
| source_ref     |             1 |

## Category Counts

### Source ID

| Source | Records |
| ------ | ------: |
| SRC-A  |       5 |
| SRC-B  |       3 |
| SRC-C  |       3 |
| SRC-D  |       3 |
| SRC-E  |       3 |
| SRC-F  |       3 |

### Status

| Status  | Records |
| ------- | ------: |
| valid   |      14 |
| review  |       5 |
| invalid |       1 |

### Unit

| Unit  | Records |
| ----- | ------: |
| count |      14 |
| pH    |       6 |

### Asset Type

| Asset Type   | Records |
| ------------ | ------: |
| seedling     |       7 |
| water_sample |       6 |
| plantation   |       3 |
| mangrove     |       3 |
| sapling      |       1 |

## Initial Observations

1. The dataset contains 20 records.
2. Every `record_id` is currently unique.
3. There are no completely duplicated rows.
4. Two fields contain missing values: `quantity` and `source_ref`.
5. One `observed_at` value is malformed (`not-a-date`).
6. One quantity uses a comma decimal format (`7,1`).
7. A negative quantity (`-12`) is present.
8. A very large quantity (`99999`) is marked for review.
9. `source_ref` is repeated for `SRC-C:007`.
10. The dataset contains both schema versions 1.0 and 1.1.
