---

layout: default
title: 연산자(Operator)
parent: RxJava
has_children: true
nav_order: 1
---

## 소개(Introduction)

ReactiveX에서 언어 별 연산자를 구현하고. 특정 언어에서만 존재하는 일부 연산자도 존재하지만 대체적으로 컨텍스트에서 익숙하고 유사한 메서드나 연산자의 이름을 지정합니다.

### Chaining Operators

체이닝 연산자들은 `Observable` 에서 작동하고 `Observable`을 반환합니다. 메서드 체이닝 기법을 통해 연산자를 차례대로 선언하고 순차적으로 작동합니다. 따라서 `Observable` 연산자는 바로 이전에 생성한 `Observable` 혹은 `Observable` 연산자의 결과를 바탕으로 `Observable`을 수정합니다.

체이닝 연산자 기법은 마치 빌더 패턴과 비슷하지만 빌더 패턴은 메서드 체인의 순서가 중요하지 않은 반면 체이닝 연산자는 Observable 연산자 순서에 중요성하다는 점에서 차이가 있습니다. 

### Operators

연산자의 카테고리 리스트입니다.

- Creating
- Transforming
- Filtering
- Combining
- Error Handling
- Observable Utility
- Conditional And Boolean
- Mathmatical
- Backpressure
- Connectable
- Convert

