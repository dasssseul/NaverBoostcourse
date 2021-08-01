# CSS

## CSS 문법

    * 선택자
    * 속성
    * 값
    * 선언
    * 선언부
    * 규칙

## 선택자

    * 요소 선택자 : 가장 기본이 되는 선택자, 태그 선택자
    * 전체 선택자 : * 기호로 문서 내에 모든 요소 선택
    * class 선택자 : HTML 요소에 class 속성을 추가하여 사용
    * id 선택자 : HTML 요소에 id 속성을 추가하여 사용, 문서 내 유일한 요소에 사용
    * 속성 선택자 : 단순 속성, 정확한 속성값, 부분 속성값으로 선택
    * 문서 구조 선택자 
        * 자손 선택자 : 선택자 사이에 기호 없이 공백으로 구분
        * 자식 선택자 : 선택자 사이에 > 기호로 구분
        * 형제 선택자 : 선택자 사이에 + 기호로 구분
    * 가상 클래스 선택자 : 미리 정의해놓은 상황에 적용되도록 약속된 보이지 않는 클래스 (hover, first-child 등)
    * 가상 요소 선택자 : 문서에 존재하지 않는 요소에 내용이나 스타일 추가 (before, after, first-line 등)

## CSS 적용 방식

    * Inline : 해당 요소에 직접 스타일 속성을 이용해서 규칙들을 선언
    * Internal : 문서에 <style>을 활용
    * External : 외부 스타일 시트 파일을 이용

## 구체성

    * 선택자를 얼마나 명시적으로 선언했느냐를 수치화한 것
    * 구체성은 값이 높을수록 우선되어 적용
    * 0, 0, 0, 0 4개의 숫자 값으로 이루어짐
        * 0, 1, 0, 0 : 선택자에 있는 모든 id 속성값
        * 0, 0, 1, 0 : 선택자에 있는 모든 class 속성값, 기타 속성, 가상 클래스
        * 0, 0, 0, 1 : 선택자에 있는 모든 요소, 가상 요소
        * 전체 선택자는 0, 0, 0, 0을 가짐
        * 조합자는 구체성에 영향을 주지 않는다 (>, + 등)
    * 인라인 스타일 구체성 값은 1, 0, 0, 0
    * !important 키워드는 모든 구체성을 무시하고 우선권을 가짐

## 상속

    * 어떤 스타일 규칙이 특성 요소뿐만 아니라 그 자손 요소까지 적용되는 것
    * margin, padding, background, border 등 박스 모델 속성들은 상속되지 않음
    * 상속된 속성은 아무런 구체성을 가지지 못함

## 케스케이딩

    * 스타일 규칙들이 어떠한 기준으로 요소에 적용되는지를 정한 규칙
        1. 중요도와 출처(중요도 > 사용자 > 제작자 > 사용자 에이전트)
        2. 구체성 - 구체성이 높은 규칙 우선
        3. 선언 순서 - 뒤에 선언된 규칙일수록 우선


