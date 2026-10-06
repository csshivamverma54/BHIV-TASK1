# Day 2 — Facts vs Questions

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Facts

| Fact                                         | Evidence                    |
| -------------------------------------------- | --------------------------- |
| Dataset contains 20 records                  | Row count                   |
| Dataset contains 10 fields                   | Column count                |
| There are 2 missing values                   | `quantity` and `source_ref` |
| There are no complete duplicate rows         | Duplicate check             |
| `observed_at` contains `not-a-date`          | Direct row inspection       |
| `quantity` contains `7,1`                    | Direct value inspection     |
| `quantity` contains `-12`                    | Direct value inspection     |
| `source_ref` `SRC-C:007` occurs twice        | Frequency check             |
| Dataset contains schema versions 1.0 and 1.1 | Frequency check             |

## Questions

| Question                                              | Why It Matters                                   |
| ----------------------------------------------------- | ------------------------------------------------ |
| Is a negative quantity ever allowed for `count`?      | Needed to define a valid quantity rule           |
| Is `99999` an acceptable count or an outlier?         | A threshold is not yet established               |
| Should `7,1` be interpreted as 7.1?                   | Requires an explicit parsing rule                |
| Is `SRC-C:007` allowed to appear in multiple records? | Need to understand source-reference uniqueness   |
| What should happen when `quantity` is missing?        | Required for a quality disposition               |
| What is the accepted date format?                     | Needed for date validation                       |
| Are schema versions 1.0 and 1.1 compatible?           | Needed for later schema/version work             |
| Should `source_ref` be mandatory?                     | Needed for later lineage and completeness checks |

## Principle

The profiling stage records what is observed. It does not silently correct or change the original data.
