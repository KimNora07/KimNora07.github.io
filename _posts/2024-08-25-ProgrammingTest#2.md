---
layout: single
title: "[ProgramingTest] 백준 25206번 문제"
excerpt: "백준 프로그래밍 테스트"

categories: # 카테고리 설정
  - CodingTest
tags: # 포스트 태그
  - [BackJoon, CodingTest]

permalink: programmingTest/backjoon25206 # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

---

**[1회차/8월 25일/백준 25206/C++]**<br/>
<span style="font-size:150%">문제<br/><span style>

<p align="center">
  <img src="/assets/images/Backjoon/Backjoon25206Problem.png">
</p>

<span style="font-size:150%">결과<br/><span style>

<p align="center">
  <img src="/assets/images/Backjoon/Backjoon25206Result.png">
</p>

<span style="font-size:150%">코드<br/><span style>

```
#include <stdio.h>
#include <iostream>
#include <string.h>
#include <string>

using namespace std;

int main() {
    // 전공평점 계산식: 전공과목별 {(학점 * 과목평점)의 합} / (학점의 총합)
    // P/F 과목의 경우 등급이 P또는 F로 표시되는데, 등급이 P인 과목은 계산에서 제외해야 한다.
    
    // 입력
    // [20줄] [과목명/학점/등급] 공백으로 구분
    double majorRating = 0.0f;  // 전공평점
    double total = 0.0f;        // 학점의 총합

    for (int i = 0; i < 20; i++) {
        string subjectName; // 전공과목 이름
        double score;       // 학점
        string ratingStr;   // 등급
        double rating = 0;  // 등급별 점수
 
        cin >> subjectName >> score >> ratingStr;

        // P등급을 제외한 등급별 점수
        if (ratingStr == "P") continue;
        else if (ratingStr == "A+") rating = 4.5f;
        else if (ratingStr == "A0") rating = 4.0f;
        else if (ratingStr == "B+") rating = 3.5f;
        else if (ratingStr == "B0") rating = 3.0f;
        else if (ratingStr == "C+") rating = 2.5f;
        else if (ratingStr == "C0") rating = 2.0f;
        else if (ratingStr == "D+") rating = 1.5f;
        else if (ratingStr == "D0") rating = 1.0f;
        else if (ratingStr == "F")  rating = 0.0f;
        
        // P등급일 때는 계산에서 제외
        if (ratingStr != "P") {
            majorRating += (rating * score);
            total += score;
        }
    } 

    // 출력
    // 전공평점을 출력
    majorRating = majorRating / total;

    cout << majorRating;
}
```
