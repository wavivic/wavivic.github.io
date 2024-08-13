---
title: "[UE] 애니메이션 구간 속도 조절"
excerpt: "ANS를 이용한 애니메이션 시퀀스의 특정 구간 속도 조절"

categories: # 카테고리 설정
  - unreal
tags: # 포스트 태그
  - [ unreal, develog ]

permalink: /unreal/ue-weapon-bone/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2024-07-26 # 작성 날짜
last_modified_at: 2024-08-13 # 최종 수정 날짜
---

### 🌸 개요
![](https://velog.velcdn.com/images/cottondream/post/4f27e4a3-1fd6-4189-a689-6f1a522b697c/image.gif)

칼을 내려치는 애니메이션 중에 다시 Idle로 돌아오는 _**특정 구간의 재생 속도를 제어**_ 하고 싶었다.

- - -

### 🌸 해결
제어하는 데에 다른 방법이 있겠지만, 본 글에서는 **Montage**와 **Animation Notify State**를 이용한다.

- 조절하고자 하는 애니메이션 시퀀스를 몽타주로 만든다.
- 조절하고자 하는 구간에 ANS를 추가한다.
- Notify Begin 함수를 오버라이드한다.
- Anim Instance에 접근하여 Montage Set Play Rate에서 Rate 값을 원하는 대로 조정한다.
  ![](https://velog.velcdn.com/images/cottondream/post/ad71133d-8375-4bb9-bce9-c410fa5c2a71/image.png)

- - -

### 🌸 결과![](https://velog.velcdn.com/images/cottondream/post/48422339-075a-41c3-b559-64dbb585db0d/image.gif)

