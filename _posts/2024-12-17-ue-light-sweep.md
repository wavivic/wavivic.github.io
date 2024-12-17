---
title: "[UE] 텍스쳐에 빛이 지나가는 이펙트 주기"
excerpt: "머터리얼에서 빛이 지나가는 듯한 이펙트(light sweep) 부여하는 법 소개"

categories: # 카테고리 설정
  - unreal
tags: # 포스트 태그
  - [ Unreal, UE, UE5, Material ]

permalink: /ue-light-sweep/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2024-12-17 # 작성 날짜
last_modified_at: 2024-12-17 # 최종 수정 날짜
---

### 🍥 개요

![](\assets\images\posts_img\unreal\lightsweepEX.gif)
<sup><i>▲ Light Sweep의 예시</i></sup>

UI에 종종 쓰이는 이펙트인 Light Sweep 효과를 언리얼 머터리얼에서도 적용하고자 한다.

---

### 🍥 방법
#### <mark>기본 설정</mark>
png 투명 파일을 그대로 적용하기 위하여 아래와 같이 세팅함.

- Material Domain : Surface
- Blend Mode : Translucent


![](\assets\images\posts_img\unreal\light-sweep-material.png)

#### <mark>Light Sweep</mark>

1. 빛이 지나가는 효과를 줄 맵을 제작.
   1. 흰색 : 빛처럼 밝아질 영역
   2. 검은색 : 투명 영역
2. Panner 노드를 이용하여 이동 애니메이션 부여.
   1. Time 입력핀에는 시간 흐름이 들어가는 노드와 연결
   2. Speed는 맵을 움직일 방향과 속도에 따라 조절
3. Panner의 아웃핀을 텍스쳐 샘플의 UVs 인풋에 연결
4. 원하는 밝기에 따라 Multiply도 해 줄 수 있음

- - -

### 🍥 결과

![](\assets\images\posts_img\unreal\light-sweep-result.gif)

✨✨
