# Task 1 — Identify Constraints

## Railway Level-Crossing Control System

The following constraints define rules that the Automated Railway Level-Crossing Control System (ARLCCS) must always satisfy.

| Constraint ID | Constraint in Simple English                                                                                                                              | Why the Constraint is Necessary                                                                                       |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **C1**        | The barrier must not open while a train is present at the crossing.                                                                                       | Opening the barrier while a train is present could allow road traffic to enter the crossing and cause an accident.    |
| **C2**        | The barrier must close before a train enters the crossing.                                                                                                | The road must be blocked before the train reaches the crossing to protect road users.                                 |
| **C3**        | Warning lights and audible alarms must be activated when an approaching train is detected.                                                                | Warnings alert drivers and pedestrians that a train is approaching.                                                   |
| **C4**        | The barrier must remain closed while the train is passing through the crossing.                                                                           | Keeping the barrier closed prevents road traffic from entering the crossing during train movement.                    |
| **C5**        | The barrier may open only after the system confirms that the train has completely cleared the crossing.                                                   | Opening before the train has cleared the crossing can create a collision risk.                                        |
| **C6**        | If a train sensor fails or gives an invalid reading, the barrier must not be opened automatically.                                                        | A failed sensor may provide incorrect information about the train's location, so opening the barrier could be unsafe. |
| **C7**        | If a barrier failure is detected, the system must activate a safety warning and report the failure to the control center.                                 | The control center must know about barrier failures so that appropriate safety action can be taken.                   |
| **C8**        | The system must not allow normal barrier operation when communication with the control center is lost if communication is required for safety monitoring. | Loss of communication may prevent the control center from receiving important safety information.                     |
| **C9**        | An emergency condition must cause the system to enter a safe state and prevent unsafe road traffic movement.                                              | Emergency situations require the system to prioritize safety over normal operation.                                   |
| **C10**       | The system must not indicate that the crossing is safe for road traffic while a train is present or an unsafe condition exists.                           | A false safe indication could cause drivers to enter the crossing during a dangerous situation.                       |


