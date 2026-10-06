#  Static Measurement Report

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Dataset Overview

| Measure                       | Result |
| ----------------------------- | -----: |
| Total records                 |     20 |
| Valid status                  |     14 |
| Review status                 |      5 |
| Invalid status                |      1 |
| Flagged records               |      6 |
| Flagged rate                  |    30% |
| Records with source reference |     19 |
| Source-reference completeness |    95% |

## Metric Interpretation

### Record Count — 20

The supplied synthetic dataset contains 20 records.

### Flagged Rate — 30%

Six records have a status of either `review` or `invalid`.

```text
6 / 20 × 100 = 30%
```

This indicates that 30% of the supplied records are already marked for attention by their status field.

### Source-Reference Completeness — 95%

Nineteen of the twenty records contain a source reference.

```text
19 / 20 × 100 = 95%
```

One record, R011, has a missing source reference.

## Key Observation

The source-reference completeness metric is high at 95%, but completeness alone does not guarantee source-reference quality. R009 and R007 share the same source reference, which was identified as a review item during Day 3.

## Measurement Limitation

All measurements are calculated from the supplied synthetic training dataset.

They do not represent live InsightFlow telemetry or production operational metrics.
