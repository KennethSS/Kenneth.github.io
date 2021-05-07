---
layout: default
title: Vector와 ArrayList 차이
parent: Java
nav_order: 2


---



## Vector와 ArrayList 차이



### Vector의 특징

현재 `Collection` 프레임워크에 포함되어 있지만 초기 자바에서는 인터페이스로 정의 되어 있었습니다. 

- 필요에 따라 크기를 동적으로 조절 가능
- 배열과 같이 Index에 접근 및 제어 가능
- 동기화(Thread Safe)가 되어 있음



### ArrayList의 특징

`Collection` 프레임워크에 포함되어 있는 자료구조입니다.

- 크기를 동적으로 바꿀 수 있는 동적 배열
- 배열에서의 조작이 많을 때 유용합니다(특히 Index를 통한 접근)
- 타입 객체를 참조해서 사용



### 그럼 본격적으로 차이는?

가장 중요한 차이점은 **동기화 유무** 입니다. Vector의 구조를 보면 `element` 접근에 관한 함수들은 synchronized 처리가 되어있습니다. 즉 여러 스레드에 접근에도 Thread Safe(스레드 안전)한 특징을 가지고 있습니다.

- **성능:** ArrayList 동기화를 지원하는 Vector 보다 좋은 성능을 가지고 있습니다.
- **스레드 세이프:** Vector는 동기화를 지원하므로 ArrayList에 비해 멀티 스레드에 안전합니다.
- **배열의 길이 증가:** 초기 할당한 배열의 최대길이에 도달했을 때 ArrayList는 50%씩 증가하는 반면 Vector는 2배씩 크기가 증가합니다.



### 그럼 무엇을 써야하나?

Vector는 Java초기에 만들어서 초기 버전의 호환성이 아니라면 많이 쓰지 않습니다. ArrayList를 사용하되 멀티 스레드에 대해 적절한 처리를 해서 사용해 주시면 됩니다.