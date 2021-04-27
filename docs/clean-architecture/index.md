---
layout: default
title: Clean Architecture
nav_order: 8
has_children: true
permalink: /docs/clean-architecture
---

## 클린 아키텍처란?

![clean-architecture](https://blog.cleancoder.com/uncle-bob/images/2012-08-13-the-clean-architecture/CleanArchitecture.jpg)

클린 아키텍처의 특징

- 경계선(Boundaries)
- 유스케이스(UseCase)
- 험블 객체
- 의존성 역전 DIP



## 아키텍처의 목적

- 프레임워크로 부터 독립적
  라이브러리 혹은 프레임워크에 한정적이지 않아 어떠한 도구로 사용하는 것이 가능합니다.
- 테스트 용이
  Business Rule은 UI, DB, Web Server 등 외부 요인과 관계없이 테스트 가능합니다.
- UI에 독립적
  시스템의 다른 부분을 고려하지 않고 UI 변경이 가능합니다.
- 데이터베이스에 독립적
  DB를 독립적으로 변경 가능합니다.(SQL, Mongo, Oracle 등)
- 외부 기능과 독립적
  Business Rule은 외부 상황(Database, UI, WebServer)에 대해 전혀 알지 못합니다. 

이러한 아키텍처를 하나의 실행 가능한 아이디어로 통합하려는 시도로 존재한게 바로 클린 아키텍처

### 클린아키텍처

가장 가운데는 고수준 가장 바깥은 저수준 저수준에서 고수준 방향으로 의존



### 프레임워크와 드라이버(Frameworks & Drivers)

- UI
- 데이터베이스
- 네트워크
- 라이브러리 및 프레임워크

### 인터페이스 어댑터(Interface Adapters)

유스케이스와 엔티티에 있어 용이한 형식으로부터 데이터베이스나 웹 등 외부의 기능에 용이한 형식으로 데이터를 변환한다. 

> **인터페이스 어댑터 레이어의 뷰**
>
> 엉클 밥은 이 레이어에서 View 를 고려했지만 개인적으로는 이런 부분이 이해가 되지 않아요. View 는 가장 바깥 레이어에 두는게 나을 것 같다는 생각이에요. 하지만 만약 우리가 View 인터페이스에 대해서 얘기하고 있다면 인터페이스 어댑터에 정의될 수 있겠죠.

> 엉클 밥은 인터페이스 어댑터에 Presenter, View, Controller 가 모두 포함된다고 The Clean Architecture 책에도 명시를 했다. 클린 아키텍처 레이어 구조를 보면 인터페이스 어댑터의 밖에 UI 레이어가 존재하게 그려져있다. 나름 해석해 보자면 여기에 보여지는 UI 레이어는 프레임워크이고, 인터페이스 어댑터는 이 프레임워크를 기반으로 직접 만든 코드(Presenter, View, Contgroller 모두 직접 만든 것들)에 해당하기 때문에 이 레이어에 두는 것이 아닐까? 실제 UI 프레임워와 도메인 영역을 연결하는 역할을 한다는 의미로. 맞는지 아닌지 모르겠지만 … 난 그냥 이렇게 이해할래요. ㅎ



### Use Cases(Application Business Rule)

로그인하기, 업무처리하기, 포스팅하기, 사진업로드하기와 같이 동사로 표현되는 비지니스 로직을 말한다. Use cases는 Entity에 의존하는 동시에 상호작용한다.



### Entities(Enterprise Business Rules)

Entity는 비즈니스 로직을 캡슐화한 것으로 가장 일반적이면서도 고수준의 규칙을 캡슐화한 모듈이다.



### 의존성 규칙 (Dependency Rule)

**"모든 소스코드 의존성은 반드시 outer에서 inner로, 고수준 정책을 향해야 한다."**

### 의존 관계 역전의 원칙(Dependency Inversion Priciple)

하지만 고수준(Use cases)이 저수준(Presenter)을 참조하는 경우가 있는데 이런경우에는 `의존 관계 역전의 원칙(Dependency Inversion Priciple)`에 의해 해결될 수 있다.

Use case는 Output port라는 인터페이스를 둔다. 그리고 Presenter는 이 Output port 인터페이스를 구현한다. 직접 Presenter는 Use case에 직접 접근하는 것이 아니라 Output port라는 `인터페이스`를 통해 접근하는 것이다.
이를 통해 고수준(Use cases)은 저수준(Presenter)의 세부사항을 알 필요 없고 변동사항에도 영향을 받지 않게 된다.



### 클린 아키텍처 질문

- 꼭 4개의 레이어를 사용해야 하는가? -> No
- UseCase 사용이유
- 



#### 참고

- [The Clean Code Blog - Robert C. Martin(Uncle Bob)][https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html]
- 

