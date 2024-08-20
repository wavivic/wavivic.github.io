---
title: "[UE] 나침반(Compass) 구현"
excerpt: "나침반 관련 기능을 머터리얼부터 UI까지 만드는 법"

categories: # 카테고리 설정
  - unreal
tags: # 포스트 태그
  - [ unreal, develog, compass, UI ]

permalink: /unreal/ue-compass/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2024-08-20 # 작성 날짜
last_modified_at: 2024-08-20 # 최종 수정 날짜
---

### 🍥 개요
![](\assets\images\posts_img\compass\example.gif)

<sub> 예시는 엘든링의 나침반 HUD </sub>

Elden Ring이나 여타 FPS 게임처럼 카메라의 회전에 따라 보는 곳의 방향을 알려 주는 나침반 기능을 HUD에 추가하고 싶었다.

- - -

### 🍥 원리

> 1. 정가운데를 N(남쪽)으로 하는 나침반 이미지 텍스쳐를 생성.
> 2. 머터리얼의 Offset UV 좌표를 파라미터화.
> 3. 컨트롤러의 Yaw 회전값에 따라 Offset 좌표 변경.

- - -

### 🍥 Material

> 💡 미리 설정!
>  
> 1. Result Node의 디테일 창에서 도메인은 <mark>User Interface</mark>로 설정.
> 2. 양 옆으로 페이드 아웃 효과를 주려면 블렌드 모드는 <mark>Translucent</mark>로 변경.

![](\assets\images\posts_img\compass\bp_material.png)

#### 오프셋 좌표를 파라미터화 하기
기본적으로 UV 또한 0 ~ 1 사이의 값으로 이루어진, 축이 두 개인 Vector2 좌표계이기 때문에 익히 알고 있는 그대로 적용할 수 있다. 따라서, 좌표의 원점을 바꾸는 공식은 아래와 같다.

현재 좌표 A<br>
현재 중심 좌표 C<sub>1</sub><br>
새 중심 좌표 C<sub>2</sub>

**<mark>A' = (A - C<sub>1</sub>) + C<sub>2</sub></mark>**

위 공식을 토대로 캡처 이미지처럼 머터리얼 노드를 구성할 수 있다. 

1. Tex Cord
   - 텍스처의 UV 좌표를 가져온다. 
2. Append 
   - UV 벡터 값을 생성하는 노드.
   - 나침반의 이미지는 X축으로만 움직이면 되기 때문에, X축은 파라미터로 빼 주고 Y축은 0으로 지정한다.
3. Add
   - 현재 중심 좌표는 (0, 0)이기 때문에 단순 새 중심 좌표를 더해 주면 된다. 
4. Texture Sample
   - 사용할 텍스처를 설정해 주고 RGB 채널을 마지막 컬러에 연결해 주면 된다.

<br>

#### 사이드에 페이드 아웃 효과 주기

어떤 방법으로 페이드 아웃을 할까, 고민하다가 머터리얼에서 한꺼번에 처리하기로 했다.

0. 알고 가야 하는 성질
   - Color) 0 == 검은색 / 1 == 흰색
   - Opacity) 0 == 보이지 않음 / 1 == 보임
1. 그라디언트 마스크 맵 생성
   - 가운데는 보여야 하고, 끝으로 갈수록 흐릿하다가 보이지 않아야 하기 때문에 0을 숙지하고 **좌우 끝이 까만 그라디언트로 마스크 맵을 생성** 하여 준다.
2. 텍스처와 마스크 맵을 Multiply
   - 0에 어떤 수를 곱하여도 0이기 때문에 투명하게 렌더링됨.
3. Multiply한 값을 최종 Opacity에 연결.

- - -

### 🍥 WBP

![](\assets\images\posts_img\compass\bp_wbp.png)

1. User Widget을 상속받은 WBP를 생성. Hierarchy에 나침반 텍스처가 들어갈 Image를 배치.
2. Pre Construct - **Create Dynamic Material Instance**
   - 게임이 실행되는 중에 인스턴스 값을 바꿔야 하기 때문에 머터리얼의 동적 인스턴스를 생성하는 노드를 사용하여 준다.
3. 2에서 생성된 인스턴스를 따로 변수로 담아 주고, 이를 Image의 머터리얼에 넣어 준다.
4. Tick
   - 인스턴스로 생성한 머터리얼의 파라미터를 변경.
   - 캐릭터의 컨트롤러(마우스)의 **Yaw 회전값을 파라미터와 연결**.
   - 최대 360의 값을 가질 수 있기 때문에 UV 좌표 값과 매칭할 수 있도록 360으로 나눠 준다.
   
- - -

### 🍥 결과

![](\assets\images\posts_img\compass\result.gif)

이제 길을 잃지 않을 수 있게 되었다!

- - -

### 🍥 Reference

Ryan Laley - [ **Unreal Engine 5 Tutorial - Compass Part 1: UI** ](https://youtu.be/o-pgOvQlI6I?si=sa1w5u82EG_MM07g)