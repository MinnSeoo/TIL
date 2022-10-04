# **CSS Grid 내용정리**

## **Grid 란 ?**
&nbsp; **Grid**는 ``두 방향``(가로-세로) 레이아웃 시스템(2차원)으로
**Flex**보다 더 복잡한 레이아웃을 표현할 수 있다.<br>
&nbsp; Grid는 Flex와 마찬가지로 Container와 Item이 필요로하며 
부모 요소인 **div.container를** `Grid Containe`r라고 부르고<br>
&nbsp; 자식 요소인 **div.item**을 `Grid item`이라고 부른다.<br><br>

## **Grid Container Properties**
<br>&nbsp; **Grid container 속성**

- **display -** Grid container를 정의.
  
- **grid-template-rows -** 명시적 **행**의 크기를 정의.

- **grid-template-columns -** 명시적 **열**의 크기를 정의.

- **grid-template-area -** 영역의 이름을 참조해 템플릿 생성.
  
- **grid-row-gap -** 행과 행 사이의 간격을 정의.

- **grid-column-gap-** 열과 열 사이의 간격을 정의.

- **grid-auto-rows-** 암시적인 행의 크기를 정의.

- **grid-auto-columns-** 암시적인 열의 크기를 정의.

- **grid-auto-areas-** 영역이름을 참조해 템플릿 생성.

- **grid-auto-flow -** 자동 배치 알고리즘 방식을 정의.

- **align-content -** Grid contents를 ``수직``정렬.

- **justify-content -** Grid contents를 ``수평``정렬.

- **place-content -** **align-content**, **justify-content** 의
``단축``속성.

- **align-items -** ***Grid-item***들을 `수직`으로 정렬.

- **justify-items -** ***Grid-item***들을 `수평`으로 정렬.


- **place-items -** ***align-items***, ***justify-items***의 단축속성
<br><br>

## **Grid Item Properties**

&nbsp; **Grid item 속성**

- **grid-row-start -** Grid item의 행의 **시작** 위치 지정.

- **grid-row-end -** Grid item의 행의 **끝** 위치 지정.

- **grid-column-start -** Grid item의 **열(시작)** 위치 지정.

- **grid-ccolumn-end -** Grid item의 **열(끝)** 위치 지정.
  
- **grid-area -** 영역 **이름** 설정, ``grid-row`` 와 ``gird-column``의 단축속성.

- **align-self -** 단일 Grid item을 수직(열 축)정렬.
  
- **justify-self -** 단일 Grid item을 수평(행 축)정렬.

- **place-self -** align-self 와 place-self의 단축 속성.

- **order -** Gird item의 배치 순서 지정.

- **z-index -** Grid item의 쌓이는 순서를 지정. 





