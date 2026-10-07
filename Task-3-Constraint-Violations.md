# Task 3 — Identify Constraint Violations

The following scenarios show realistic situations in which the formalized constraints are violated.

---

## Violation 1 — C1

### Constraint

```text
Train_Present → ¬Barrier_Open
```

### Violation Scenario

```text
Train_Present = TRUE
Barrier_Open = TRUE
```

### What Went Wrong?

A train is present at the crossing, but the road barrier is open.

### How Do We Know the Constraint Was Violated?

The constraint requires:

```text
Train_Present → ¬Barrier_Open
```

Since `Train_Present = TRUE` and `Barrier_Open = TRUE`, the required condition `¬Barrier_Open` is false.

Therefore, **C1 is violated**.

---

## Violation 2 — C2

### Constraint

```text
Train_Approaching → Barrier_Closed
```

### Violation Scenario

```text
Train_Approaching = TRUE
Barrier_Closed = FALSE
```

### What Went Wrong?

The system detected an approaching train, but the barrier remained open.

### How Do We Know the Constraint Was Violated?

The constraint requires the barrier to be closed whenever a train is approaching.

Since `Train_Approaching = TRUE` but `Barrier_Closed = FALSE`, **C2 is violated**.

---

## Violation 3 — C3

### Constraint

```text
Train_Approaching → Warning_Active
```

### Violation Scenario

```text
Train_Approaching = TRUE
Warning_Active = FALSE
```

### What Went Wrong?

An approaching train was detected, but the warning lights and audible alarms were not activated.

### How Do We Know the Constraint Was Violated?

The constraint requires warnings to be active when a train is approaching.

Since the train is approaching but `Warning_Active = FALSE`, **C3 is violated**.

---

## Violation 4 — C4

### Constraint

```text
(Train_Present ∧ ¬Train_Cleared) → Barrier_Closed
```

### Violation Scenario

```text
Train_Present = TRUE
Train_Cleared = FALSE
Barrier_Closed = FALSE
```

### What Went Wrong?

The train is still passing through the crossing, but the barrier is not closed.

### How Do We Know the Constraint Was Violated?

Both conditions on the left side are true:

```text
Train_Present = TRUE
¬Train_Cleared = TRUE
```

Therefore, the barrier must be closed. However, `Barrier_Closed = FALSE`.

Therefore, **C4 is violated**.

---

## Violation 5 — C5

### Constraint

```text
Barrier_Open → Train_Cleared
```

### Violation Scenario

```text
Barrier_Open = TRUE
Train_Cleared = FALSE
```

### What Went Wrong?

The system opened the barrier before confirming that the train had completely cleared the crossing.

### How Do We Know the Constraint Was Violated?

The constraint says that an open barrier implies that the train has cleared the crossing.

Since `Barrier_Open = TRUE` but `Train_Cleared = FALSE`, **C5 is violated**.

---

## Violation 6 — C6

### Constraint

```text
Sensor_Failure → ¬Barrier_Open
```

### Violation Scenario

```text
Sensor_Failure = TRUE
Barrier_Open = TRUE
```

### What Went Wrong?

A train-detection sensor failed, but the system automatically opened the barrier.

### How Do We Know the Constraint Was Violated?

When a sensor failure occurs, the barrier must not be opened automatically.

Since `Sensor_Failure = TRUE` and `Barrier_Open = TRUE`, **C6 is violated**.

---

## Violation 7 — C8

### Constraint

```text
Communication_Lost → ¬Safe_Indication
```

### Violation Scenario

```text
Communication_Lost = TRUE
Safe_Indication = TRUE
```

### What Went Wrong?

Communication with the control center was lost, but the system still indicated that the crossing was safe for normal road traffic.

### How Do We Know the Constraint Was Violated?

The constraint requires `Safe_Indication` to be false when communication is lost.

Since `Communication_Lost = TRUE` and `Safe_Indication = TRUE`, **C8 is violated**.

---

## Violation 8 — C9

### Constraint

```text
Emergency → ¬Safe_Indication
```

### Violation Scenario

```text
Emergency = TRUE
Safe_Indication = TRUE
```

### What Went Wrong?

An emergency condition exists, but the system indicates that the crossing is safe.

### How Do We Know the Constraint Was Violated?

During an emergency, the system must not indicate that the crossing is safe.

Since `Emergency = TRUE` and `Safe_Indication = TRUE`, **C9 is violated**.

---

## Summary of Violations

| Violation | Constraint | Unsafe Condition                                      |
| --------- | ---------- | ----------------------------------------------------- |
| V1        | C1         | Train present while barrier is open                   |
| V2        | C2         | Train approaching while barrier is not closed         |
| V3        | C3         | Train approaching but warnings are inactive           |
| V4        | C4         | Train is passing but barrier is not closed            |
| V5        | C5         | Barrier opens before train clears                     |
| V6        | C6         | Sensor failure but barrier opens                      |
| V7        | C8         | Communication lost but safe indication remains active |
| V8        | C9         | Emergency exists but safe indication remains active   |

These violation scenarios demonstrate how the system can detect unsafe behavior by checking the formal constraints against the actual system state.
