---
layout: default
title: MultiDex 란?
parent: Framework
grand_parent: Android
permalink: /docs/android/framework/multidex/

---

```
trouble writing output:
Too many field references: 131000; max is 65536.
You may try using --multi-dex option.
```

빌드 시에 위와 같은 오류를 마주한 적이 있다면 이것은 `MultiDex`관련 오류이다

## MultiDex가 무엇인가?

APK 파일에는 `Dalvik Executabled(DEX)` 파일 형식의 실행 가능한 바이트 코드 파일이 포함되어있고 이 DEX 파일 안에는 앱을 실행하기 위해 컴파일된 코드들이 들어있다. `Dalvik Executabled` 내 참조가능한 메서드의 개수는 65,536으로 제한되어있다. 이 65,536 개수에는 안드로이드 프레임워크, 라이브러리, 자체 코드가 모두 포함되어 있다. 이 제한이 넘어가 버리면 `MultiDex` 오류가 발생한다

## MultiDex 제한사항 회피 방법

- 코드 축소 사용
- 큰 라이브러리 미포함
- R8으로 사용되지 않는 코드 삭제

위와 같은 방법으로 `MulitDex` 오류를 회피할 수 있다. 하지만 요즘처럼 많은 기능을 요구하는 앱에 `MultiDex` 적용은 필수불가결 할 것이다.
그럼 어떻게 `MultiDex` 를 설정하는지 알아보자

## MuitiDex 설정

minSdkVersion 21 (API 21) 이상은 기본적으로 사용 설정되어서 더 이상 MultiDex를 설정해줄 필요가 없다.

minSdkVersion 21 (API 21) 이하 설정 방법

<script src="https://gist.github.com/KennethSS/b903e7bcf01c151abe0d9c1189253054.js"></script>

`build.gradle(app)`에 라이브러리를 추가 해준다

<script src="https://gist.github.com/KennethSS/a13ec97fcdbb28566d56dc1afcca4c14.js"></script>

`AndroidManifest.xml` 에 `application` 을 MultiDexApplication으로 선언한다

<script src="https://gist.github.com/KennethSS/9a218c9f9e669ee9a9f69f2ac9da1a01.js"></script>



MultiDexApplication을 상속받거나 attachBaseContext에서 MultiDex를 설치해주면 된다.

## 마무리

요즘 개발하다가 문득 느끼는게 무분별한 라이브러리 사용은 성능이슈와
Dex 혹은 앱크기에 문제가 간다는걸 느끼고 있다.
간단한 기능 정도는 라이브러리를 사용하지 않고 직접 구현하는 방식으로 LightWeight 앱을 구현하는 방식이 이상적이다