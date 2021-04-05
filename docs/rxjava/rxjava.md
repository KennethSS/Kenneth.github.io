---
layout: default
title: RxJava
nav_order: 3
has_children: true
permalink: /docs/rxjava
---

# RxJava

To make it as easy as possible to write documentation in plain Markdown, most UI components are styled using default Markdown elements with few additional CSS classes needed.
{: .fs-6 .fw-300 }



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

