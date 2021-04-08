---
layout: default
title: OS 주요 변경 사항
parent: Framework
grand_parent: Android
permalink: /docs/android/framework/os-important-changed/

---

## OS별 주요 변경사항



### 백그라운드 제한

Android 8.0(API 26 Oreo) 부터 백그라운드 서비스에 대한 제한이 강화됩니다.

앱이 포그라운드에 있을 때 는 백그라운드에 제한이 비활성화 됩니다. 아래는 포그라운드에 대해 간주한 경우입니다.

- Activity가 시작 혹은 일시중지 되거나 눈에 보이는 Activity가 있는 경우
- 포그라운드 서비스가 있는 경우
- 다음 항목과 같은 사항으로 다른 포그라운드 앱이 연결된 경우
  - [IME](https://developer.android.com/guide/topics/text/creating-input-method)
  - 배경화면 서비스
  - 알림 리스너
  - 음성 또는 텍스트 서비스



만약 포그라운드가 아닌 백그라운드 상태에서 백그라운드 서비스가 유지된다면 Oreo 이상부터는 5초 이내에 startForeground()를 호출하여 포그라운드로 변경해야합니다. 변경하지 않는다면 ANR이 발생합니다.



안드로이드 서비스는 크게 3가지가 있습니다.

- Foreground
- Background
- Bound



