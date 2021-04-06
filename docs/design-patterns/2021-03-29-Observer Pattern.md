---
layout: default
title: Observer 패턴
parent: Design Pattern
grand_parent: CS
permalink: /docs/design-pattern/observer-pattern/



---



## 옵저버 패턴 이란?

객체의 상태 변화를 관찰하는 관찰자들(옵저버)의 목록을 객체에 등록하여 상태 변화가 발생하면 등록된 목록의 관찰자(옵저버)들에게 통지하도록 하는 디자인 패턴이다.

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