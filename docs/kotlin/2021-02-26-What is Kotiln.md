---
layout: default
title: Kotlin 이란?
parent: Kotlin
nav_order: 2


---



### Kotlin

Kotlin은 Java를 대체하기 위한 목적으로 2011년에 JetBrains에서 만들었습니다



### 왜 코틀린이 나왔을까요?

Kotlin은 기존 자바의 약점(보일러 플레이트 코드등)을 개선 가능함과 동시에
JVM과 호환이 가능하며 웹, 앱 개발도 가능하며 KMM(Kotlin MultiPlatform Mobile)을 이용해 
다른 언어 개발도 지원이 되는 언어입니다.



### 어떤 장점이 있길래? 그냥 Java 쓰면 안되나요?

Kotlin은 Java를 완벽히 대체 가능하면서 여러 장점을 추가적으로 가지고 있습니다.

- Kotlin은 코드가 간결하다(Java의 보일러 플레이트 구문을 최소화)
- 람다식 사용 가능(Retrolambda 라이브러리를 사용 않고)
- 직관적인 Null Check 명시에 의한 Null Safty
- 변경이 불가능한(Immutable), 변경이 가능한(Mutable) 변수 타입 지원

더 나아가 Kotlin 만의 추가 장점이라고 생각되는 부분입니다.

- object class를 이용한 싱글톤 객체 생성
- 고차 함수 지원(filter, map, forEach)
- 정적 타입 지정 언어
- 함수형 프로그래밍
- getter/setter 묵시적 제공
- 지연 초기화
- KMM(Kotlin MultiPlatform Mobile) 지원
- expression (when, sealed)

이 밖에도 셀 수 없을 정도로 장점이 많은 언어입니다. 이 많은 장점을 두고 Java를 쓰실건가요?

{: .mb-lg-32 }

### 성능차이?

Java vs Kotlin를 컴파일 성능을 비교한 [자료](https://medium.com/@johnkorly/kotlin-vs-java-performance-drill-down-which-to-choose-2514bdf91916)가 있습니다

성능면에서 Kotlin이 빠르니 걱정하지말고 사용하는게 좋습니다.

***

### 마무리

- Java를 어느정도 익히고 Kotlin을 사용하자
- 성능도 Kotlin 우위!
- Kotlin을 Java로 Decompile해서 동작 원리를 파악해 볼. 것
