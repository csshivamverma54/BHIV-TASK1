# Failure Simulations

**Classification:** SYNTHETIC TRAINING DATA ONLY

## Failure 1 — Missing Version

### Scenario

A retrieval request asks for:

```text
schema_version = 2.0
```

but the supplied synthetic dataset contains only:

```text
1.0
1.1
```

### Expected Behaviour

The request should not silently return another version.

### Simulated Response

```text
STATUS: VERSION_NOT_FOUND

Requested version: 2.0
Available versions: 1.0, 1.1

Action:
Do not substitute a different version automatically.
Request clarification or use an explicitly available version.
```

### Safety Reason

Returning version 1.1 when version 2.0 was requested could produce incorrect interpretation.

---

# Failure 2 — Stale Input

### Scenario

A consumer expects a newer refresh of a source, but the available local training input has not been refreshed.

For example, SRC-B is described as having an hourly refresh in the supplied source register.

### Expected Behaviour

The system/process should identify that freshness cannot be confirmed rather than pretending the data is current.

### Simulated Response

```text
STATUS: FRESHNESS_UNCONFIRMED

Source: SRC-B
Expected refresh: Hourly
Available evidence: Local synthetic file only

Action:
Do not claim that the current data is fresh.
Record freshness as unverified and request a newer input if required.
```

### Safety Reason

A dataset should not be described as current when freshness has not been verified.

---

# Failure 3 — Unauthorized Request

### Scenario

A hypothetical request asks for access to a restricted/private BHIV dataset.

### Expected Behaviour

The request must not be fulfilled because Task 1 does not provide authorization or system access.

### Simulated Response

```text
STATUS: UNAUTHORIZED

Requested resource:
Private / production BHIV dataset

Action:
Reject the request.
Do not access credentials, private data, internal repositories or internal endpoints.
```

### Safety Reason

Task 1 explicitly has an access lock. The exercise is limited to supplied synthetic data.

---

## Failure Summary

| Failure              | Expected Action                                       |
| -------------------- | ----------------------------------------------------- |
| Missing version      | Do not substitute; request clarification              |
| Stale input          | Mark freshness unverified                             |
| Unauthorized request | Reject request and do not access restricted resources |

## Boundary

These are simulated failure scenarios. No live system failure or production endpoint was tested.
