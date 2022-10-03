# Flex에 관한 내용정리

## **Flex 란 ???**<br>
&nbsp;**Flex**는 웹페이지의 레이아웃을 잡을 때 사용하는 CSS 속성이며 **flex box, flexible box**라고도 부른다.<br>&nbsp;**Flex**는 **레이아웃** 배치기능에 중점을 맞추어 고안되었기 때문에 기존 속성들 보다 훨씬 더 수월하게<br>&nbsp;**퍼블리싱**이 가능하다. &nbsp; flexbox는 부모 요소인 ***div.container***를  ***flex container***라고 부르고,<br>&nbsp;
자식 요소인 ***div.item***들을 ***Flex Item***이라고 부른다.

## **Flex 속성**
&nbsp; **1) Container**에 적용하는 속성<br>
&nbsp; **2) Item**에 적용하는 속성<br><br>

## **Flex Container에 적용하는 속성들**
&nbsp; **display: flex; -** flex item을 <span style = "color :#2D3749;background-color:#fff5b1">**가로방향**</span> 으로 배치되며 자신이 가진 내용물의 <span style = "color :#2D3749;background-color:#fff5b1">**width**</span>만큼 공간을 차지하게 된다.<br>

&nbsp; **inline-flex -** container가 주변 요소들과 어떻게 어우러질지 결정하는 값이다. (inline-block처럼 동작한다.)<br>

&nbsp; **flex-direction -** item들이 배치되는 `축의방향`을 결정하는 속성이다.<br>
&nbsp; - ***row***(가로), ***row-reverse***(역순가로), ***column***(세로), ***column-reverse***(역순세로)<br>

&nbsp; **flex-wrap -** container가 더 이상 item들을 한 줄에 담을 여유 공간이 없을때 **`줄바꿈`**</span>을 어떻게 할지 결정하는 속성.<br>
&nbsp;  -***nowrap*** (기본값,줄바꿈 X), ***wrap*** (줄바꿈 O), ***wrap-reverse*** (줄바꿈 O ,item 역순배치), ***flex-flow*** (flex의 **방향**과 **줄바꿈**을 한번에 지정한다)<br>

&nbsp; **justify-content -** 메인축 방향으로 item들을 정렬하는 속성.<br>
- flex-start : item들을 시작점으로 정렬. (flex의 방향이 row일때는 왼쪽, column일 때는 위로 정렬)
  
- flex-end : item들을 끝점으로 정렬. (row - 오른쪽, column - 아래)
  
- center : item들을 가운데로 정렬.<br>
  
- space-between : item들 사이에 균일한 간격을 만들어준다.

- space-around : item들의 둘레에 균일한 간격을 만들어준다.

- space-evenly : item들의 사이와 양 끝에 균일한 간격을 만들어준다.

&nbsp; **align-itms -** 수직축 방향으로 item들을 정렬하는 속성.<br>
- stretch : item들이 수직축 방향으로 끝까지 늘어난다. (기본값)

- flex-start : item들을 시작점으로 정렬한다. (flex의 방향이 row - 위, column - 왼쪽)

- flex-end : item들을 끝으로 정렬. (row - 아래, column - 오른쪽)

- center : 가운데 정렬
  
- baseline : item들을 text-baseline 기준으로 정렬.

&nbsp; **align-content -** ***flex-wrap***이 설정된 상태에서 item들의 행이 2줄 이상 되었을 경우 ***수직축 방향*** 정렬을 결정하는 속성.<br><br>

## **Flex item에 적용하는 속성들**
&nbsp; **flex-basis -** Flex item의 기본 크기 설정
(flex의 방향이 ***row - 너비***, ***column - 높이***)<br>

&nbsp; **flex-grow -** item이 flex-basis의 값보다 더 `커질` 수 있는지 결정하는 속성.<br>

&nbsp; **flex-shrink -**  item이 flex-basis의 값보다 `작아질` 수 있는지 결정하는 속성.<br>

&nbsp; **flex -** ***flex-grow, shrink, basis***를 한번에 쓸 수 있는 **`축약`** 속성.<br>

&nbsp; **align-self -** 해당하는 item의 수직축 방향 정렬. (기본값으로 auto, align-items설정을 **`상속받음`**.)<br>

&nbsp; **order -** 각 item들의 시각적 나열 순서를 결정하는 속성.<br>

&nbsp; **z-index -** Z축 정렬 (숫자가 **`클 수록`** 위로 올라옴.)



