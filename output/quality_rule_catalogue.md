#  Deterministic Quality Rule Catalogue

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Objective

The objective of the Day 3 quality checks is to apply deterministic rules to the synthetic dataset and identify records that require acceptance, review, or rejection.

The original CSV files are preserved and are not modified.

## Disposition Definitions

* **ACCEPT:** The record passes the applicable quality rule.
* **REVIEW:** The value may be usable, but requires human or defined business-rule confirmation.
* **REJECT:** The record fails a required quality condition and should not be accepted as valid without correction or clarification.

## Rule Catalogue

| Rule ID | Quality Rule                                          | Check                                                                   | Disposition                           |
| ------- | ----------------------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------- |
| Q01     | Record ID is required                                 | `record_id` must not be blank                                           | REJECT if missing                     |
| Q02     | Record ID must be unique                              | No two records may have the same `record_id`                            | REJECT if duplicated                  |
| Q03     | Source ID must be registered                          | `source_id` must exist in the supplied source register                  | REJECT if unregistered                |
| Q04     | Observed timestamp must be valid                      | `observed_at` must follow a valid timestamp format                      | REJECT if malformed                   |
| Q05     | Quantity must be present                              | `quantity` must not be missing when a quantity is required              | REJECT if missing                     |
| Q06     | Quantity must be numerically interpretable            | Quantity must be a valid numeric value using the defined representation | REVIEW if representation is ambiguous |
| Q07     | Count quantities must be positive                     | When `unit = count`, quantity must be greater than 0                    | REJECT if zero or negative            |
| Q08     | pH values must be within the normal measurement range | When `unit = pH`, quantity must be between 0 and 14                     | REJECT if outside range               |
| Q09     | Unit must match the asset type                        | `water_sample` uses `pH`; counted assets use `count`                    | REJECT if inconsistent                |
| Q10     | Source reference must be present                      | `source_ref` must not be blank                                          | REJECT if missing                     |
| Q11     | Source reference should not repeat unexpectedly       | A repeated `source_ref` must be investigated                            | REVIEW                                |
| Q12     | Status must use an allowed value                      | Status must be `valid`, `review`, or `invalid`                          | REJECT if outside allowed set         |
| Q13     | Schema version must use an observed version           | Schema version must be one of the supplied versions (`1.0` or `1.1`)    | REJECT if unknown                     |

## Rule Application Principle

Rules are applied to the existing values without silently correcting them. When a value is ambiguous or unusual but cannot be conclusively declared invalid from the available evidence, it is placed in REVIEW rather than automatically changed or accepted.
