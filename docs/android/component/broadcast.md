---
layout: default
title: 브로드캐스트(Broadcast)
parent: Component
grand_parent: Android
permalink: /docs/android/component/broadcast/

---

## Broadcast Receiver 란 무엇일까?

안드로이드에서 Broadcast란 SMS, 배터리, 시스템 부팅등 시스템 범위의 이벤트들을 전달, 수신하는 구성 요소입니다. Broadcast는 말 그대로 방송사에서 방송을 하고 TV 채널을 수신하는 것과 비슷합니다. 방송사에서는 수신자에 관계없이 방송하고 수신 TV는 요금제에 맞는 채널만 보여주듯이 `IntentFilter`로 원하는 이벤트만 수신이 가능합니다

##  OS별 제한사항

### Android 9 (API 28)

Android 9(API 레벨 28)부터 [`NETWORK_STATE_CHANGED_ACTION`](https://developer.android.com/reference/android/net/wifi/WifiManager?hl=ko#NETWORK_STATE_CHANGED_ACTION) 브로드캐스트는 사용자의 위치 또는 개인 식별 데이터에 관한 정보를 수신하지 않습니다. 또한 Wi-Fi의 시스템 브로드캐스트 정보에는 SSID, BSSID 검색 결과가 포함되지 않습니다. 이 정보를 얻으려면 [`getConnectionInfo()`](https://developer.android.com/reference/android/net/wifi/WifiManager?hl=ko#getConnectionInfo())를 이용해야 합니다.



### Android 8.0 (API 26)

Android 8.0 (API 26) 부터 백그라운드에 대한 제한사항이 강화되면서 더이상 manifest에 암시적 브로드캐스트를 선언할 수 없습니다. 



### Android 7.0 (API 24)

Android 7.0 (API 24) 이상에서는 다음과 같은 항목이 제한 됩니다.

- `ACTION_NEW_PICTURE`
- `ACTION_NEW_VIDEO`
- `CONNECTIVITY_ACTION`를 manifest에 수신자로 선언 불가





