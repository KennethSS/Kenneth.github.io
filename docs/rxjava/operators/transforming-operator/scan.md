---
layout: default
title: FlatMap
parent: 변환 연산자
grand_parent: RxJava
permalink: /docs/rxjava/operator/trasforming-operator/scan/

---

## Scan

**Scan**은 Observable이 발행하는 각 항목에 대해서 순차적으로 작성한 함수의 결과를 적용하고 값을 내보냅니다. 

![scan](/assets/images/scan.png)

**Scan** 연산자는 **Reduce**와 비슷하지만 조금 다릅니다. Observable에서 발행된 첫번째 아이템은 그대로 결과로 전달하고 그 이후 부터는 중간 결과 값과 최종 결과를 구독자에게 발행합니다.



### 샘플 코드 ()

```kotlin
observable
	.scan { t1, t2 ->
		println("Scan $t1 to $t2")
		t1 + t2
	}
	.subscribe(::printSubscribe)
```



```
Result: 1
Scan 1 to 2
Result: 3
Scan 3 to 3
Result: 6
```

