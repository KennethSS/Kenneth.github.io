---

layout: default
title: Context Switching
parent: OS
grand_parent: CS
permalink: /docs/cs/os/context-switching/

---

# 컨텍스트 스위칭(Context Switching)

**컨텍스트 스위칭(Context Switching)**이란? CPU가 어떤 프로세스를 실행하고 있는 상태일 때 인터럽트에 의해 그 다음 우선 순위를 가진 프로세스를 실행해야 할 때 기존의 프로세스의 정보는 PCB(Process Control Block)에 저장하고 다음 프로세스의 정보를 PCB에서 가져와 교체하는 작업이라한다.

### 컨텍스트 스위칭의 단점

A의 프로세스의 상태를 저장하고 B의 프로세스 상태를 가져올 때 CPU는 아무런 일도 하지 못한다. 따라서 컨텍스트 스위칭이 잦으면 오버헤드가 발생할 가능성이 높아 성능이 떨어진다.



컨텍스트 스위칭의 대표적인 인터렙트는 다음과 같다

- 입출력 요청 시 (I/O Interrupt)
- CPU 사용시간 만료(time slice exired)
- 자식 프로세스를 만들 때(fork a child)
- 인터럽트 처리를 대기할 때(wait for an interrupt)



