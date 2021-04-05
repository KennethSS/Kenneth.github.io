---
layout: default
title: 데이터 바인딩 사용시 에러
parent: Component
grand_parent: Android
permalink: /docs/android/component/context/

---

## Context 란 무엇일까?

Application, Activity, Service 3가지 모두 Context를 상속 받고 있습니다.   
Context를 사용하면 startActivity(), startService(), getResource(), getSystemService(), getTheme(), getAssets()등 시스템의 정보를 얻을 수 있는 메소드를 가지고 있습니다. 

## Context의 종류와 올바른 사용 방법

Context는 크게 2가지로 분류할 수 있습니다

- ApplicationContext
- ActivityContext



## ApplicationContext

`Application Context`는 어플리케이션과 관련되어 있고 어플리케이션이 종료되지 않는한 변경되지 않는 싱글톤이며 getApplication()



