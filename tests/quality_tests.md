# Quality Tests

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Test 1 — Record Count

Expected:

`20 records`

Observed:

`20 records`

Result: **PASS**

## Test 2 — Record ID Uniqueness

Expected:

All `record_id` values are unique.

Observed:

20 unique record IDs across 20 records.

Result: **PASS**

## Test 3 — Source Registration

Expected:

Every `source_id` exists in the source register.

Observed:

All source IDs used in the dataset are present in the supplied source register.

Result: **PASS**

## Test 4 — Malformed Timestamp Detection

Expected:

The malformed timestamp should be identified.

Observed:

R020 contains `observed_at = not-a-date`.

Result: **PASS**

## Test 5 — Negative Count Detection

Expected:

A negative count should be rejected.

Observed:

R008 contains `quantity = -12` with `unit = count`.

Result: **PASS**

## Test 6 — Missing Quantity Detection

Expected:

A missing required quantity should be identified.

Observed:

R010 has a missing quantity.

Result: **PASS**

## Test 7 — Missing Source Reference Detection

Expected:

A missing source reference should be identified.

Observed:

R011 has a missing `source_ref`.

Result: **PASS**

## Test 8 — Repeated Source Reference Detection

Expected:

A repeated source reference should be identified for review.

Observed:

`SRC-C:007` appears for R007 and R009.

Result: **PASS**

## Test 9 — Ambiguous Numeric Representation

Expected:

The comma-formatted quantity should be identified without silently changing it.

Observed:

R006 contains `7,1`.

Result: **PASS**

## Test 10 — Original Data Preservation

Expected:

Original CSV files remain unchanged.

Observed:

No values were modified during the quality-check process.

Result: **PASS**
