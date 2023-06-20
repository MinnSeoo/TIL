# **한시간만에 Nodejs 백엔드 기초 끝내기**

`npm init` - package.json을 만드는 명령어, 보통은 새로운 프로젝트나 패키지를 만들 때 사용된다.

<br>

**[package.json]** 

- 설치된 모듈들을 정리해주는 메모장 같은 역할을 한다.
- 현재 프로젝트에 대한 정보를 저장하는 곳 이다. (주로 관리를 깔끔하게 하기 위해 사용된다.)
- 프로젝트의 root 디렉토리에 저장하며 애플리케이션의 종속성 및 기타 정보를 저장한다.
- 파일 내의 각 정보는 기본적으로 key-value 형태로 저장된다.

<br>

**[package-lock.json]**

- package.json의 정보가 부족하기 때문에 package-lock.json에 더 정확하게 표시되어 있다.
- node_moudles의 구조나 package.json이 수정 및 생성될 때 당시 의존성에 대한 정확하고 구체적인 정보를 품고 자동으로 생성된다.

<br>

`npm install figlet` - figlet이라는 모듈을 설치하겠다.

`npm uninstall figlet` - figlet이라는 모듈을 삭제하겠다.

<br>

**Express란?** 

프론트엔드 화면에서 어떤것을 클릭 했을때 백엔드로 requset(요청)을 보냈을때 requset를 받아서

그에 맞는 동작을 수행 및 처리하고 response를 프론트엔드로 돌려주는 역할.

(한마디로 요청에 따른 응답을 해 주는 역할.)

<br>

**HTTP 메소드란?**

클라이언트와 서버 사이에 이루어지는 request와 response 데이터를 전송하는 방식을 말한다.

<br>

**Routing 이란?**

nodejs에서 Routing이란 특정한 HTTP 요청 메소드(GET, POST)인 특정 엔드포인트에 대한 클라이언트 요청에 애플리케이션이 응답하는 방법을 결정하는 것.

ex) youtube 웹 사이트를 들어가면 [`youtube.com`](http://youtube.com) 이라는 default 라우팅 주소값이 존재한다. 이때 검색창에 nodejs 입력하고 검색하게 되면 [`youtube.com/watch](http://youtube.com/watch) 채널명` 이런식으로 주소값이 변경되게 된다. (한 마디로 라우팅 값에 따라서 user에게 보여지는 HTML 페이지가 달라지게 된다.)

<br>

**CallBack 함수란?**

다른 코드의 인수로서 넘겨주는 실행 가능한 코드이다.