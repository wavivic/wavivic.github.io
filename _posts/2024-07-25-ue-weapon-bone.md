---
title: "[UE] Weapon Bone이 있는 스켈레톤의 애니메이션"
excerpt: "Weapon Bone이 있는 스켈레톤의 애니메이션을 리타겟팅을 통하여 원활하게 쓸 수 있는 방법"

categories: # 카테고리 설정
  - unreal
tags: # 포스트 태그
  - [ unreal, develog ]

permalink: /categories/unreal/ue-weapon-bone/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2024-07-25 # 작성 날짜
last_modified_at: 2024-08-13 # 최종 수정 날짜
---

## 🍥 개요

![](https://velog.velcdn.com/images/cottondream/post/fa1d7e3e-bafe-499d-8288-85f9e2e79584/image.gif)

애니메이션 리타겟팅 이후 Arm, Unarm 애니메이션에서 무기의 위치가 원본 애니메이션과 다르게 어색한 것이 확인됨.

- - -

## 🍥 해결 1)

###  해결 방법

소켓과 Arrow 컴포넌트를 활용해 Montage Notify에서 무기의 메쉬의 위치를 조정해 봄.
  ![](https://velog.velcdn.com/images/cottondream/post/88a21b7e-a6de-4c59-b9ba-710cfd906b36/image.png)

###  문제점

![](https://velog.velcdn.com/images/cottondream/post/ad79fbf3-22c3-4ef9-a998-ea3fe58c5481/image.gif)
![](https://velog.velcdn.com/images/cottondream/post/018a1077-330a-49e8-abe1-66a0a3613f96/image.gif)

개발하고 있는 게임의 장르가 소울라이크이다보니, 전반적인 **_게임이 주는 중후한 무게가 생명_**이라고 생각했다. 그런데 멋있게 칼을 뽑고 넣어야 하는 상황에서 이런 식으로 덜커덩(...)거리는 건 타협할 수 없는
지점. 심지어 구매한 애니메이션은 고가. 이와 같이 사용하려던 건 본 의도와는 동떨어져 있음.

- - -

## 🍥 문제 분석
###  해결할 수 있다고 생각한 이유

원본 애니메이션은 제작 버전보다 한참 상위인 5.4.2 버전에서도 문제없이 깔끔하게 재생되었다. 충분히 해결할 수 있는 문제라고 생각했다.


### 무엇이 다른가?
![](https://velog.velcdn.com/images/cottondream/post/32b99f07-8c8a-4b9e-bcc1-32cf38935bb1/image.png)

1) 원본 스켈레탈 메쉬는 검과 칼집이 아예 붙어있음.

2) 스켈레톤에서 본 트리 구조를 확인하면서, 해당 메쉬가 어느 본에 붙어 있는지 확인.

3) 오브젝트들은 본래 있어야 하는 손의 본을 부모로 하는 **weapon_r, weapon_l 이라는 새로운 본**에 붙어 있었음.

4) 새로운 본이라서 리타겟팅(5.4 auto 진행) 되면서 이를 놓쳤다고 생각함.


### 결론

따라서, 본을 수정할 필요성을 느낌.

- - -

## 🍥 해결 2)

### 본 수정

> **Skeletal Mesh Editing Tools**

본을 만질 때는 보통 3D 모델링 프로그램을 써야 한다. 개인적으로 그렇게 하고 싶지 않았다.... 다른 툴까지 써가며 해결해야 되는 필수 이슈가 있는데, 판매자가 간과할 리가. 알고 보니 언리얼에서 이미 제공하는
기능(!)이다.

- 언리얼 Plugins에서 **Skeletal Mesh Editing Tools**를 다운로드 받고 재시작.

- 본을 수정할 스켈레탈 메쉬를 오픈.
- Editing Tools를 클릭하고 Edit Skeleton 으로 원본 스켈레톤 참고하며 추가.


  ![](https://velog.velcdn.com/images/cottondream/post/51721c98-7023-4594-bf74-55f09bc97bf5/image.png)


### 리타겟 체인 추가

- 원본과 수정할 스켈레탈 메쉬의 IK Rig 생성.
- 최대한 원본과 비슷하게 체인 만들기.
- Weapon용 본에 새로운 체인을 각각 만들어 서로 연결.


### 리타겟팅 후 소켓 추가

- IK Rig 를 바탕으로 IK Retargeter 생성.
- 해당 리타겟터를 이용해 애니메이션 리타겟팅.
- 스켈레톤에 추가된 새로운 Weapon 본에 소켓을 넣고 무기 메쉬 부착.


### 결과

![](https://velog.velcdn.com/images/cottondream/post/ce5df829-9a57-44d0-a851-c1659a3329ae/image.gif)


### 문제점

기쁨, 그리고 절망.... 칼이 돌아가긴 한다. 본이 제대로 만들어져서 리타겟팅 된 것이다. 그러나 무기가 끝까지 오른손을 따라온다. 여기서 최후의 수단으로 키 프레임을 손수 찍어야 할까 고민했다. 그런데 막상
하려고 했으면 어차피 사용해야 하는 스켈레탈 메쉬에는 무기 메쉬가 병합되어 있는 게 아니라서 적절하지 못한 방법이었을 것이다.

강사분들에게도 여쭤 보고 동기들에게도 물어보고. 이래저래 해 봤지만, 포기하는 게 좋겠다는 결론이 나왔다. 그러나 분명 원본은 제대로 잘되는데! 거의 다 왔는데! 칼만 놓고 다시 돌아오면 되는 거다. Bone에
적용된 키들은 원본과 다르지 않고 모두 적절하다. 그래서 이거 분명 딸깍 한 번으로 끝날 문제일 것이다, 라는 예상으로 유튜브를 검색해 보았다.

검색어는 **unreal weapon bone** . . . !

- - -

## 🍥 해결 3)

> **Translation Mode를 Globally Scaled로 변경**

- 리타겟터에서 _Weapon Bone의 Chain 디테일_ 창 확인.
- FK 항목에서 Translation Mode를 None에서 **Globally Scaled**로 변경.

### 결과

![](https://velog.velcdn.com/images/cottondream/post/f734c7a2-9dd3-4608-abf8-61fe717322b0/image.gif)

성공! 짝짝짝! 🥹👏

- - -

## 🍥 요약

> - 언리얼 플러그인을 이용해 타겟 스켈레탈 메쉬에 Weapon Bone을 추가

- 원본, 타겟 전부 둘 다 Weapon Bone에 새로운 리타겟 체인 생성

- 체인의 디테일 창에서 Translation Mode를 **Globally Scaled**로 변경

- - -

## 🍥 마무리

-
  소켓이나 코드로 무기 위치를 조정해 보았으나 느낌상으로 어색하거니와, 원본 애니메이션 시퀀스의 **프리뷰에서는 코드를 이용하지 않고도 칼이 옮겨 가는 것**을 보고 다른 방법이 있을 거라고 접근했다. 이번
  이슈에서 가장 핵심적인 키 포인트였다. _이슈와 타협하지 않을 수 있었던 이유_ 이기도 하다.


- 최소 7시간을 이 방법, 저 방법 도전해 보았다. 결국 이런 시간이 최대한 가치 있게 느껴지려면 타협 없는 해결이 베스트라는 걸 느꼈다. 그런데 완벽하게 해결하려면 뭐다? 원인을 알아야 한다.


- 최근 개발 이슈 중에서 가장 오랫동안 고민했기에 개발 일지 형식으로 이 글을 남긴다.

- - -

## 🍥 Reference

- https://youtu.be/pa9AjL36wdY?si=1coADzEOobaJSdMt