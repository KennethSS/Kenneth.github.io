---
layout: default
title: 병행성과 병렬성 차이
parent: OS
grand_parent: CS
permalink: /docs/cs/os/concurrency-and-parallelism/

---

# 병행성(Concurrency) 병렬성(Parallelism)의 차이

### 병행성([Concurrency](https://en.wikipedia.org/wiki/Concurrent_computing))

> 동시에 실행되는 것처럼 보이는 것.

- Logical Level에 속한다.
- Single Core
  - 물리적으로 병렬이 아닌 순차적으로 동작할 수 있다.
  - 실제로는 [Time-sharing](https://en.wikipedia.org/wiki/Time-sharing)으로 CPU를 나눠 사용함으로써 사용자가 Concurrency를 느낄 수 있도록 한다.
- Multi Core
  - 물리적으로 병렬로 동작할 수 있다.
- Case
  - Mutex, Deadlock

### 병렬성([Parallelism](https://en.wikipedia.org/wiki/Parallel_computing))

> 실제로 동시에 작업이 처리가 되는 것.

- Physical(Machine) Level에 속한다.
- 오직 Multi Core에서만 가능하다.
- Case
  - OpenMP, MPI, CUDA