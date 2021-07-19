# HTML

html 태그

* h1 ~ h6 : 제목(heading) 태그
* p : 단락(paragraph) 태그
* br : 줄바꿈(linebreak) 태그
* b : 글자 굵게
* i : 글자 이탤릭체
* u : 글자에 밑줄 
* s : 글자에 중간선
* a : 다른 문서로 이동할 수 있는 링크 생성 
    * href : "링크 url"
    * targrt : _self(현재 페이지에 표시), _blank(새로운 페이지에 표시)
* 의미없이 요소를 묶기 위한 태그(Container)
    * div : block-level
    * span : inline-level
* 리스트 요소
    * 자식으로 li 태그를 가짐
        * ul : 순서가 없는 리스트
        * ol : 순서가 있는 리스트
    * 자식으로 dt(용어 명), dd(용어 설명)를 가짐
        * dl : 용어, 정의를 표현할 때 사용
* 이미지 요소
    * img : 문서에 이미지 삽입
        * src : "이미지 경로"
            * 상대 경로 : 현재 웹 페이지를 기준으로 상대적인 이미지 위치
            * 절대 경로 : 실제 그 이미지가 위치한 곳의 전체 경로
        * alt : 이미지 대체 텍스트
        * width / height : 이미지 크기 지정
* 테이블 요소
    * table : 표를 나타냄
        * caption : 표의 제목
        * thead : 제목 행 그룹화
            * tr : 행
            * th : 제목 셀
        * tbody : 본문 행 그룹화
            * tr : 행
            * td : 셀
        * tfoot : 바닥 행 그룹화
            * tr : 행
            * td : 셀
        * rowspan : 셀 세로 방향 병합 (속성 값 : 병합할 셀의 개수)
        * colspan : 셀 가로 방향 병합 (속성 값 : 병합할 셀의 개수)
* 폼 요소
    * form : 폼 요소들을 감싸는 태그, 데이터들을 묶어서 실제 서버로 전송
        * action : 데이터를 처리하기 위한 서버의 주소
        * method : 데이터 전송 방식 (get : 주소창에 데이터 노출, post : 데이터 노출 X)
    * input : 서버에 데이터 전달
        * type 속성
        * text : 단순한 텍스트 입력 
            * placeholder : 입력 전 미리 화면에 노출하는 값
        * password : 암호와 같이 공개할 수 없는 내용 입력
        * radio : 중복 선택 불가한 항목 (남, 여)
            * name : 항목들을 그룹으로 묶어줌
            * checked : 초기에 선택될 항목 
        * checkbox :중복 선택 가능 항목 (취미)
            * name : 항목들을 그룹으로 묶어줌
        * submit : form의 값을 전송
        * reset : form의 값 초기화
        * button : 아무 기능이 없는 버튼
        * submit, reset, button의 경우 value 속성으로 버튼 이름 설정 
        * image : 이미지 삽입 가능한 버튼
    * select : 선택 목록 상자, 콤보 박스
        * option : 각 항목을 리스트 형태로 노출
            * selected : 초기 선택될 항목
    * textarea : 여러 줄의 텍스트 입력 가능
        * cols, rows : 가로, 세로 크기 조절
    * button : 버튼을 만들 때 사용, submit, reset, button 3가지 타입
    * label : label 클릭 시 해당 폼 요소 클릭한 것 처럼 동작, lable의 for 속성 값과 form 요소의 id 속성값을 동일하게
    * fieldset : 여러 개의 폼 요소를 구조화
        * legend : 폼 요소의 제목으로 fieldset 내부에 작성


콘텐츠 모델

    * metadata : 콘텐츠의 style, script을 설정하거나 다른 문서와의 관계 등의 정보를 포함하는 요소
        * head 태그 내에 들어가는 태그 (link, meta, script, style, title)
    * flow : 문서에 사용되는 대부분의 요소
        * 태그의 대부분이 해당
    * sectioning : heading과 footer의 범위를 결정하는 요소, 아웃라인
        * 문서의 구조와 관련된 태그 (aside, nav, section)
    * heading : 섹션의 헤더를 정의하는 요소
        * 제목 태그 (h1, h2, ... , h6) 
    * phrasing : 문서의 텍스트이며 문단 내부 레벨로 마크업하는 요소
        * a, b, i, br
    * embedded : 이미지, 비디오, 플래시 등의 외부 콘텐츠를 문서 내에 표현하는 요소
        * embeded 모델은 모두 phrasing 모델 (audio, img, video)
    * interactive : 사용자와 상호작용을 하는 요소
        * 대표적으로 form 요소들 (button, input, select, textarea)


시멘틱 마크업

    * 브라우저가 잘 이해할 수 있는 코드
    * 의미에 맞는 요소를 사용
    * 문서의 구조화
    * 예시) b(굵은) vs strong(중요한), i(기울어진) vs em(강조하는), s(중간선) vs del(삭제된)


BLOCK & INLINE

    * block level : 한 줄에 하나의 요소 표시
        * 일반적인 모든 요소 포함 (div, h1~h6, p, ul, li, table 등)
    * inline level : 한 줄에 여러개의 요소 표시
        * block level의 자식 요소 (span, a, i, img, em, strong 등)
    * inline level은 block level을 자식으로 가질 수 없으나, 예외 존재(a 태그)

