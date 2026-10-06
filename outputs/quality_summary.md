#  Quality Summary

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Overall Result

The synthetic dataset contains **20 records**.

After applying the deterministic quality rules, **7 records were identified with quality exceptions**.

| Category                              | Records |
| ------------------------------------- | ------: |
| Total records checked                 |      20 |
| Records with identified exceptions    |       7 |
| Records without identified exceptions |      13 |
| REVIEW exceptions                     |       3 |
| REJECT exceptions                     |       4 |

## Exception Distribution

| Disposition                      | Records | Record IDs                                   |
| -------------------------------- | ------: | -------------------------------------------- |
| ACCEPT / no exception identified |      13 | Remaining records                            |
| REVIEW                           |       3 | R006, R009, R014                             |
| REJECT                           |       4 | R008, R010, R011, R020                       |
| **Total affected records**       |   **7** | **R006, R008, R009, R010, R011, R014, R020** |

## Quality Observations

The main quality issues identified were:

1. Ambiguous numeric representation in `quantity`.
2. Negative value for a count.
3. Repeated source reference.
4. Missing quantity.
5. Missing source reference.
6. Unusually large quantity.
7. Malformed timestamp.

## Important Handling Decision

The quality process does not automatically repair any of these values. Instead, each exception is documented with the affected record, rule, observed value, reason, and disposition.

This preserves the original evidence and makes the quality decision reproducible.

## Reconciliation Check

Total records:

`20`

Records with exceptions:

`7`

Records without identified exceptions:

`13`

Reconciliation:

`7 + 13 = 20`

**Result: PASS**

## Limitation

The available synthetic source information does not define a hard maximum for plantation or mangrove counts. Therefore, the value `99999` is classified as REVIEW rather than REJECT.

Similarly, the value `7,1` is not automatically converted to `7.1` because the intended numeric representation is not established by the available evidence.
