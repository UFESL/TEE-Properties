# TEE-Properties

### Overview
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

