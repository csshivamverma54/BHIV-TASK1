# Unresolved Questions

**Classification:** SYNTHETIC TRAINING DATA ONLY

The following questions remain unresolved because the supplied Task 1 material does not provide enough information to answer them safely.

| ID    | Question                                                                                                           | Why It Matters                                                                | Current Safe Position                                      |
| ----- | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- | ---------------------------------------------------------- |
| UQ-01 | What is the canonical dataset name and identifier in MASTERDB?                                                     | A real registration requires governed identity.                               | Do not invent an ID.                                       |
| UQ-02 | Who is the authoritative production owner for this dataset?                                                        | Ownership affects accountability and lifecycle decisions.                     | Use `Synthetic custodian` only for the mock exercise.      |
| UQ-03 | Is `Synthetic use only` sufficient as the permission basis for an actual registration?                             | Permission requirements may depend on the real system.                        | Treat it as mock evidence only.                            |
| UQ-04 | What is the authoritative schema definition for versions 1.0 and 1.1?                                              | Version compatibility and consumer impact depend on the canonical schema.     | Do not claim canonical schema semantics.                   |
| UQ-05 | What is the intended dataset-level refresh frequency when sources have different refresh schedules?                | Sources refresh hourly, daily or weekly.                                      | Keep refresh source-dependent until defined.               |
| UQ-06 | Is `7,1` intended to mean `7.1`?                                                                                   | Automatic conversion could change the original meaning.                       | Keep the value unchanged and mark REVIEW.                  |
| UQ-07 | What is the approved maximum quantity for count-based environmental records?                                       | R014 contains `99999`.                                                        | Keep R014 in REVIEW because no hard threshold is supplied. |
| UQ-08 | Is repeated `source_ref` allowed for separate observations?                                                        | R007 and R009 both use `SRC-C:007`.                                           | Mark for review rather than assuming duplication.          |
| UQ-09 | Are rejected records expected to remain in the dataset with quality status, or be excluded from a registered view? | This affects retrieval and lineage behaviour.                                 | Do not decide without a defined rule.                      |
| UQ-10 | What are the exact lifecycle approval requirements?                                                                | The exercise provides lifecycle stages but not production approval authority. | Use lifecycle as a proposed training workflow only.        |

## Safe Assumptions Used

The following assumptions were used only to complete the mock packet:

1. The dataset is synthetic training data.
2. `Synthetic custodian` is treated as the source owner role because it is present in the supplied source register.
3. `Synthetic use only` is recorded as the supplied permission basis.
4. The observed schema fields are taken directly from the supplied dataset.
5. The lifecycle is represented as a proposed workflow, not a live system state.

These assumptions are explicitly labelled and should not be interpreted as production facts.
