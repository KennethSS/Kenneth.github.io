---
layout: default
title: 페이징 교체 알고리즘
parent: Algorithm
grand_parent: CS
permalink: /docs/cs/algorithm/paging-replacement-algorithm/


---



# 페이징 교체 알고리즘(Paging Replacement Algorithm)

## 페이징 교체 알고리즘 이란?

페이지 교체 알고리즘(Paging Replacement Algorithm)은 [페이징 기법](https://ko.wikipedia.org/wiki/페이징_기법)으로 메모리를 관리하는 운영체제에서 [페이지 부재(Page Fault)](https://ko.wikipedia.org/wiki/페이지_부재)가 발생하여 새로운 페이지를 할당하기 위해 현재 할당된 페이지 중 어느 것과 교체할지를 결정하는 방법이다.

이 알고리즘이 사용되는 시기는 페이지 부재가 발생하여 새로운 페이지를 적재하고 싶지만 더 이상 새로운 페이지를 적재할 공간이 없을 때 어느 것을 교체할지 정할 때 사용된다. 이를통해 페이지 부재 문제를 해결할 수 있다.

단점으로는 TimeStamping에 의한 overhead가 존재한다는 점이다.

## 페이지 알고리즘 종류

### FIFO

단순한 알고리즘으로 가장 오래된 페이지(가장 먼저 메모리에 적재된 페이지)를 교체하는 알고리즘이다.    

   

### LFU

가장 적은 횟수를 참조한 페이지를 교체하는 알고리즘.  

   

### LRU

가장 오랫동안 되지 않은 페이지를 교체

이 알고리즘의 기본 가설은 가장 오랫동안 이용되지 않은 페이지는 앞으로도 사용할 [확률](https://ko.wikipedia.org/wiki/확률)이 적다는 것이다.



