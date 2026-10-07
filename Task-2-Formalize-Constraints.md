# Task 2 — Formalize Constraints

## Logical Symbols

The following symbols are used:

* `Train_Present` = A train is present at the crossing.
* `Train_Approaching` = A train is approaching the crossing.
* `Barrier_Open` = The barrier is open.
* `Barrier_Closed` = The barrier is closed.
* `Train_Cleared` = The train has completely cleared the crossing.
* `Warning_Active` = Warning lights and audible alarms are active.
* `Sensor_Failure` = A train-detection sensor has failed or provided an invalid reading.
* `Barrier_Failure` = A barrier failure has been detected.
* `Communication_Lost` = Communication with the control center is lost.
* `Emergency` = An emergency condition exists.
* `Safe_Indication` = The system indicates that the crossing is safe for road traffic.

---

## C1 — Barrier Must Not Open While Train Is Present

### Simple English

The barrier must not be open when a train is present at the crossing.

### Formal Expression

```text
Train_Present → ¬Barrier_Open
```

---

## C2 — Barrier Must Close Before Train Enters

### Simple English

If a train is approaching, the barrier must be closed before the train reaches the crossing.

### Formal Expression

```text
Train_Approaching → Barrier_Closed
```

---

## C3 — Warnings Must Be Active for an Approaching Train

### Simple English

If a train is approaching, warning lights and audible alarms must be active.

### Formal Expression

```text
Train_Approaching → Warning_Active
```

---

## C4 — Barrier Must Remain Closed While Train Is Passing

### Simple English

If a train is present and has not yet cleared the crossing, the barrier must remain closed.

### Formal Expression

```text
(Train_Present ∧ ¬Train_Cleared) → Barrier_Closed
```

---

## C5 — Barrier Opens Only After Train Has Cleared

### Simple English

If the barrier is open, the train must have completely cleared the crossing.

### Formal Expression

```text
Barrier_Open → Train_Cleared
```

---

## C6 — Sensor Failure Must Prevent Automatic Opening

### Simple English

If a sensor failure is detected, the system must not automatically open the barrier.

### Formal Expression

```text
Sensor_Failure → ¬Barrier_Open
```

---

## C8 — Communication Loss Must Prevent Unsafe Normal Operation

### Simple English

If communication with the control center is lost, the system must not indicate that the crossing is safe for normal road traffic.

### Formal Expression

```text
Communication_Lost → ¬Safe_Indication
```

---

## C9 — Emergency Must Prevent Unsafe Road Traffic

### Simple English

If an emergency condition exists, the system must not indicate that the crossing is safe.

### Formal Expression

```text
Emergency → ¬Safe_Indication
```

---



Eight system constraints have been converted into formal logical expressions. These expressions can be used to check whether the system is operating according to its safety requirements.
