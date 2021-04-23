---
layout: default
title: Clean Architecture
nav_order: 8
has_children: true
permalink: /docs/clean-architecture
---

## 클린 아키텍처란?



## 아키텍처의 목적

- 프레임워크로 부터 독립적

- 비지니스 룰을 UI, DB, 웹 서버등 외부 요인 없이 테스트 가능

- UI와 무관하게 비지니스 룰 변경 가능

- 데이터베이스에 독립적

  무관 오라클, SQL, Mongo 

- 외부 기관과 독립적입니다. 실제로 비즈니스 규칙은 외부 세계에 대해 전혀 알지 못합니다.

  

  

  이러한 아키텍처를 하나의 실행 가능한 아이디어로 통합하려는 시도로 존재한게 바로 클린 아키텍처



### 프레임워크와 드라이버

- UI
- 데이터베이스
- 네트워크
- 라이브러리 및 프레임워크