---
title: "Hey, Developer!"
permalink: /about/
layout: single
classes: wide
comments: false
---

<style>
.outer-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
    .two-columns {
        display: flex;
        flex-direction: row;
    }
    .column1 {
        flex-basis: 30%;
        padding: 10px;
        color:  #ff9db9 !important;
    }
    .column2 {
        display: inline;
        flex-basis: 70%;
        padding: 10px;
    }

    .hover-image-container img {
        display: none; /* 기본적으로 이미지를 숨김 */
        position: absolute;
        transform: translate(-100%, -50%);
        z-index: 10;
    }

    .hover-image-container:hover img {
        display: block; /* 마우스를 올리면 이미지를 표시 */
    }

    .column2 a {
        text-decoration: none;
        color: #ff9db9 !important;
        font-weight: bold;
    }
    .hover-image-container {
        display: inline;
    }

</style>

<div class="two-columns">
<div class="column1">
<img src="\assets\images\meee.png" width="200">
</div>
<div class="column2">
<br>
{{ "

**<mark>Email</mark>** &ensp; cottondream116@gmail.com

**<mark>Github</mark>** &ensp; https://github.com/wavivic

**<mark>Blog</mark>** &ensp; https://wavivic.github.io

" | markdownify }}


</div>
</div>
- - -
<div class="two-columns">
<div class="column1">
        {{ "# INTRODUCE" | markdownify }}
</div>
<div class="column2">
{{ "## 스스로 고민하고 실현해내는 것이 즐거운 게임 클라이언트 개발자입니다."| markdownify }}
<br>
&ensp; 모 개발 회사 사무실에는 ‘어~?’ 를 금지하는
문구<div class="hover-image-container"><a href="#"><sup>[1]</sup></a><img src="\assets\images\posts_img\about/first.jpg" width="400"></div>
가 붙어 있다고 합니다. 개발자들의 밈(meme) 중에 만국 공통으로 유명한 밈은 ‘어? 이게 왜 되지?’, ‘어? 이게 왜 안 되지?’<div class="hover-image-container">
<a href="#"><sup>[2]</sup></a><img src="\assets\images\posts_img\about/second.png" width="400"></div>가 있습니다. 저의 ‘어?’ 는 <i><b>‘어? 이게 왜 (의도한 대로) 안 되지?’</b></i> 밖에 없습니다.
<br>
<p>

1. 기능을 스스로 고민하고 실현해내며, 작성한 코드 한 줄, 한 줄의 문맥적 의미와 역할을 파악하고 있습니다.

2. 구현할 구체적인 목표를 정리 후에 슈도 코드를 작성하여 로직을 짭니다.

3. 의도와 달리 작동하지 않을 때엔 왜 안 되는지 가장 먼저 원인에 접근합니다. 디버깅을 적극 활용합니다.

4. 교육 기간 동안 강사나 교육생들에게 문제 접근 방식이나 해결 방법을 제시한 경험이 다수 존재합니다.

</p><br>
<p></p>
{{ "<mark><b>💡 스스로 고민하고 실현하는 개발자</b></mark>

&ensp; 프로젝트를 진행하면서 작성한 코드의 대다수는 **직접 구성하고, 구현**해낸 코드입니다. 혹여 레퍼런스로 삼은 자료가 있다면, 원리를 이해하고 이를 체득하기 위하여 블로그에 일지 형식으로 남기고 있습니다.

&ensp; 이러한 작업 성향 덕분에 코드의 유지 보수 속도가 빠르고, 이슈가 발생했을 때 팀원과의 커뮤니케이션이 즉각적으로 이루어집니다.
"| markdownify }}

<p>
<p><br>
{{ "<mark><b>🎨 청사진을 그리는 개발자</b></mark>

&ensp; *무엇을?* 을 먼저 명확히 합니다. 하고자 하는 바를 코드 흐름과 유사한 흐름대로 잘게 쪼개어 정리합니다. 그 다음인 *어떻게?* 는 **슈도 코드**를 작성하는 것입니다. 복잡한 기능을 구현해야 할수록 펜을 들고 고민하는 성향입니다.
"| markdownify }}

<p>
<br><p>

{{ "<mark><b>🏃‍➡️ ❛모❜로 가지 않고 ❛바❜로 서울 가는 개발자</b></mark>

&ensp; 의도한 바대로 실행이 되지 않을 때, 가장 먼저 하는 일은 **원인에 접근**하는 것입니다. 이때, 디버깅을 적극 활용합니다. 때로는 사용한 엔진 함수의 소스 코드를 확인해 보기도 합니다. 우연에 의존한 문제 해결 방식을 철저히 베재하고 **체계적이고 논리적인 문제 해결**을 지향합니다.
"| markdownify }}

📝 <div class="hover-image-container"><a href="/unreal/ue-weapon-bone/" target=_blank> 문제 해결 경험 개발일지 - [UE] Weapon Bone이 있는 스켈레톤의 애니메이션</a>

</div><p><br>

- - -

<div class="two-columns">
<div class="column1">
{{ "# SKILL" | markdownify }}
</div>
<div class="column2">
{{ "

- Unity
- Unreal Engine
- C#
- C++
- Github
- SVN
- HTML
- CSS

" | markdownify }}
</div> 
</div>

- - -
<div class="two-columns">
<div class="column1">
{{ "# CAREER" | markdownify }}
</div>
<div class="column2">
{{ "
## <font color=ff9db9>Geniesoft</font>

- 직급 : 인턴
- 기간 : 2024. 10. 21 ~ 2024. 12. 13
- 담당 업무
  - 더스트 더비 (Dust Derby) AI 유지 보수 및 개선
  - 더스트 더비 (Dust Derby) 장난감 스테이지 콘텐츠 개발
  - 새 스테이지 기획 및 제작

" | markdownify }}
</div></div>

---

<div class="two-columns">
<div class="column1">
{{ "# PROJECTS" | markdownify }}
</div>
<div class="column2">
{{ "
## <font color=ff9db9>돌돌네이쳐 (Doll Doll Nature)</font>

<i>Unity를 이용하여, ‘Stardew Valley’ 게임을 오마주한 **2D 농사 시뮬레이션 게임** 개발</i>
<br><br>

#### Description

- 프로젝트 인원 : 1인 개발
- 사용 엔진 : Unity
- 기간 : 2023. 11. 18 ~ 2024. 01. 08 <mark>총 58 일</mark>
  <br><br>

#### What did I do

- 역할 : 전반적인 게임 구현
- 기여
    - 전체적인 게임 기획 및 개발
    - Tilemap을 이용한 맵 구성
    - 인벤토리 및 상점 구현
    - 농작물 정보를 이용한 Tilemap 변경
    - 농기구와 자연물끼리의 상호작용 구현
      <br><br>

#### Insights

1. 게임 개발의 난이도는 게임의 역동성보다도 플레이어와 사물, 맵의 상호작용과 거기서 파생되는 경우의 수에 의해 결정된다는 것을 깨달았습니다.
2. 게임 기능에 관련된 Manager 와 갈래로 뻗어 나오는 Script, Layer, Tag 의 기능과 역할의 부여 및 카테고리 설정을 기획 단계에서부터 짜임새 있는 구성과 기획을 실행하는 것이 작업의 혼선을
   줄이고 효율을 높인다는 것을 느꼈습니다.
3. Github을 이용한 프로젝트 관리법을 배우고, 편의성을 느꼈습니다.
   <br><br>

#### Skill

<mark>C#</mark> <mark>Unity</mark> <mark>Github</mark> <mark>Cinemachine</mark> <mark>Tilemap</mark> <mark>Rule
Tile</mark>
<br><br>

#### Game Play Video

" | markdownify }}

📽️ <a href="https://youtu.be/qDrX-Z9s8iE?si=9LiZh4lM9rZpLVuI" target=_blank>인게임 플레이 영상</a>
{{ "
- - -

## <font color=ff9db9>KIHON</font>

<i>Unreal Engine을 이용하여, ‘섀키로 : ‘섀도즈 다이 트와이스 게임을 오마주한 <b>3D 소울라이크 ARPG 게임</b> 개발</i>
<br><br>

#### Description

- 프로젝트 인원 : 5인 개발
- 사용 엔진 : Unreal Engine 5
- 기간 : 2024. 07. 08 ~ 2024. 09. 30 <mark>총 65 일</mark>
  <br><br>

#### What did I do

- 역할
  - 프로젝트 매니저 및 기획 · 개발 총괄
  - Player, 최종 보스 파트 전담
  - Github 리포지토리 관리
- 기여
    - Player 파트 전담
      - 애니메이션
      - 공격, 가드, 패링, 처형
      - 스탯
      - 각종 상호작용 등
  - 게임 시스템 관련한 매니저 구현
      - UI Manager
      - Sound Manager
      - Level Manager
      - Setting Manager 등
  - 게임 데이터 로드 및 세이브 기능 구현
  - 카메라 액션 무빙 제어, 카메라 락온 기능 구현
  - 보스 진입 시퀀스 제작
  - 최종 보스 AI 제작 등
        <br><br>

#### Insights

1. Github를 이용하여 브랜치 작업, 컨플릭트 처리, 커밋 컨벤션 등과 같은 협업 프로젝트 관리법 습득했습니다.
2. 데이트 로드 및 세이브 기능을 고려한 거시적 관점에서의 액터 설계를 하게 되었습니다.
3. 협업에서 타 팀원들의 코드 가독성을 높이기 위하여 의도가 담긴 주석을 작성하였습니다.
   <br><br>

#### Skill

<mark>UE</mark> <mark>Github</mark> <mark>Blueprint</mark> <mark>Sequencer</mark>
<br><br>

#### Game Play Video

" | markdownify }}

📽️ <a href="https://youtu.be/cv4Lt6bWeQ4?si=40HTDLb7joHvQ0fJ" target=_blank>인게임 플레이 영상</a>
{{ "
- - - 

## <font color=ff9db9>Do Not Late!</font>

<i>Unity 엔진을 이용한 **3D 캐쥬얼 레이싱 게임** 개발</i>
<br><br>

#### Description

- 프로젝트 인원 : 1인 개발
- 사용 엔진 : Unity
- 기간 : 2024. 01. 09 ~ 2024. 01. 24 <mark>총 16일</mark>
  <br><br>

#### What did I do

- 역할 : 전반적인 게임 구현
- 기여
    - 전체적인 게임 기획 및 개발
    - 전반적 기능 구현
    - Light 및 Shader 사용
      <br><br>

#### Insights

1. Cinemachine을 이용한 카메라 제어법을 배웠습니다.
2. 3D 환경에서의 Light 및 Shader 의 이용법을 배웠습니다.
3. NaviMesh Agent 을 심화 적용 하였습니다.
   <br><br>

#### Skill

<mark>C#</mark> <mark>Unity</mark> <mark>Github</mark> <mark>Cinemachine</mark> <mark>Shader</mark>
<br><br>

#### Game Play Video

" | markdownify }}
📽️ <a href="https://youtu.be/qDrX-Z9s8iE?si=NyU65NMI1zR_f1Ku&t=169" target=_blank>인게임 플레이 영상</a>
{{ "
- - - 

## <font color=ff9db9>❛Otter Story❜ Team Project</font>

<i>Unity 엔진을 이용한 **횡스크롤 액션 2D 게임** 개발 / 첫 팀 프로젝트</i>
<br><br>

#### Description

- 팀 구성 : 4인
- 사용 엔진 : Unity
- 기간 : 2023.09.11 ~ 2023.09.26 <mark>총 16일</mark>
  <br><br>

#### What did I do

- 역할 : 몬스터 및 아이템 관련해서 전담하여 구현했습니다.
- 기여
    - 몬스터 기본 움직임 및 애니메이션
    - 몬스터 AI 공격 패턴
    - 아이템 Prefab 생성 및 드랍
    - 아이템 획득 후 기능 구현
      <br><br>

#### Insights

1. 애니메이션 프레임 구간에서 이벤트 함수 사용 가능하다는 것을 배웠습니다.
2. 문제 해결을 위한 팀원 간의 활발한 의사소통으로 팀 단위의 프로젝트 성공을 경험하였습니다.
3. 게임 개발에 관련된 팀 프로젝트에서의 일정 관리 중요성을 느꼈습니다.
   <br><br>

#### Skill

<mark>C#</mark> <mark>Unity</mark>
<br><br>

#### Game Play Video

" | markdownify }}
📽️ <a href="https://youtu.be/SoNoUJA6L8Y?si=Yd-XGcMGLYM082Tz" target=_blank>인게임 플레이 영상</a>
{{ "

- - - 

## <font color=ff9db9>❛Animal Hunting Game❜ Team Project</font>

<i>Unity 엔진을 이용한 **쿼터뷰 형식의 FPS 게임** 개발</i>
<br><br>

#### Description

- 팀 구성 : 3인
- 사용 엔진 : Unity
- 기간 : 2023.10.10 ~ 2023.11.10 <mark>총 30일</mark>
- 교육 과정 중 예제 프로젝트 복습 차원에서의 게임 재구현
  <br><br>

#### What did I do

- 역할 : Player의 기본 움직임, Shooting 기능, Enemy와의 상호 작용을 담당하였습니다.
- 기여
    - Player의 기본 움직임 및 애니메이션 구현
    - Camera와 연동된 조작
    - Shoot 기능 구현
    - Scene과 Scene에서의 정보 전달 구현
      <br><br>

#### Insights

1. 게임 기획 단계에서 시스템 기획을 탄탄하게 해야 일을 반복하지 않는다는 걸 배웠습니다.
2. Manager, Layer, Tag 사용 시 팀원들과 원활하게 공유되어야 한다는 걸 배웠습니다.
3. 팀원 간의 소통의 중요성에 대해 깨달았습니다.
   <br><br>

#### Skill

<mark>C#</mark> <mark>Unity</mark>
<br><br>

#### Game Play Video

" | markdownify }}
📽️ <a href="https://youtu.be/cNaSxMAQjQc?si=BhgMc9HXjfSDMyil" target=_blank>인게임 플레이 영상</a>
</div> 
</div> 
- - -

<div class="two-columns">
<div class="column1">
{{ "# Education" | markdownify }}
</div>
<div class="column2">
{{ "

## <font color=ff9db9>The국제직업전문학교</font>

<i>C#, Unity를 이용한 게임 개발 및 에셋 디자이너 양성 과정 6기</i>
<br><br>

- 2023.07 ~ 2024.01 (6개월)
- 총 000 시간 과정
- 팀 프로젝트 2개, 개인 프로젝트 2개 완성 커리큘럼
- 성과 발표회 최우수 수상

<mark>C#</mark> <mark>Unity</mark> <mark>3ds Max</mark> <mark>Unreal</mark>
<br><br>

- - -

## <font color=ff9db9>GCC 사관학교</font>

<i>Unreal 엔진을 활용한 멀티 플랫폼 게임 개발자 양성 과정</i>
<br><br>

- 2024.03 ~ 2024.10 (7개월)
- 총 000 시간 과정
- C++, Blueprint
- 개임 프로젝트 1개, 팀 프로젝트 1개 완성 커리큘럼

<mark>C++</mark> <mark>Unreal Engine</mark> <mark>Blueprint</mark> <mark>Github</mark>
<br><br>

" | markdownify }}
</div>
</div>
</div>