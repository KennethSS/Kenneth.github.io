---
layout: default
title: Kotlin으로 람다 함수와  고차 함수란
parent: Kotlin
nav_order: 2

---



## Kotlin으로 람다 함수(Lambda Function)와  고차 함수(High Order Function)에 대해서 알아보자



### Lambda Function(람다 함수) 이란?

람다 함수는 함수형 프로그래밍 언어에서 사용되는 개념으로 **익명 함수**라고도 불린다
Java8 부터 사용이 가능하며, 가독성을 향상시키고 보일러 플레이트 코드를 줄일 수 있다

### Lambda Function(람다 함수) 의 사용 방법

**기본 사용 방법**

```kotlin
val lambdaName : Type = { argumentList -> codeBody }
```

**Type Interface를 활용하는 방법**

```kotlin
val square = { number: Int -> number * number }
val nine = square(3)
```





```kotlin
val lambdaName = { a: Int, b: String -> 
	"$a $b"
}
```

1개 이상의 타입을 파라미터로 전달 가능하고 리턴 타입을 생략 할 수 있습니다

---

### High Order Function(고차 함수) 란?

함수를 인수로 취하거나 함수를 결과로 반환할 수 있는 함수를 말합니다

아래 사용되고 있는 예시를 보겠습니다.

```kotlin
fun square(x: Int, y: Int, block: (result: Int) -> Unit) {
        block(x * y)
}

square(4, 4) { result ->
	// result 16
}
```

- x, y를 인자를 받고 해당 block이라는 람다식을 invoke 합니다.
- 선언된 square 함수에서 block 파라미터의 블록에서 결과값을 받을 수 있습니다



고차 함수로 람다함수를 파라미터로 넘겨줄 때 과도하게 사용하면 런타임 오버헤드가 발생합니다.
그럴때는 inline 키워드를 사용하여 오버헤드를 방지해야 합니다.

[Medium 글](https://kennethss.medium.com/kotlin-%EA%B3%A0%EC%B0%A8%ED%95%A8%EC%88%98%EC%99%80-inline-noinline-crossinline-reified-960f1f1511c2)

Medium 설명글에 inline에 대해서 작성한 글이 있습니다. 참고해 보시길 바랍니다.