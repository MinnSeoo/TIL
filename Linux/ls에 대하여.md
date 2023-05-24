# **ls**

Linux는 `ls` 명령어를 사용하여 디렉토리에 있는 내용을 확인한다.

(Window의 dir 명령어와 비슷하다.)

`ls` 을 입력하게 되면 **현재 디렉토리에 있는 내용을 출력**한다.

**기본형식 → ls [옵션] [파일 및 디렉토리]**

`ls` 명령어는 파일 및 디렉토리를 기본 알파벳 순서로 출력한다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7f061980-c34c-40b9-9a71-664c767c3df0/Untitled.png)

### **자주 쓰이는 옵션**

- `**-a` 옵션**
    
    → ****all의 줄임말로 모든파일(숨김 파일 및 디렉터리 포함) 형식을 출력.
    
    → `-l` 옵션과 조합하여 사용가능.
    
- `**-h`  옵션**
    
    → human의 약자로 사용자가 보기 좋은 형태의 단위로 출력한다.
    
    → K 킬로바이트, M 메가바이트, G 기가바이트 형태로 출력함.
    
- `**-l` 옵션**
    
    → long의 줄임말로 파일 출력 형식을 긴 목록 형식으로 출력
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ca064565-16ce-4b4e-823c-cab35e97278b/Untitled.png)
    

- **`-r`옵션**
    
    → reverse의 줄임말로 파일을 거꾸로 출력함.
    
- **`-S` 옵션**
    
    → 파일 크기별로 정렬하여 출력.
    
- **`-t` 옵션**
    
    → 최근 수정된 파일을 맨 위로 정렬시켜 출력한다.
    

### 알아두면 좋은 옵션

- **`-A` 옵션**
    
    → 지정된 디렉토리의 현재 디렉토리 와 상위 디렉토리 을 제외한 모든 파일 및 디렉토리를 출력
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/893becb5-34dd-4f25-bbaf-d1044dfd2807/Untitled.png)
    
- **`-b` 옵션**
    
    → 알파벳 순으로 파일 및 디렉토리 출력한다.
    
- **`-i` 옵션**
    
    → 각 파일의 인덱스 값을 첫 번째 열에 출력.
    

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ff1f57b0-9b6e-47a8-992b-7d2340f24dc0/Untitled.png)

- **`-m` 옵션**
    
    → 파일의 출력 형식이 디렉토리 및 파일을 쉼표로 구분한다.
    
- **`-n` 옵션**
    
    → 소유자와 소유자 그룹을 UDI와 GID로 출력한다.
    

- **`-R` 옵션**
    
    → 현재 위치 및 지정한 디렉토리, 경로에 저장한다.