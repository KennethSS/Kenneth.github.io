---
date: 2021-03-08T13:46:05.000Z
layout: post
title: Kotlin Sealed Class란?
subtitle: Kotlin Sealed Class에 대해서 설명합니다.
description: >-
  Kotlin Sealed Class에 대해서 설명합니다.
image: >-
  /assets/img/uploads/kotlin.jpg
optimized_image: >-
 /assets/img/uploads/kotlin.jpg
category: kotlin
tags:
  - kotiln
author: KennethSS
paginate: true



---

### Sealed Class란 무엇일까?

sealed class는 상속을 받는 Child 클래스에 대해서 제한된 클래스 계층을 가지고 있는 클래스입니다. 상속을 받는 하위 클래스는 여러 파일에 해당 될 수 있기 때문에 컴파일러는 얼마나 많은 하위 클래스를 포함하고 있는지 모릅니다. sealed class는 해당 모듈 컴파일타임에 정의된 하위 클래스만외에 다른 하위 클래스는 존재 하지 않는다는 것을 알려줍니다.

어떤 의미에서는, 봉인된 클래스는 열거형 클래스와 유사하다. 즉, 열거형의 값 집합도 제한되지만, 각 열거형 상수는 하나의 인스턴스로만 존재하는 반면, 봉인된 클래스의 하위 클래스는 각각 고유한 상태를 가진 여러 인스턴스를 가질 수 있다.



### Sealed Class 사용 방법

``` kotlin
sealed class Expr
data class Const(val number: Double) : Expr()
data class Sum(val e1: Expr, val e2: Expr) : Expr()
object NotANumber : Expr()
```

클래스 앞에 sealed의 키워드를 붙여서 사용합니다. 그리고 하위 클래스가 이 클래스를 상속하도록 선언합니다.



>  kotiln 가이드에서는 변수를 포함하고 있지 않은 객체는 object로 선언하길 권고하고있습니다



### Sealed Class 의 특징

- when expression 사용시 else 절 구현이 필요 없음
- 객체로 생성 불가능
- 생성자는 private로 public으로 설정 불가능
- sealed class와 하위 클래스는 동일한 파일에 선언
- 하위 클래스는 `class`, `data class`, `object class` 로 정의 가능



