---
layout: default
title: MVP 패턴
parent: Architecture Pattern
grand_parent: CS
permalink: /docs/cs/architecture-pattern/mvp/



---

## MVP 패턴이란?

MVP패턴은 View의 비즈니스 로직을 분리하고 서로간의 상호작용을 Presenter에 의해 서로의 의존성을 최소화 할 수 있는 패턴입니다. 

- MVP는 자동화 된 단위 테스트를 용이하게하고 프리젠 테이션 로직에서 문제의 분리를 개선하도록 설계된 사용자 인터페이스 아키텍처 패턴입니다.





### 구성요소

![MVP](https://upload.wikimedia.org/wikipedia/commons/d/dc/Model_View_Presenter_GUI_Design_Pattern.png)

MVP 패턴은 3가지 단위로 구성되어 있습니다.

- **모델 (Model)**: 응용 프로그램의 데이터를 캡슐화 하는 비시각적 클래스
- **뷰 (View)**: 사용자와 상호작용하는 UI 인터페이스, 비즈니스 로직을 포함하지 않음
- **프레젠터 (Presenter)**: View가 사용할 메서드 혹은 필드를 구현하고 View에게 상태 변화를 알림



### View

### Model

### Presenter



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

- [Wiki](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter)