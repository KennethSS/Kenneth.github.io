---
layout: default
title: Command 패턴
parent: 행위 패턴(Behavior Pattern)
grand_parent: Design Pattern
permalink: /docs/design-pattern/command-pattern/



---



## Command 패턴 이란?

**커맨드 패턴**(Command pattern)이란 요청을 객체의 형태로 [캡슐화](https://ko.wikipedia.org/wiki/캡슐화)하여 사용자가 보낸 요청을 나중에 이용할 수 있도록 매서드 이름, 매개변수 등 요청에 필요한 정보를 저장 또는 로깅, 취소할 수 있게 하는 패턴이다.

커맨드 패턴에 사용되는 4가지 주요 용어가 있다

- 명령(Command)
- 수신사(Receiver)
- 발동자(Invoker)
- 클라이언트(Client)

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
그리고 입력된 커맨드 인스턴스를 바탕으로 RemoteController의 openRoof(), closeRoof() 클래스를 실행해봅니다. 

```
Ford: Open Convertible
Ford: Close Convertible
Benz: Open Cabriolet
Benz: Close Cabriolet
```

각 차량에 맞게 함수가 호출되었습니다. 





Subject(이벤트를 발생 시키는 주체)에서 Register, UnRegister를 통해 
옵저버를 추가 및 삭제하여 리스트를 관리합니다.
그리고 어떤 이벤트에 발생함에 따라 Subject에서 notifyObservers()를 통해 구독 혹은 옵저빙 중인 객체들에게 이벤트를 발생 및 전달합니다

![img](https://cdn-images-1.medium.com/max/800/0*uH6_TpuqD5Uccpld.png)by wikipedia

한번에 이해가 어려울 수도 있습니다. 저도 그랬어요 ^^
예시를 보면서 익혀봅시다

### 예시

먼저 객체를 구독해줄 구독자들 부터 만들어 봅시다

<script src="https://gist.github.com/KennethSS/8c5a27084877025c0f563ae1eeff576d.js"></script>

<script src="https://gist.github.com/KennethSS/dcd69550ecf254f7ca19fe484bd12a06.js"></script>



Fragment를 구독자로 예시를 들어 구현해보았습니다.
구독자를 구현했으니 구독자에게 이벤트를 전달할 
Subject를 만들어보겠습니다.

<script src="https://gist.github.com/KennethSS/8d66353718f72e1ff8e5975fd5f7e80d.js"></script>

<script src="https://gist.github.com/KennethSS/de0b04b8c750691c2680645b50e313a0.js"></script>



Observable이라는 Interface를 구현하여
옵저버등록, 옵저버삭제, 옵저버 이벤트 발생 3가지를 만들었습니다
편의상 이해하기 쉽게 이벤트 발생 주체는 Youtuber로 만들었습니다

옵저버를 등록하고 이벤트를 발생시키는 조건은 아래와 같습니다.

```
val youtuber = Youtuber()
val observer = SampleFragment()
youtuber.registerObserver(observer)
youtuber.notifyObserversNewVideo(resource)
```

해당 이벤트를 발생하면

```
override fun newVideo(imageRes: Int) {

}
```

newVideo 함수로 이벤트가 콜백됩니다.

Observer 패턴은 RxJava의 기반이되는 패턴이기도 합니다.

Rxjava의 대한 내용은 추후 다뤄보도록 하겠습니다. 감사합니다 :)

Android Sample 코드를 Github에 올려두었습니다.
참고하시면 더 이해가 쉬울겁니다 :)