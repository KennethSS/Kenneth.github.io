---
layout: default
title: 서비스 로케이터 패턴
parent: Architecture Pattern
grand_parent: CS
permalink: /docs/cs/architecture-pattern/service-locator/



---

## 서비스 로케이터 패턴이란?

서비스 로케이터 패턴은 강력한 추상화 계층으로 어떤 서비스를 얻는 데 관련된 프로세스를 캡슐화를 위한 디자인 패턴입니다. 

이 패턴은 "서비스 로케이터"로 알려진 중앙 레지스트리를 사용하며, 요청시 특정 작업을 수행하는 데 필요한 정보를 반환합니다. 이

 패턴을지지하는 사람들은이 접근 방식이 전체 애플리케이션 설계의 시작 부분에 모든 종속성이 명확하게 나열되는 구성 요소 기반 애플리케이션을 단순화하여 결과적으로 기존 종속성 주입을보다 복잡한 개체 연결 방식으로 만든다고 말합니다. 패턴에 대한 비평가들은 이것이 의존성을 모호하게 만들고 소프트웨어를 테스트하기 어렵게 만드는 안티 패턴이라고 주장합니다.

### 참고

- [WikiPedia](https://en.wikipedia.org/wiki/Service_locator_pattern)

