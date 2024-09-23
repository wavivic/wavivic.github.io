---
title: "[Unity] Korean Typer 코드 리뷰"
excerpt: "음절 단위의 타이핑 효과를 주는 스크립트 코드 리뷰"

categories: # 카테고리 설정
  - unity
tags: # 포스트 태그
  - [ unity, code reivew, typing effect ]

permalink: /unity/korean-typer/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2024-09-03 # 작성 날짜
last_modified_at: 2024-09-23 # 최종 수정 날짜
---

### 🍥 개요 

개인 프로젝트를 만들면서 유일하게 사용했던 기능 패키지인 Korean Typer의 코드 리뷰를 하고자 한다. 개인 프로젝트에서 비교적 부드러운 다이얼로그 효과를 위하여 사용한 패키지다.

![](\assets\images\posts_img\koreanTyper\dialogue.gif)

'안' / '안녕' / '안녕하' / '안녕하세' / '안녕하세요' char 인덱스 순차적으로 출력보다도 'ㅇ' / '아' / '안' / '안ㄴ' / '안녀' / '안녕' 과 같이 음절 단위의 완벽한 타이핑 효과를 원했다.

후술할 배경 지식이 없었던 탓에 직접 만들 생각을 하지 못하고 서치로 찾게 된 패키지를 이용하였다. 충분한 코드 리뷰 후에 이 포스트를 게시한다.

- - -
### 🍥 배경 지식
ASCII 코드를 이용하여 문자를 처리하는 C++과 달리 C#에서는 Unicode를 이용한다.
- - -

### 🍥 Reference

[Korean Typer - KimYC1223 - Unity Asset Store](https://assetstore.unity.com/packages/tools/localization/koreantyper-232949)