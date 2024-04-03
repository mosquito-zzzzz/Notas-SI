---
share: true
---
**Speculative execution** is an optimization technique where a computer system performs some task that may not be needed. Work is done before it is known whether it is actually needed, so as to prevent a delay that would have to be incurred by doing the work after it is known that it is needed. If it turns out the work was not needed after all, most changes made by the work are reverted and the results are ignored.

The objective is to provide more concurrency if extra resources are available. This approach is employed in a variety of areas, including branch prediction in pipelined processors, value prediction for exploiting value locality, prefetching memory and files, and optimistic concurrency control in database systems.

---

## Summary 

Modern pipelined microprocessors use speculative execution to reduce the cost of conditional branch instructions using schemes that predict the execution path of a program based on the history of branch executions. To improve performance and utilization of computer resources, instructions can be scheduled at a time when it has not yet been determined that the instructions will need to be executed, ahead of a branch.

---

## Variants

#### Eager execution

See also: [Eager evaluation](https://en.wikipedia.org/wiki/Eager_evaluation "Eager evaluation")

Eager execution is a form of speculative execution where both sides of the conditional branch are executed; however, the results are committed only if the predicate is true. With unlimited resources, eager execution (also known as _oracle execution_) would in theory provide the same performance as perfect branch prediction. With limited resources, eager execution should be employed carefully, since the number of resources needed grows exponentially with each level of branch executed eagerly.

#### Predictive execution

See also: [Pipeline (computing)](https://en.wikipedia.org/wiki/Pipeline_(computing) "Pipeline (computing)")

Main article: [Branch predictor](https://en.wikipedia.org/wiki/Branch_predictor "Branch predictor")

Predictive execution is a form of speculative execution where some outcome is predicted and execution proceeds along the predicted path until the actual result is known. If the prediction is true, the predicted execution is allowed to commit; however, if there is a misprediction, execution has to be unrolled and re-executed. Common forms of this include branch predictors and memory dependence prediction. A generalized form is sometimes referred to as value prediction.

#### Runahead

This paragraph is an excerpt from [Runahead](https://en.wikipedia.org/wiki/Runahead "Runahead").

Runahead is a technique that allows a computer processor to speculatively pre-process instructions during cache miss cycles. The pre-processed instructions are used to generate instruction and data stream prefetches by executing instructions leading to cache misses (typically called _long latency loads_) before they would normally occur, effectively hiding memory latency. In runahead, the processor uses the idle execution resources to calculate instruction and data stream addresses using the available information that is independent of a cache miss. Once the processor has resolved the initial cache miss, all runahead results are discarded, and the processor resumes execution as normal. The primary use case of the technique is to mitigate the effects of the memory wall. The technique may also be used for other purposes, such as pre-computing branch outcomes to achieve highly accurate branch prediction.

---

## Security vulnerabilities 

Starting in 2017, a series of security vulnerabilities were found in the implementations of speculative execution on common processor architectures which effectively enabled an elevation of privileges.

- Foreshadow
- Meltdown
- Microarchitectural Data Sampling
- [[Spectre|Spectre]]
- SPOILER
- Pacman