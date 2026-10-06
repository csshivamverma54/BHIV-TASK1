#  Metric and Retrieval Tests

**Classification:** SYNTHETIC TRAINING DATA ONLY

| Test                            | Expected                    | Result |
| ------------------------------- | --------------------------- | ------ |
| Total record count              | 20                          | PASS   |
| Valid records                   | 14                          | PASS   |
| Review records                  | 5                           | PASS   |
| Invalid records                 | 1                           | PASS   |
| Status reconciliation           | 14 + 5 + 1 = 20             | PASS   |
| Flagged records                 | 6                           | PASS   |
| Flagged rate                    | 30%                         | PASS   |
| Records with source_ref         | 19                          | PASS   |
| Source-reference completeness   | 95%                         | PASS   |
| R012 source ID                  | SRC-D                       | PASS   |
| R012 source reference           | SRC-D:012                   | PASS   |
| R012 schema version             | 1.1                         | PASS   |
| Missing version simulation      | No silent substitution      | PASS   |
| Stale input simulation          | Freshness marked unverified | PASS   |
| Unauthorized request simulation | Request rejected            | PASS   |

## Independent Recalculation

### Record Count

```text
20
```

### Flagged Rate

```text
(5 + 1) / 20 × 100
= 30%
```

### Source-Reference Completeness

```text
19 / 20 × 100
= 95%
```

## Overall Result

**PASS**

All Day 6 calculations and simulated retrieval/failure checks are reproducible from the supplied synthetic data.
