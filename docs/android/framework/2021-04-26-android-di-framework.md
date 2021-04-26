---
layout: default
title: 안드로이드에서 DI 프레임워크
parent: Framework
grand_parent: Android
permalink: /docs/android/framework/di/

---

## 안드로이드에서 DI 프레임워크



안드로이드 DI 프레임워크 라이브러리에는 크게 3가지가 있다

- Dagger
- Koin
- Hilt



Hilt는 Dagger를 기반으로 안드로이드에서 공식적으로 발표한 DI 라이브러리다.

Dagger는 Square사에서 만든 라이브러리로 역사적으로 가장 오래되었다

Koin은 Arnaud Giuliani의해 만들어졌으며 kotlin 도입 후 주목을 많이 끌었다





### Dagger와 Koin의 차이

- Dagger는 컴파일시 Annotation을 처리하는 과정에서 오버헤드가 발생하지만 에러가 발생하지 않고 주입이 가능합니다.
- Koin은 런타임 과정에서 DI를 주입합니다. 컴파일 과정에 오버헤드가 없는 반면 런타임중 Crash가 발생할 확률이 있습니다. 또한 Kotlin은 DSL 형태에 의존하기 때문에 순수한 코틀린 코드로 되어있습니다.



### 성능이슈?

2개의 성능은 크게 다를게 없습니다.

