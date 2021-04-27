---
layout: default
title: RxJava
nav_order: 5
has_children: true
permalink: /docs/rxjava
---



## RxJava가 무엇일까?

반응형 프로그래밍(Reactive Programming) 패러다임을 Java에서 구현한 프로그래밍 라이브러리입니다. RxJava는 옵저버 패턴(Observer Pattern)을 확장하여 데이터 및 이벤트의 시퀀스를 지원하고 낮은 수준의 스레딩, 동기화, 스레드 세이프등 동시 데이터구조의 문제를 추상적으로 해결할 수 있는 연산자를 제공합니다.

### 반응형 프로그래밍(Reactive Programming) 이란?

데이터 스트림과 변경사항에 대한 전파(Propagation)를 중심의 선언적 프로그래밍 패러다임입니다. 즉 데이터를 관찰하고 데이터가 변경되면 해당 이벤트를 처리하는 프로그래밍을 의미합니다.





- Observable
- Operators
- Single
- Subject
- Scheduler







|      head1      | head two                                                     |
| :-------------: | :----------------------------------------------------------- |
|      map()      | 데이터 변환                                                  |
|   concatMap()   | 인터리빙(끼어들기)를 방지하고 들어온 데이터들 순서대로 Map function 수행 |
|   switchMap()   | 들어온 데이터를 concatMap처럼 처리하나 처리가 완료되기 이전 신규 input이 들어오면 이전 input의 처리 중단 이후 신규 input 처리 진행 |
|    groupBy()    | 들어오는 데이터를 형식에 따라 묶어 별도의 Observable로 반환  |
|     cast()      | 클래스 타입으로 변경                                         |
| startWithItem() | 시작하는 아이템을 변경                                       |
|    sorted()     | 오름차순으로 변경                                            |
|                 |                                                              |

### 변환 연산자

```markdown
| 함수 이름      | 설명								|
|:-------------|:------------------|
| map() 			 		| 데이터 변환 |
| concatMap() 		| 인터리빙(끼어들기)를 방지하고 들어온 데이터들 순서대로 Map function 수행  |
| switchMap()     | 들어온 데이터를 concatMap처럼 처리하나 처리가 완료되기 이전 신규 input이 들어오면 이전 input의 처리 중단 이후 신규 input 처리 진행 |
| scan()        	| 들어오는 데이터를 형식에 따라 묶어 별도의 Observable로 반환 |
| groupBy()       | 들어오는 데이터를 형식에 따라 묶어 별도의 Observable로 반환 |
| cast()        	| 클래스 타입으로 변경 |
| startWithItem() | 시작하는 아이템을 변경 |
| sorted()        | 오름차순으로 변경 |
```

