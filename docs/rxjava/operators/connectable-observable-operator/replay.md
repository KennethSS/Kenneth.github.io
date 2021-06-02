---
layout: default
title: Distinct
parent: 필터 연산자
grand_parent: RxJava
permalink: /docs/rxjava/filtering-operator/distinct/

---

## Distinct

Observable에서 발행된 중복 아이템을 제어하는 함수입니다.

### distinct()

![distinct](/assets/images/distinct.png)

발행된 아이템으로부터 절대적으로 중복이 발생하지 않게 합니다



### distinctUntilChanged()

![distinctUntilChanged](/assets/images/distinctUntilChanged.png)

발행된 아이템이 이전 발행된 아이템과 같을 때는 중복을 방지하여 발생하지 않지만 다른 데이터가 들어오면 아이템을 발행합니다.





