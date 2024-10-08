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
{{ "## 스스로 고민하고 실현해내는 것이 즐거운 게임 클라이언트 신입 개발자입니다."| markdownify }}
<br>
&ensp; 모 개발 회사 사무실에는 ‘어~?’ 를 금지하는
문구<div class="hover-image-container"><a href="#"><sup>[1]</sup></a><img src="\assets\images\posts_img\about/first.jpg" width="400"></div>
가 붙어 있다고 합니다. 개발자들의 밈(meme) 중에 만국 공통으로 유명한 밈은 ‘어? 이게 왜 되지?’, ‘어? 이게 왜 안 되지?’<div class="hover-image-container">
<a href="#"><sup>[2]</sup></a><img src="\assets\images\posts_img\about/second.png" width="400"></div>가 있습니다. 저의 ‘어?’ 는 <i><b>‘어? 이게 왜 (의도한 대로) 안 되지?’</b></i> 밖에 없습니다!
<br>
<p>
&ensp; 직접 로직을 짜고 실행하는 데에서 흥미를 느끼기에 코드 한 줄, 한 줄이 <u>①의미</u>가 무엇인지, 이 줄에서 어떤 <u>②역할</u>을 수행하는지, 이곳에 이 코드가 있어야 하는 <u>③이유</u>를 파악하고 있습니다.

&ensp; 이러한 성향으로 인해 문제 해결 능력이 향상되었고, 동료들과의 협업 시에도 효과적인 커뮤니케이션을 할 수 있게 되었습니다. 또한, 코드의 가독성과 유지보수성을 높이는 데에도 큰 도움이 되었습니다. 아래에는 그에 따른 효과에 대한 이야기를 구체적으로 해 보았습니다.
</p><br>
<p></p>
{{ "<mark><b>먼저 청사진을 그리는 개발자</b></mark>

&ensp; 코드를 짠다고 했을 때 가장 먼저 하는 일은 <b>원하는 의도를 잘 정리</b> 하는 것입니다. 의도를 구현하기 위해 세워야 할 로직은 의도를 구체화할수록 쉽게 접근할 수 있기 때문입니다. 특히 <U> 반복과 규칙, 분기점 </u> 같은 요소를 유념하고 있습니다.

&ensp; 그렇게 <i>무엇을?</i> 이 완성되면 다음은 <i>어떻게?</i> 입니다. 구현해야 할 로직이 복잡할수록 저는 슈도 코드 작성하는 것을 즐겨하는 편입니다. 자연어로 문장을 모아 한 흐름을 만듭니다. 그후에 한 문장마다 쪼갠 후, 컴퓨터의 언어로 번역하면 그 안에서 등장하는 숨은 명령을 찾아냅니다. 복잡한 기능을 구현해야 할수록 먼저 펜을 들고, 고민하는 성향입니다. 코드의 의미와, 역할, 이유를 아는 이유입니다.
"| markdownify }}
<br>

{{ "<mark><b>❛모❜로 가지 않고 ❛바❜로 서울 가는 개발자, 혈을 뚫어 주는 개발자</b></mark>

&ensp; 스스로 고민하여 코드를 짠다는 이유로 문제 해결을 할 때 의미없이 노드 핀을 여기저기 연결한다든가, 사용한 함수를 바꿔 본다든가 하는 일이 없습니다. 얻어 걸리는 식의 문제 해결을 지양하고 있습니다. 안 된다면 안 되는 이유가 분명 있을 거라고 생각하며, 문제에 당면하였을 때 가장 먼저 <b>*원인에 접근하는 편*</b>입니다.

&ensp; 그러한 성향 때문에 교육 기간 동안 강의를 진행하는 강사님이나 동기들에게 문제 해결 방법을 제시하는 일이 빈번하였습니다. 같은 문제로 오래 고민하고 있는 동기를 보면 같은 특징을 가지고 있었는데, 그것은 바로 컴퓨터를 의심하는 것이었습니다. 그럴 때마다 저는 매번 말합니다. 컴퓨터는 거짓말을 하지 않아! 의심해야 하는 것은 <i>내가 과연 컴퓨터에게 제대로 명령을 했는가</i>, 라고 충고합니다. 이를 확인할 수 있는 강력한 방법은 <u>디버깅</u>이며, 상대의 의도를 파악한 후 그에 맞게 디버깅할 포인트들을 알려 주는 식으로 접근합니다.
<p>&ensp;  이러한 해결 경험을 잊지 않고 복기, 공유하기 위하여 개발일지 형식으로 남기고 있습니다. 개발 일지를 작성할 때 가장 중요하게 생각하는 것은 <b>원인에 접근하는 근거</b>입니다.</p>
"| markdownify }}
📝 <div class="hover-image-container"><a href="/unreal/ue-weapon-bone/" target=_blank> 문제 해결 경험 개발일지 - [UE] Weapon Bone이 있는 스켈레톤의 애니메이션</a></div></div></div>

- - -

<div class="two-columns">
<div class="column1">
{{ "# SKILL" | markdownify }}
</div>
<div class="column2">
{{ "

- C# <mark>(4/5)</mark>
- C++ <mark>(3/5)</mark>
- Unity  <mark>(4/5)</mark>
- Unreal Engine <mark>(4/5)</mark>
- Github <mark>(4/5)</mark>
- HTML <mark>(2/5)</mark>
- CSS <mark>(2/5)</mark>

" | markdownify }}
</div> 
</div>

- - -


<div class="two-columns">
<div class="column1">
{{ "# Projects" | markdownify }}
</div>
<div class="column2">
{{ "

## <font color=ff9db9>돌돌네이쳐 (Doll Doll Nature)</font>

<i>Unity를 이용하여, ‘Stardew Valley’ 게임을 오마주한 농사 시뮬레이션 2D 게임 개발</i>
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

## <font color=ff9db9>Do Not Late!</font>

<i>Unity 엔진을 이용한 3D 캐쥬얼 레이싱 게임 개발</i>
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

<i>Unity 엔진을 이용한 횡스크롤 액션 2D 게임 개발 / 첫 팀 프로젝트</i>
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

<i>Unity 엔진을 이용한 쿼터뷰 형식의 FPS 게임 개발</i>
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