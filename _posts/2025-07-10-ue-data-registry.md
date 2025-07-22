---
title: "[UE] 데이터 레지스트리"
excerpt: "언리얼 데이터 관리"

categories: # 카테고리 설정
  - unreal
tags: # 포스트 태그
  - [ Unreal, UE, UE5, Data, DataTable, DataRegistry ]

permalink: /ue-data-registry/ # 포스트 URL

toc: true # 우측에 본문 목차 네비게이션 생성
toc_sticky: true # 본문 목차 네비게이션 고정 여부

date: 2025-07-10 # 작성 날짜
last_modified_at: 2025-07-22 # 최종 수정 날짜
---

### 🍥 개요

Data Table을 쓰면서 해당 데이터에 접근하려면 쓰는 곳마다 참조를 해 주어야 하는데 **데이터에 글로벌하게 접근할 수 있는 방법**은 없을까? 하는 생각으로부터 시작하여 Data Registry를 사용하게 됨.

---

### 🍥 Data Registry

[언리얼 엔진의 데이터 레지스트리 | 언리얼
엔진 5.6 문서 || Epic Developer Community] (https://dev.epicgames.com/documentation/ko-kr/unreal-engine/data-registries-in-unreal-engine)

#### <mark>장점</mark>

- Data Table과 같은 데이터 에셋을 통합할 수 있음 
  - 분량과 같은 문제로 카테고리를 여러 개 나누어 관리하나 탐색은 통합하여 이루어져야 할 때 유용 
  - 예를 들어, 스킬이란 큰 카테고리 안에서 클래스 별로 나눠야 함 그러나 어빌리티 부여할 때 모든 클래스를 순회하여 조건에 따라 분류된 어빌리티만 부여하도록 해야 함 이럴 때 여러 데이터 에셋을 한 데 모을 수 있음
- 데이터 에셋을 직접 참조하지 않아도 되어 의존성을 줄임
- 빠른 속도, 적은 코스트

#### <mark>주의점</mark>
- Data Table처럼 모든 데이터를 가지고 와 순회하면서 필터링하는 기능은 현재까지 찾지 못함
- 특정 Data를 가져오는 데에 특화된 것으로 보임

- - -

### 🍥 데이터 레지스트리 세팅
#### 1. Plugin
![](\assets\images\posts_img\unreal\DataRegistry\data-registry-plugin.png)
- 해당 프로젝트에 Data Registry 이름의 플러그인을 추가

#### 2. Project Settings
![](\assets\images\posts_img\unreal\DataRegistry\data-registry-projectsetting.png)
- Project Settings - Game - Data Registry 에서 Directories to Scan 추가
- Data Registry를 탐색하는 경로를 추가하여야 함 해당 경로를 기준으로 순회

#### 3. Data Registry Asset
![](\assets\images\posts_img\unreal\DataRegistry\data-registry-asset.png)
- 데이터 테이블과 같은 관련 에셋을 제작한 후 진행
- Data Registry 에셋을 생성
- Registry Type : 데이터 레지스트리를 구분하는 기준
- Item Struct : 다룰 데이터 구조체
- Data Source : 선행으로 제작한 에셋들 추가

- - -

### 🍥 코드
```angular2html
// 레지스트리 구분할 프로퍼티 설정
FDataRegistryId RegistryId;
RegistryId.RegistryType = FDataRegistryType("Ability");
RegistryId.ItemName = AbilityTags.First().GetTagName();

// 레지스트리에서 데이터 뽑기
const FAbilityData* OutData = UDataRegistrySubsystem::Get()->GetCachedItem<FAbilityData>(RegistryId);

  if (OutData)
  {
  // ... 처리
  }
```
