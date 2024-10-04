---
layout: single
title: "[ProgramingTest] 백준 10798 문제"
excerpt: "백준 프로그래밍 테스트"

categories: # 카테고리 설정
  - ProgrammingTest
tags: # 포스트 태그
  - [BackJoon, PrgrammingTest]

permalink: programmingTest/backjoon10798 # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

---

**[1회차/8월 25일/백준 10798/C++]**<br/>
<span style="font-size:150%">문제<br/><span style>

<p align="center">
  <img src="/assets/images/Backjoon/Backjoon10798Problem.png">
</p>

<span style="font-size:150%">결과<br/><span style>

<p align="center">
  <img src="/assets/images/Backjoon/Backjoon10798Result.png">
</p>

<span style="font-size:150%">코드<br/><span style>

```
#include <stdio.h>
#include <iostream>
#include <string.h>
#include <string>

using namespace std;

int main() {
    string str[5];
    string maxSizeStr;

    for (int i = 0; i < 5; i++) {
        cin >> str[i];
    }

    maxSizeStr = str[0];

    for (int i = 1; i < 5; i++) {
        if (str[i].size() > maxSizeStr.size()) {
            maxSizeStr = str[i];
        }
    }

    for (int i = 0; i < maxSizeStr.size(); i++) {
        for (int j = 0; j < 5; j++) {
            if (i < str[j].size()) {
                cout << str[j][i];
            }
        }
    }

    return 0;
}
```
