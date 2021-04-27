---

layout: default
title: 의존성 주입 패턴
parent: Design Pattern
has_children: true
nav_order: 4
---

## 의존성 주입(Dependency Injection)이란?

**의존성(Dependency)**이란 A클래스 내부에서 B클래스 인스턴스를 생성한다고 가정할 때 A클래스는 B에 의존한다고 할 수 있습니다. 

**의존성 주입(Dependency Injection)**이란 하나의 객체가 다른 객체의 의존성을 제공하는 기술입니다. 즉  외부에서 객체를 생성해서 주입하여 생성자나 메서드 등을 통해 전달받는 것 입니다.

## 의존성 주입은 왜 필요할까?

소프트웨어를 개발하다보면 여러 클래스에서 인스턴스 생성을 합니다. 이러한 과정은 객체간의 결합(Coupling)이 강해지는 구조를 가집니다. 이러한 문제는 코드의 복잡도가 늘어나며, 하나의 클래스 수정에도 많은 클래스에 변경점이 일어나고, 테스트하기 어려운 문제를 가집니다. 이러한 문제를 해결하기 위해 **변경의전이, 제어의 역전(IOC)**가 의존성 주입에 어떠한 의미와 해결책으로 다가오는지 알아보겠습니다.

### 변경의전이

하나의 클래스를 변경함으로 다른 의존 관계까지 변경사항이 전이된다.

```kotlin
class Computer {
  lateinit var IntelCPU cpu
  
  fun setCPU(cpu: InterCPU) {
    this.cpu = cpu
  }
}
```

만약 Computer가 InterCPU가 아닌 AmdCPU를 원한다면 Computer 클래스도 변경이 필요하다. 이를 해결할 방법은 CPU를 Interface로 만드는 것이다. 

``` kotlin
interface CPU { ... }
class InterCPU : CPU
class AmdCPU: CPU

class Computer {
  lateinit var CPU cpu // InterCPU or AmdCPU
  fun setCPU(cpu: CPU) {
    this.cpu = cpu
  }
}
```

### 제어의 역전(Inversion Of Control)

기존 Computer 클래스에서 객체를 생성하고 관리했지만 CPU의 객체의 생성 및 관리를 외부로 위임함으로써 의존관계가 역전이 되면서 방향이 역전되었다고 하며 이를 **IOC(Inversion Of Control)**라고 합니다.



## 장단점

### 의존성 주입의 장점

- 보일러 플레이트 코드 감소
- 테스트 용이
- 재사용성 향상
- 클래스간 결합도가 낮음
- 리팩토링 향상

### 단점은?

- 코드를 추적하고 읽기 어려워짐
- 작은 규모의 프로젝트에서는 비효율적일 수 있음
- 러닝커브도 존재(Dagger..)



## 마무리

의존성주입을 소프트웨어에 적용하기 위해서는(안드로이드 Dagger의 경우)높은 러닝커브와 초반 설계 기간이 필요하다는 단점이 있지만 장기적으로 볼 때 테스트하기 쉽고 리팩토링이 향상되어 결과적으로는 개발 기간을 더 단축시키는 이점이 있습니다. 이를 통해 조금더 클린하게 코드를 작성해 봅시다. 👍