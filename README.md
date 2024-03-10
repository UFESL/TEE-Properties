# TEE-Properties
TEE-Properties provides an executable of template based property generation for Trusted Execution Environments.  Our proposed approach generate properties to verify TEE implementations. The first step extracts the local FSMs related to security protocols based on TEE  specifications. The second step composes a global FSM by identifying the external relations within local FSMs. The third step generates properties using the global FSM and the property templates.

This is developed at [Embedded Systems Lab, Department of Computer Science, University of Florida](https://www.cise.ufl.edu/research/cad), as a deliverable for a [SRC](https://www.src.org/) project.

## Overview
<img src="overview_date24.pdf"
     alt="Overview of template based property generation for TEE architecture"
     style="float: center; margin-right: 10px;" 
     align="center"/>

## Templates for Different Types of Properties

| Property    | Template                                                        | Explanation                                                                                      |
|-------------|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| Safety      | `G (q1 -> X (! (q2 U i1)))`                                 | In state `q1`, input `i1` should never lead to state `q2`.                                   |
| Liveness    | `G ((q1 & i1) -> F q2)`                                     | In state `q1`, input `i1` should eventually lead to state `q2`.                              |
| Concurrency | `G ((q1 & q2 & ... & qn) -> o1)`                            | Concurrent execution of states `q1, q2, ..., qn` should result in output `o1`.               |

## Setup
To run:
```
./property_generation <fsm_file>
./property_generation fsm.json
```
## Environment
-Python
-Ubuntu/Linux

## Input
Provide the FSM similar to the global FSM provided in [fsm.json](fsm.json)

<img src="globalfsm1.pdf"
     alt="Sample global FSM in fsm.json file"
     style="float: center; margin-right: 10px;" 
     align="center"/>
## Output
Set of properties for Saftey, Liveness and Concurrency. This is created as [property.txt](property.txt)
