# Git에 관한 내용정리

## **Git 이란?**<br>

***Git***은 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의<br>작업을 조율하기 위한 분산 **버전 관리 시스템**이며 **빠른 수행 속도**에 중점을 두고<br> 
있는 것이 특징이며 데이터의 무결성, 분산, 비선형 워크플로(작업 흐름)를 지원한다.
<br/><br>

## **Git은 꼭 필요할까..?**
<br>-&nbsp;&nbsp;다른사람과 협업할 필요 없이 혼자만의 프로그램을 개발하는 <br>&nbsp;&nbsp; 개발자가 아닌이상 **Git은 필수이다.**
<br><br>

## **그럼 Git을 사용하는 이유는 ? 🤔**

<br> **1 .효과적인 협업** <br>
&nbsp; &nbsp; - 팀 구성원이 서로의 작업에 쉽게 기여할 수 있으며 새로운 코드를 병합하고 <br>&nbsp; &nbsp; &nbsp; &nbsp;  프로젝트를 발전시킬 수 있다. <br><br>

**2. 효율적인 배포관리** <br>
&nbsp; &nbsp; - Git을 사용하면 언제든 새로운 내용들을 기록 하여 배포할 수 있으며 문제<br> &nbsp; &nbsp; &nbsp; &nbsp; 발생시에도 원하는 배포지점으로 돌아가 쉽게 수정을 할 수 있다.<br><br>

**3. 손쉬운 개발 및 테스트 환경 구축** <br>
&nbsp; &nbsp; - 간단한 명령어로 모든 파일이 정확이 업로드 되었는지 확인할 수 있으며 <br> &nbsp; &nbsp; &nbsp; &nbsp; 신규 프로젝트 진행시 기존 소스와 독립된 환경을 만들어주기 때문에 <br>
&nbsp; &nbsp; &nbsp; &nbsp;
새로운 서버 구축..등의 문제점을 간단하게 해결할 수 있다.<br>

  - 위 3가지는 Git이 가진 가장 **강력한 장점**이다. <br><br>
  

## **Git 용어 📖** <br>

- **Working Directory** : 개발자의 현재 시점으로 소스코드를 수정하며 개발하는 공간을 의미.<br><br>
- **Staging Area** : Working Directory에서 작업한 Repository에 전달하기 위해 파일들을 분류하는 공간. <br><br>
- **Index** : Staging Area를 의미 <br><br> 
- **Local Repository** : 로컬 저장소이며 작업한 파일들을 저장해두는 내부 저장소. <br><br>
- **Remot Repository** : 원격 저장소이며 인터넷으로 연결되어 있어 있는 외부 저장소. <br><br>
- **Branch** : Remote Repository의 현재 상태를 복사하여 master 브랜치와 별개의 작업을 진행할 수 있는 공간. <br><br>
- **Head** : 현재 작업중인 브랜치의 최근 커밋된 위치.<br><br>

## **Git 명령어 📝** <br>

  - **git init** : git을 초기화 시키며 새로운 git 저장소를 생성할 때 사용하는 명령어. <br><br>
  - **git add** : 수정된 소스코드들을 Staging Area로 전달. <br><br>
  - **git commit** : add된 모든 소스코드들을 Local Repository로 전달한다. <br><br>
  - **git push** : LocalRepository에서 변경이 발생한 파일들을 RemoteRepository로 전달한다. <br><br>
  - **git pull** : RemoteRepository에서 변경이 발생한 파일들을 Local PC에 있는 모든 공간에 전달한다. <br><br>
  - **git merge** : LocalRepository에서 변경이 발생한 파일들을 WorkingDirectory로 전달한다. <br><br>
  - **git branch** : 생성되어 있는 브랜치를 확인한다. <br><br>
  - **git branch {name}** : name의 이름으로 새로운 브랜치를 생성한다. <br><br>
  - **git checkout** {name}: 현재 브랜치를 변경할때 사용된다. <br><br>
  - **git status** : WorkingDirectory에서 수정이 발생된 파일들을 확인한다. <br><br>
  - **git clone** : RemoteRepository에 저장되어 있는 모든 파일들을 Local PC에 복사한다. <br><br>
  - **git reset** : 작업된 파일들을 특정 commit 위치로 리셋시킨다.




