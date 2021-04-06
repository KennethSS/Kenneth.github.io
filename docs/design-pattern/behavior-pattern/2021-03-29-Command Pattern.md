---
layout: default
title: Command 패턴
parent: 행위 패턴(Behavior)
grand_parent: Design Pattern
permalink: /docs/design-pattern/command-pattern/



---



## Command 패턴 이란?

**커맨드 패턴**(Command pattern)이란 요청을 객체의 형태로 [캡슐화](https://ko.wikipedia.org/wiki/캡슐화)하여 사용자가 보낸 요청을 나중에 이용할 수 있도록 매서드 이름, 매개변수 등 요청에 필요한 정보를 저장 또는 로깅, 취소할 수 있게 하는 패턴이다.

커맨드 패턴에 사용되는 4가지 주요 용어가 있다

- **명령(Command)**: 수신자의 정보 + 행동
- **수신사(Receiver)**: 행동을 하는 객체
- **발동자(Invoker)**: 커맨드를 저장하는 객체
- **클라이언트(Client)**: 커맨드 객체를 저장하고 발동하여 수신자에게 전달

안드로이드에서는 `Thread` 와 `Runnable` 이 대표적인 커맨드 패턴사례라고 볼 수 있다

## Command 패턴 사용해 보기

필자는 자동차를 좋아합니다. 뚜껑이 열리는 차를 부르는 방식이 각자 다른거 아시나요?

로드스터, 까브리올레, 컨버터블 등이 있습니다. 벤츠 모델은 까브리올레로 명칭하고 있고 포드 같은 미국 계열의 차는 컨버터블로 불리고 있습니다. 어떤 리모컨으로 자동차의 뚜껑을 열고 닫을 때 벤츠나 포드의 리모컨을 나누지 않고 하나의 리모컨으로 기능을 구현합니다. 예시는 다음과 같습니다.

- 자동차를 컨트롤하는 리모컨이 있음
- 차종에 관계 없이 차 뚜껑을 열고 닫을 수 있어야 함

위의 구현을 Command 패턴으로 구현해 보겠습니다.

먼저 뚜껑을 열고 닫는 Command Interface를 작성합니다.

```kotlin
interface Command {
    fun openRoof()
}
```

벤츠와 포드 자동차의 객체를 만듭니다. 두 자동차는 명칭과 동작하는 방식이 다르기 때문에 함수명이 다릅니다.

```kotlin
class BenzCar {
    fun openCabriolet() {
        println("Benz: Open Cabriolet")
    }
}
```

```kotlin
class FordCar {
    fun openConvertible() {
        println("Ford: Open Convertible")
    }
}
```

이제 Command를 Implement한 객체를 BenzCommand를 생성합니다.

```kotlin
class BenzCommand(
    private val benzCar: BenzCar
) : Command {
    override fun openRoof() {
        benzCar.openCabriolet()
    }
}
```

```kotlin
class FordCommand(
    private val fordCar: FordCar
) : Command {
    override fun openRoof() {
        fordCar.openConvertible()
    }
}
```

자 이제 실제로 만든 Command 패턴을 이용해 잘 동작되는지 확인해보겠습니다

```kotlin
class RemoteController(
    private var command: Command? = null
) {
    fun setCommand(command: Command) {
        this.command = command
    }

    fun openRoof() {
        command?.openRoof()
    }
}
```

Command를 이용해 차량을 컨트롤하는 `RemoteController` 클래스를 생성합니다.

테스트코드로 잘 동작되는지 확인해보겠습니다.

```kotlin
class CommandUnitTest {
    private val remote: RemoteController = RemoteController()

    @Test
    fun testBenzCar() {
        remote.setCommand(BenzCommand(BenzCar()))
        remote.openRoof()
    }

    @Test
    fun testFordCar() {
        remote.setCommand(FordCommand(FordCar()))
        remote.openRoof()
    }
}
```

RemoteContrller 인스턴스를 생성하고 리모컨에 할당할 차량의 커맨드 인스턴스를 할당해줍니다.
그리고 입력된 커맨드 인스턴스를 바탕으로 RemoteController의 open()을 실행해봅니다. 

```
Ford: Open Convertible
Benz: Open Cabriolet
```

각 차량에 맞게 함수가 호출되었습니다. 



앞서 말한 4가지 용어 중 각 해당 되는 클래스입니다.

- 명령(Command): Command
- 수신사(Receiver): BenzCommand, FordCommand
- 발동자(Invoker): RemoteController
- 클라이언트(Client): TestCode 



## 장단점

### 장점

- 시스템의 결합도를 낮춤
- 기존 코드를 수정하지 않고 새 커맨드를 이용하여 추가할 수 있음
- 명령 호출자와 수신자간의 의존성이 없음

### 단점

- 명령에 대한 클래스가 점점 늘어남



## 마무리

커맨드 패턴을 활용하여 큐(Queue)에 저장하여 execute() 만 실행하여 작업큐 관련 작업에 사용 할 수 있습니다. 