## 속성

    * 단위
        * 절대 길이 : 고정된 크기 단위, 다른 요소의 크기에 의해 영향을 받지 않음
            * px : 화면에서 고정된 크기를 가지지만, 장치의 해상도에 따라 상대적
            * pt : 인쇄물이나 워드 프로세서 프로그램에서 사용된 가장 작은 표준 인쇄 단위
        * 상대 길이 : 다른 요소의 크기나 폰트 크기, 브라우저 등의 크기에 따라 상대적으로 값이 변함
            * % : 부모의 값에 대해 백분율로 환산한 크기 (100%라면 부모의 값과 동일)
            * em : 폰트 사이즈를 기준으로 값을 환산 (1em = 16px)
            * rem
            * vw

    * 색상(color)
        * 색상 값 지정 방식
            * 색상명
            * 16진수 (검은색:#00000, 흰색:#ffffff)
                * 같은 수가 2개씩이면 세자리로 줄여서도 표현 가능
            * RGB (검은색:rgb(0, 0, 0), 흰색:rgb(255, 255, 255))
            * RGBA (투명도 설정 가능, 투명:0, 불투명:1)

    * 배경(background)
        * background-color : 배경 색상 지정
        * background-image : 배경으로 사용할 이미지의 경로 지정
        * background-repeat : 배경 이미지의 반복 여부와 방향 지정
            * repeat : x, y축 모두 반복
            * repeat-x : x축 방향으로만 반복
            * repeat-y : y축 방향으로만 반복
            * no-repeat : 반복하지 않음
        * background-position : 배경 이미지의 위치를 지정
            * 기본값 : 상단 왼쪽(left top)
            * left center
            * center bottom
            * right top 
        * background-attachment : 화면 스크롤에 따른 배경 이미지의 움직임 여부 지정
            * 기본값 : scroll
            * fixed : 뷰포트를 기준으로 고정, 스크롤에 영향을 받지 않음

    * 박스 모델(box model)
        * content : 요소의 실제 내용을 포함하는 영역
            * width : 너비
            * height : 높이
        * border : content를 감싸는 테두리 선
            * border-width : 두께
            * border-style : 종류
            * border-color : 색상
        * padding : content와 border 사이의 여백
            * padding 축약형의 경우 시계방향으로 선언
            * padding : [top] [right] [bottom] [left]
            * % 단위를 사용할 경우 가로축을 기준으로 움직임
            * 음수 사용 불가능
        * margin : border 바깥쪽의 영억, 다른 요소와 구별
            * margin 축약형의 경우 시계방향으로 선언
            * margin : [top] [right] [bottom] [left]
            * 음수 사용 가능
            * auto 
                * 가로축을 기준으로 정렬
                * margin : 0 auto -> 수평 중앙 정렬
                * width 값이 꼭 필요함 
            * margin collapse(마진 병합)
                * 인접한 두 개 이상의 수직 방향 박스의 마진이 하나로 합쳐지는 것
                * 두 요소의 상하 마진이 인접한 경우 더 큰 마진 값이 적용됨

    * 폰트, 텍스트 
        * typography
            * em : 폰트의 전체 높이 
            * ex : 해당 폰트의 영문 소문자 x의 높이 
            * baseline : 소문자 x를 기준으로 하단의 라인을 의미 
            * descender : 소문자에서 baseline 아래로 쳐지는 영역
            * asender : 소문자 x의 상단 라인 위로 넘어가는 영역
        * font-family : 글꼴을 지정하는 속성
            * family-name : 사용할 폰트의 이름, ','로 구분하여 여러 개 선언 가능
            * generic-family : family-name으로 지정된 글꼴 사용이 불가능할 경우, 브라우저가 대체할 수 있는 폰트가 필요한 경우 선택 가능
        * line-height : 텍스트 라인의 높이 의미, 행간 제어 
            * 타이포그래피 구조의 [em 박스] + [상하단의 여백]
        * font-size : 글꼴의 크기를 지정하는 속성
            * keyword : xx-small, x-small, small, large ...
            * length : px, em 등 고정 수치
            * % : 부모 요소의 font-size 기준의 퍼센트로 지정
        * font-weight : 글꼴의 굵기 지정
            * normal, bold, bolder, lighter, number
        * font-style : 글꼴의 스타일 지정 
            * normal, italic, oblique
        * font-variant : 글꼴의 형태 변형
            * small-caps : 소문자를 작은 대문자로 변형
        * font 속성의 축약형
            * font : style|variant|weight|size/line-height|family
            * font-size와 font-family는 필수 속성
        * webfont(@font-face) : 웹에 있는 글꼴을 사용자의 로컬 환경으로 다운로드하여 적용하는 속성
        * vertical-align : inline-level 요소의 수직 정렬을 지정
            * length : 요소를 지정한 길이 만큼 올리거나 내림, 음수 허용
            * % : 요소를 line-height를 기준으로 올리거나 내림, 음수 허용
            * keyword : baseline(기본값), sub, super, top, middle, bottom
        * text-align : inline-level 텍스트의 정렬 지정
            * left, right, center, justify(라인 양쪽 끝으로 붙여서 정렬)
            * block level 요소의 경우 margin을 이용해 정렬 (가운데 정렬 : 0, auto)
        * text-indent : 텍스트의 들여쓰기 지정
            * length : 문단의 첫 줄에 대한 들여쓰기, 음수 값 사용 시 왼쪽으로 이동
            * % : 텍스트를 포함하는 컨테이너 블록의 width를 기준으로 변환된 백분율 값으로 들여쓰기 
        * text-decoration : 텍스트의 장식 지정
            * 선의 위치 : none, underline, overline, line-through
            * 선의 스타일 : solid, double, dotted, dashed, wavy
        * 단어 관련 속성
            * white-space : 요소 안의 공백을 어떻게 처리할지 지정
            * letter-spacing : 글자 간의 간격을 지정
            * word-spacing : 단어 사이의 간격을 지정
            * word-break : 단어가 라인 끝에 나올 경우 어떻게 처리할지 지정
            * word-wrap : 요소를 벗어난 단어의 줄바꿈 지정
        