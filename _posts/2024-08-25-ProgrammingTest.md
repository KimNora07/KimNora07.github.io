---
layout: single
title: "[ProgramingTest] 백준 1316번 문제"
excerpt: "백준 프로그래밍 테스트"

categories: # 카테고리 설정
  - ProgrammingTest
tags: # 포스트 태그
  - [BackJoon, PrgrammingTest]

permalink: programmingTest/backjoon1316 # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

---

**[1회차/8월 25일/백준 1316/C++]**<br/>
<span style="font-size:150%">문제<br/><span style>

<p align="center">
  <img src="/assets/images/Backjoon/Backjoon1316Problem.png">
</p>

<span style="font-size:150%">결과<br/><span style>

<p align="center">
  <img src="/assets/images/Backjoon/Backjoon1316Result.png">
</p>

<span style="font-size:150%">코드<br/><span style>

```
#include <stdio.h>
#include <iostream>
#include <string.h>
#include <string>

using namespace std;

int main() {
    int num;            // 입력받은 단어의 개수
    string str;         // 입력받은 단어
    int count = 0;      // 그룹단어가 아닌 단어들의 개수

    cin >> num; // 몇개의 단어를 입력하게 할건지 입력하게 함

    // 입력가능한 단어의 개수 만큼 반복
    for (int i = 0; i < num; i++) {
        cin >> str; // 단어를 입력

        bool alphabet[26] = { false, }; // 26개의 알파뱃들을 모두 초기화(false로 설정)
        alphabet[(int)(str[0]) - 97] = true;    // 단어의 첫번째 알파뱃을 true로 변경

        // 첫번째 알파뱃을 제외하고 시작하도록 하는 반복문
        for (int j = 1; j < str.size(); j++) {

            // j번째 알파뱃과 j-1의 알파뱃이 같다면 연속적인 알파뱃이기에 넘어감
            if (str[j] == str[j - 1]) {
                continue;
            }

            // j번째 알파뱃과 j-1의 알파뱃이 다르므로 연속적이지 않고, j번째 알파뱃이 이미 연속적이라는 것을 인지했을 경우
            // count에 1을 더하고 멈춤(그 단어는 그룹단어가 아니라는 것을 확인)
            else if (str[j] != str[j - 1] && alphabet[(int)(str[j]) - 97] == true) {
                count++;
                break;
            }

            // 위의 두 경우에 해당하지 않으며, j번째 알파뱃이 처음 등장한 알파뱃이라면
            // true로 변환
            else {
                alphabet[(int)(str[j]) - 97] = true;
            }
        }
    }

    // 그룹 단어의 개수 = 전체단어의 개수 - 그룹단어가 아닌 단어의 개수
    cout << num - count;

    return 0;
}
```
