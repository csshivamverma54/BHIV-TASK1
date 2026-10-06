

# Metric Dictionary

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Metric 1 — Record Count

### Name

`record_count`

### Definition

Total number of records in the synthetic dataset.

### Formula

```text
record_count = number of dataset rows
```

### Population

All records in `task1_synthetic_dataset.csv`.

### Window

Entire supplied synthetic dataset.

### Result

```text
20 records
```

### Caveat

This is a count of the supplied synthetic dataset and does not represent a live MASTERDB dataset count.

---

## Metric 2 — Flagged Rate

### Name

`flagged_rate`

### Definition

Percentage of records whose status is `review` or `invalid`.

### Formula

```text
flagged_rate =
(review records + invalid records)
---------------------------------- × 100
       total records
```

### Population

All 20 synthetic dataset records.

### Window

Entire supplied synthetic dataset.

### Calculation

Status distribution:

```text
valid   = 14
review  = 5
invalid = 1
```

Therefore:

```text
flagged records = 5 + 1
                = 6

flagged rate = 6 / 20 × 100
             = 30%
```

### Result

**30%**

### Caveat

The metric uses the status values already present in the synthetic dataset. It should not be interpreted as a production data-quality rate.

---

## Metric 3 — Source-Reference Completeness

### Name

`source_reference_completeness`

### Definition

Percentage of records containing a non-missing `source_ref`.

### Formula

```text
source-reference completeness =
records with source_ref
----------------------- × 100
total records
```

### Population

All 20 synthetic dataset records.

### Window

Entire supplied synthetic dataset.

### Calculation

Records with a source reference:

```text
19
```

Total records:

```text
20
```

Therefore:

```text
19 / 20 × 100 = 95%
```

### Result

**95%**

### Caveat

A present source reference does not prove that the reference is unique or valid. For example, the dataset contains a repeated source reference that requires review.

---

## Independent Recalculation Table

| Metric                        | Formula                          | Result |
| ----------------------------- | -------------------------------- | -----: |
| Record count                  | Number of rows                   |     20 |
| Flagged rate                  | (Review + Invalid) / Total × 100 |    30% |
| Source-reference completeness | Present source_ref / Total × 100 |    95% |

## Measurement Principle

Each metric has a defined formula, population, time/data window and caveat so that another person can reproduce the result from the same synthetic input.
