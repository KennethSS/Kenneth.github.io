---
layout: default
title: Android
nav_order: 4
has_children: true
permalink: /docs/android
---

# Overview

2011년에 안드로이드 생태계에 코틀린이 등장 한후 2017년 구글에서 공식 언어로 지정되고 난 후 안드로이드 개발자에게 코틀린은 필수적으로 다가 왔습니다. 

# 코루틴(Coroutine)이란?

### 사전적 정의

코루틴(Coroutine)은 [서브 루틴](https://kennethss.github.io/docs/cs/sub-routine/)을 일시 정지하고 재개할 수 있는 구성 요소입니다. 코루틴은 코틀린에 제한된 개념이아니라 C#, Javascript, 파이썬등 다양한 언어에서 지원하고 있는 개념입니다.   

~~필자는 5년전에 유니티 C#으로 처음 접함~~

결국 코루틴은 Context Switching 오버헤드가 적은 Non-Blocking 경량 스레드 라고 할 수 있습니다.

### 

## 안드로이드에서 코루틴

### 장점

- **경량**: 코루틴을 실행 중인 스레드를 차단하지 않는 [*정지*](https://kotlinlang.org/docs/reference/coroutines/basics.html)를 지원하므로 단일 스레드에서 많은 코루틴을 실행할 수 있습니다. 정지는 많은 동시 작업을 지원하면서도 차단보다 메모리를 절약합니다.
- **메모리 누수 감소**: [*구조화된 동시 실행*](https://kotlinlang.org/docs/reference/coroutines/basics.html#structured-concurrency)을 사용하여 범위 내에서 작업을 실행합니다.
- **기본으로 제공되는 취소 지원**: 실행 중인 코루틴 계층 구조를 통해 자동으로 [취소](https://kotlinlang.org/docs/reference/coroutines/cancellation-and-timeouts.html)가 전달됩니다.
- **Jetpack 통합**: 많은 Jetpack 라이브러리에 코루틴을 완전히 지원하는 [확장 프로그램](https://developer.android.com/kotlin/ktx?hl=ko)이 포함되어 있습니다. 일부 라이브러리는 구조화된 동시 실행에 사용할 수 있는 자체 [코루틴 범위](https://developer.android.com/topic/libraries/architecture/coroutines?hl=ko)도 제공합니다.

### 구성요소

- Job
- Dispatcher
- Scope


