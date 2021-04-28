---
layout: default
title: WorkManager
parent: Jetpack
grand_parent: Android
permalink: /docs/android/jetpack/workmanager/

---

## WorkManager 이점

- 작업 제약조건
- 강력한 예약 관리
- 유연한 재시도 정책
- 작업 체이닝
- 지연 가능하고 안정적인 작업(앱 종료 및 기기 재시작에 대응)



### WorkManager 주 사용 목적

- 백엔드 서비스에 로그 또는 분석 전송
- 주기적으로 앱 데이터 서버와 동기화



### 사용 방법

1. Worker를 상속받아 Custom Worker 생성
2. WorkRequestBuilder를 통해 WorkRequest 생성(OneTimeWorkRequestBuilder)
3. WorkManager.getInstance(context).enqueue(workrequest)로 실행

