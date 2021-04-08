---
layout: default
title: Context 란 무엇일까?
parent: Component
grand_parent: Android
permalink: /docs/android/component/context/

---

## Context 란 무엇일까?

Application, Activity, Service 3가지 모두 Context를 상속 받고 있습니다.   
Context를 사용하면 startActivity(), startService(), getResource(), getSystemService(), getTheme(), getAssets()등 시스템의 정보를 얻을 수 있는 메소드를 가지고 있습니다. 

Context는 크게 2가지로 분류할 수 있습니다

- ApplicationContext
- ActivityContext



## ApplicationContext

`Application Context`는 어플리케이션과 관련되어 있고 어플리케이션이 살아 있는동안 유지되며 싱글톤이라고 할 수 있습니다. Activity Scope에 제한에서 벗어나 활용하고 싶다면 `Application Context`를 사용하면 됩니다. Context가 필요한 특정 싱글톤 객체를 만들 때 유용합니다.







