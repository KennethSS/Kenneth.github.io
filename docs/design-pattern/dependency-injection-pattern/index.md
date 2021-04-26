---

layout: default
title: 의존성 주입 패턴
parent: Design Pattern
has_children: true
nav_order: 4
---

### 의존성 주입(Dependency Injection)이란?

**의존성(Dependency)**이란 A클래스 내부에서 B클래스 인스턴스를 생성한다고 가정할 때 A클래스는 B에 의존한다고 할 수 있습니다. 

**의존성 주입(Dependency Injection)**이란 하나의 객체가 다른 객체의 의존성을 제공하는 기술입니다. 즉  외부에서 객체를 생성해서 주입하여 생성자나 메서드 등을 통해 전달받는 것 입니다.



### 의존성 주입은 왜 필요할까?

#### 변경의전이

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



#### 제어의 역전(Inversion Of Control)

기존 Computer 클래스에서 객체를 생성하고 관리했지만 CPU의 객체의 생성 및 관리를 외부로 위임함으로써 의존관계가 역전이 되면서 방향이 역전되었다고 하며 이를 **IOC(Inversion Of Control)**라고 합니다.



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

  



