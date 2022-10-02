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
&nbsp; **flex-direction -** item들이 배치되는 축의 방향을 결정하는 속성이다.<br>
&nbsp; - ***row***(가로), ***row-reverse***(역순가로), ***column***(세로), ***column-reverse***(역순세로)  

