---
layout: default
title: 마샬링과 직렬화 차이
parent: CS
nav_order: 2



---



마샬링(Marshalling)과 언마샬링(Unmarshalling).  
직렬화(Serialization)와 역직렬화(Deserialization) 차이는 무엇일까?



**마샬링**은 한 [객체](https://ko.wikipedia.org/wiki/객체_(컴퓨터_과학))의 메모리에서 표현방식을 저장 또는 전송에 적합한 다른 데이터 형식으로 변환하는 과정이다. 마샬링은 프로그램간 다른 부분 혹은 프로그램에서 프로그램으로 이동할 때 사용하는 변환 과정이라고 할 수 있다.

**직렬화**는 객체의 상태를 저장하기 위해 byte stream 형태로 변환하는 것을 의미한다.   
즉 객체에 저장된 데이터를 stream 형태로 write 하기 위해 연속적인 데이터로 변환하는 것이다

즉 이 둘의 큰 차이는 직렬화(Serialization)는 객체를 대상으로하고 마샬링(Marshalling)은 변환 그 자체의 목적이 있다. 주로 마샬링은 다른 언어 및 플랫폼 간의 데이터를 주고 받을 때 사용한다.



### 참고자료

- [마샬링-위키디피아](https://ko.wikipedia.org/wiki/마샬링_(컴퓨터_과학))
- [직렬화-위키디피아](https://ko.wikipedia.org/wiki/직렬화)