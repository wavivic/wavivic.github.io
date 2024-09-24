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

&ensp;개인 프로젝트를 만들면서 유일하게 사용했던 기능 패키지인 Korean Typer의 코드 리뷰를 하고자 한다. 개인 프로젝트에서 비교적 부드러운 다이얼로그 효과를 위하여 사용한 패키지다.

![](\assets\images\posts_img\koreanTyper\dialogue.gif)
<sup><b>▲ '돌돌네이처'에서 사용된 Korean Typer를 활용한 Dialogue </b></sup>

&ensp;'안' '안녕' '안녕하' '안녕하세' '안녕하세요' char 인덱스를 순차적으로 출력하는 방법보다도 'ㅇ' '아' '안' '안ㄴ' '안녀' '안녕' 과 같이 음절 단위의 완벽한 타이핑 효과를 원했다.

&ensp;후술할 배경 지식이 부족했던 탓에 직접 만들 생각을 하지 못하였고 서치로 찾게 된 패키지를 이용하였다. 충분한 코드 리뷰 후에 이 포스트를 게시한다.

- - -

### 🍥 배경 지식
<i>- 유니코드에 대해 알아보자!</i>
<br>

#### <mark>언어별 문자열을 처리 방식</mark>
> - C# : Unicode
> - C++ : ASCII

&ensp;따라서 본 스크립트에서는 아래와 같은 <u><b>Unicode(유니코드)</b>의 특징을 이용</u>하였다.

<br>

#### <mark>Unicode에서의 한글 구조</mark>
- 한글 음절이 **총 11,172개**가 존재함.
- 한글 음절 문자는 <mark>가(44032)</mark>부터 시작.
- 음절 문자는 초성, 중성, 종성으로 이루어져 있고, 유니코드에서 **분해 가능**.
  - 초성 : 19자
    - ㄱ, ㄲ, ㄴ, ㄷ, ㄸ, ㄹ, ㅁ, ㅂ, ㅃ, ㅅ, ㅆ, ㅇ, ㅈ, ㅉ, ㅊ, ㅋ, ㅌ, ㅍ, ㅎ
  - 중성 : 21자
    - ㅏ, ㅐ, ㅑ, ㅒ, ㅓ, ㅔ, ㅕ, ㅖ, ㅗ, ㅘ, ㅙ, ㅚ, ㅛ, ㅜ, ㅝ, ㅞ, ㅟ, ㅠ, ㅡ, ㅢ, ㅣ
  - 종성 : 28자
    - 없음, ㄱ, ㄲ, ㄳ, ㄴ, ㄵ, ㄶ, ㄷ, ㄹ, ㄺ, ㄻ, ㄼ, ㄽ, ㄾ, ㄿ, ㅀ, ㅁ, ㅂ, ㅄ, ㅅ, ㅆ, ㅇ, ㅈ, ㅊ, ㅋ, ㅌ, ㅍ, ㅎ

<br>

#### <mark>유니코드에서의 한글 분해 공식</mark>
> U = (초성 인덱스 * 588) + (중성 인덱스 * 28) + 종성 인덱스 + 44032

&ensp;위 공식을 활용하여 초성, 중성, 종성의 인덱스 값을 각각 구하는 것도 가능하다.

- 초성 인덱스 : ( U - 44032 ) / 21 * 28
- 중성 인덱스 : (( U - 44032 ) / 21 * 28 ) / 28
- 종성 인덱스 : ( U - 44032 ) % 28

- - -
### 🍥 코드 구조

```
public static int GetTypingLength (this string str) {

  int result = 0;
            
  for (int index = 0; index < str.Length; index++)
  {
    if (isSpecialKorean(str[index]))
    {
        result += 2; continue;
    }
    else if ((int)str[index] < (int)'가' || (int)str[index] > (int)'힣')
    {
        result += 1; continue;
    }
                
    int wordIntValue = (int)str[index] - (int)'가';
    int korean2ndWord = ( ( wordIntValue ) % ( Korean3rdWordList.Length * Korean2ndWordList.Length ) ) / Korean3rdWordList.Length;
    int korean3rdWord = ( wordIntValue ) % Korean3rdWordList.Length;


    result++;

    switch (korean2ndWord)
    {
        case 9: case 10: case 11: case 14: case 15: case 16: case 19:
          result += 2; break;
        default:
          result += 1; break;
    }

    switch (korean3rdWord)
    {
        case 3: case 5: case 6: case 9: case 10: case 11:
        case 12: case 13: case 14: case 15: case 18:
          result += 2; break;
        case 0: break;
        default: result += 1; break;
    }
  }
    return result;
}
```
        
1. **음절 단위로 쪼개어 총 몇 번의 출력이 있어야 하는지 길이 확인**
   - 반복문을 총 몇 번 돌릴 건지 알기 위함으로 가장 먼저 선행되어야 함.
   - 유니코드의 한글 분해 공식으로 각각 인덱스를 도출하여 총 출력 회수를 결정할 수 있음.
   - <mark>비정상 한글</mark>
     - 불완전한 한글에 두 번 입력해야 하는 문자인지 (ㄳ, ㄻ, ㄼ, ...) +2
     - 가 ~ 힣 사이에 있지 않은 문자인지 (특수문자, 영어, 숫자, ㄱ, ㅏ, ...) +1
   - <mark>정상 한글</mark>
     - 초성
       - 무조건 +1
     - 중성
       - ㅘ, ㅙ, ㅢ와 같은 중성 +2
       - 그 외 +1
     - 종성
       - ㄳ, ㄻ와 같은 종성 +2
       - 종성이 없음 +0
       - 그 외 +1
2. **한 글자 당 쪼개어서 초성, 중성, 종성(완전 출력) 분해 후 그중 어떤 걸 출력해야 하는지 확인. 결과값 리턴.**
   - 한 글자씩 확인하여 바로 출력 or 초, 중, 종으로 쪼개야 하는 완전한 글자인지 확인.
     - 불완전하지만 두 번 입력해야 하는 문자 (ㄳ, ㄻ, ㄼ, ...)
     - 가 ~ 힣 이외의 문자 (ㄱ, A, 1, ▲, ...)
     - 완전한 글자
       - 초, 중, 종성으로 분해
       - 경우의 수 중 최대 입력 회수는 5회

- - -
### 🍥 마치며
&ensp;C#이 유니코드로 문자를 처리하고, 유니코드로 음절 하나하나 분해할 수 있단 배경지식이 있었다면 고민해서 결국 구현해낼 수 있었던 문제였던 것 같아 개인적인 아쉬움이 있다. 조합할 수 있는 재료가 있어야 결과물도 다양할 수 있음을 깨닫게 되었다. 해당 스크립트의 원리는 충분히 숙지가 되었으니, 다음에 이런 다이얼로그 이펙트를 줘야 하는 상황이 오면 충분히 구현해낼 수 있으리라 생각한다.

&ensp;또한, 배포자분께서 하나하나 정성스런 주석이 있어서 리뷰가 쉬웠고, 나 또한 툴을 만들어 배포하게 된다면 이와 같이 꼼꼼한 주석을 달아서 편의를 도와야겠단 생각이 들었다.
- - -
### 🍥 Reference

[Korean Typer - KimYC1223 - Unity Asset Store](https://assetstore.unity.com/packages/tools/localization/koreantyper-232949)