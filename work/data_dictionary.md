# Day 2 — Data Dictionary

**Dataset:** task1_synthetic_dataset.csv
**Classification:** SYNTHETIC TRAINING DATA ONLY

| Field          | Description                                         | Expected Type      | Observed Values / Notes                                         |
| -------------- | --------------------------------------------------- | ------------------ | --------------------------------------------------------------- |
| record_id      | Unique identifier for each dataset record           | String             | R001–R020                                                       |
| source_id      | Identifier of the source associated with the record | String             | SRC-A to SRC-F                                                  |
| observed_at    | Date and time when the observation was recorded     | Date/Time          | Mostly ISO timestamp format; one malformed value observed       |
| district       | District associated with the observation            | Categorical/String | Pune, Nashik, Satara, Maval, Thane, Mumbai, Kolhapur            |
| asset_type     | Type of asset or observation                        | Categorical/String | seedling, sapling, water_sample, plantation, mangrove           |
| quantity       | Numerical or measured quantity                      | Numeric            | Count values and pH values; some values require review          |
| unit           | Unit associated with quantity                       | Categorical/String | count or pH                                                     |
| status         | Current record status                               | Categorical/String | valid, review, invalid                                          |
| schema_version | Version of the schema used by the record            | Version            | 1.0 or 1.1                                                      |
| source_ref     | Reference to the original/source record             | String             | Source references such as SRC-A:001; one missing value observed |

## Source Register Fields

The `task1_source_register.csv` file contains:

| Field       | Description                            |
| ----------- | -------------------------------------- |
| source_id   | Unique identifier for a source         |
| source_name | Name/description of the source         |
| owner_role  | Role responsible for the source        |
| method      | Method used to produce the source data |
| permission  | Permission classification              |
| refresh     | Expected refresh frequency             |
| limitations | Known limitations of the source        |
