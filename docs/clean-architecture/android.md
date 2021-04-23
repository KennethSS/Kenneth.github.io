---
layout: default
title: MVVM 패턴이란?
parent: Clean Architecture
grand_parent: Clean Architecture
permalink: /docs/clean-architecture/android/



---

## 시작하기 전에

최근 많은 분들이 MVVM 패턴에 대해 많이 관심을 가지고 사용하려고 합니다. 하지만 이제 개발을 막 시작하시는 분들이 MVVM 패턴을 접근할 때 단점이 없는 좋은 패턴(?)으로 생각하시는 분들도 있습니다. 그래서 MVVM 패턴이란 어떤 장점과 단점이 있고 어떤 구조를 가지고 있는지 기록하려고 합니다.

## MVVM 패턴이란?

MVVM패턴은 View-ViewModel-Model 단위로 분리하여 각 단위간의 의존성을 줄이고 구성된 아키텍처 패턴이다. [Command](https://kennethss.github.io/docs/design-pattern/command-pattern/)패턴과 Data Binding 패턴을 사용해서 View와 ViewModel 사이의 의존성을 낮추고 비즈니스 로직과 프레젠테이션 로직을 UI로 분리하는 것에 목적을 두고 있습니다.



### 구성요소

MVVM 패턴은 3가지 단위로 구성되어 있습니다.

- **모델 (Model)**: 응용 프로그램의 데이터를 캡슐화 하는 비시각적 클래스
- **뷰 (View)**: 사용자와 상호작용하는 UI 인터페이스, 비즈니스 로직을 포함하지 않음
- **뷰모델 (ViewModel)**: View가 사용할 메서드 혹은 필드를 구현하고 View에게 상태 변화를 알림

![mvvm](/assets/images/mvvm.png)



### View

View는 비즈니스 로직을 포함하지 않고 오직 UI 관련된 로직만 가지고 있어야합니다. View는 ViewModel을 관찰하고 있다가 ViewModel의 상태가 변경되면 조건에 맞게 화면을 갱신합니다.

### ViewModel



## 장단점

### 장점

- 개발자와 디자이너간 쉽게 공동 작업이 가능
- Model, View, ViewModel 각 부분이 독립적
- 중복 코드를 모듈화 가능
- 테스트가 용이

### 단점

- 잘못된 설계는 오히려 보일러플레이트 코드를 생성
- 작은 규모의 프로젝트에는 오버헤드 발생 가능



## 마무리

MVVM 아키텍처 패턴이 어디에도 사용하고 무조건 좋은 패턴이라고 할 수 없습니다. 개발 조건, 규모, 상황에 맞게 적절한 아키텍처를 사용해야 합니다. 



### 참고

- [MicroSoft](https://docs.microsoft.com/ko-kr/xamarin/xamarin-forms/enterprise-application-patterns/mvvm)
- [CodeProject](https://www.codeproject.com/Articles/221585/Step-By-Step-Guide-To-MVVM)

