---
title: "[Unity] 비디오 플레이어 재생 시 초반 프레임 깜빡임 현상 해결"
excerpt: "유니티로 Video Player 컴포넌트를 이용한 영상 재생 시 초반 프레임이 깜빡거리는 현상을 개선하는 법 제시"

categories: # 카테고리 설정
  - untiy
tags: # 포스트 태그
  - [ unity ]

permalink: /untiy-video-flicker-issue/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2024-11-28 # 작성 날짜
last_modified_at: 2024-11-28 # 최종 수정 날짜
---

### 🍥 현상

> 비디오 플레이어 컴포넌트를 이용하여 영상 재생 시 초반 프레임 부분에서 깜빡이는 현상 발생.

---

### 🍥 적용 실패한 해결 방법

- 비디오 컴포넌트의 Prepare 함수 이용
- 렌더 텍스쳐의 버퍼 초기화
- Graphic Blit

- - -

### 🍥 이슈 환경
- Video Player Component
  - Render Mode : Camera Far Plane
  - Wait For First Frame : True
  - Skip On Drop : True
- Video Clip
  - Original Res : 3840 * 2160 (4K)

- - -
### 🍥 해결 방법

![](\assets\images\posts_img\Unity\flicker.png)

1. 임포트한 비디오 클립의 코덱을 H.265로 변경해 주거나, (H.264의 경우에도 같은 현상 발생)
2. 해상도를 낮춰 준다.