#  Exception Register

**Classification:** SYNTHETIC TRAINING DATA ONLY

The following exceptions were identified by applying the deterministic quality rules to the synthetic dataset.

| Record ID | Rule ID | Field / Value                      | Disposition | Reason                                                                                                                                       |
| --------- | ------- | ---------------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| R006      | Q06     | quantity = `7,1`                   | REVIEW      | Numeric value uses a comma representation and requires confirmation of intended decimal interpretation.                                      |
| R008      | Q07     | quantity = `-12`, unit = `count`   | REJECT      | A count quantity cannot be negative under the defined rule.                                                                                  |
| R009      | Q11     | source_ref = `SRC-C:007`           | REVIEW      | The source reference is repeated and requires investigation to determine whether it represents a duplicate or repeated observation.          |
| R010      | Q05     | quantity = missing                 | REJECT      | Required quantity value is missing.                                                                                                          |
| R011      | Q10     | source_ref = missing               | REJECT      | Source reference is missing and provenance cannot be directly identified from the record.                                                    |
| R014      | Q07     | quantity = `99999`, unit = `count` | REVIEW      | The value is unusually large compared with the surrounding synthetic observations and requires confirmation rather than automatic rejection. |
| R020      | Q04     | observed_at = `not-a-date`         | REJECT      | The observed timestamp does not follow a valid date/time representation.                                                                     |

## Exception Handling Notes

### R006 — Ambiguous Numeric Representation

The value `7,1` is not silently converted to `7.1`. It is placed in REVIEW because the available data does not establish whether the comma is intended as a decimal separator.

### R008 — Negative Count

The value `-12` is rejected because the record uses the `count` unit and a negative count is not acceptable under the defined deterministic rule.

### R009 — Repeated Source Reference

The source reference `SRC-C:007` appears more than once. It is placed in REVIEW because the available information does not prove whether this is an accidental duplicate or a legitimate repeated observation.

### R010 — Missing Quantity

The quantity field is missing. The value is not estimated or filled in. The record is rejected under the required-field rule.

### R011 — Missing Source Reference

The source reference is missing. The value is not invented or reconstructed. The record is rejected because direct source traceability is incomplete.

### R014 — Extreme Quantity

The quantity `99999` is unusually large relative to the surrounding synthetic observations. It is placed in REVIEW rather than rejected because the available source information does not define a hard maximum threshold.

### R020 — Malformed Timestamp

The value `not-a-date` cannot be interpreted as a valid timestamp using the defined format. It is rejected rather than silently repaired.

## Data Handling Rule

No values in the original dataset were changed during this quality-check process.
