# **chmod**

---

리눅스에서 file을 사용해 할 수 있는 작업은 크게 3가지로 나뉜다.

- **파일에 저장된 데이터 읽기 (r = read)**
- **파일에 데이터 쓰기 (w = write)**
- **파일 실행 (x = execute)**

위의 이 3가지 권한을 **file을 소유한 사용자(user), 특정 그룹 (group)**, **그 외 사용자(others)**에 대해 
각각 지정할 수 있게 만들었다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/89ce5182-ceb1-480e-9ce0-03cd034c8c27/Untitled.png)

chmod 명령을 사용하여 file의 모드를 변경한다는 것은 file의 권한을 변경한다는 것과 동일한 의미를 가진다.

chmod의 기본 형태 

**chmod [OPTION] [MODE] [FILE]**

### **Option**

```markdown
-v : 모든 파일에 대해 모드가 적용되는 진단 메세지 출력

-f : 에러 메세지 출력 x

-c : 기존 파일 모드가 변경되는 경우만 진단 메세지 출력

-R : 지정한 모드를 파일과 디렉토리에 대해 재귀적으로 적용
```

### **Mode**

```markdown
u,g,o,a : 소유자(u), 그룹(g), 그 외 사용자(o), 모든 사용자(a) 지정.

+,-,=   : 현재 모드에 권한 추가(+), 현재 모드에서 권한 제거(-), 현재 모드로 권한 지정(=)

r,w,x   : 읽기(r), 쓰기(w), 실행(x)

X       : "디렉토리" 또는 "실행 권한(x)이 있는 파일"에 실행 권한(x) 적용.

s       : 실행시 사용자 또는 그룹의 ID 지정(s)

t       : 공유모드에서 제한된 삭제 플래그를 나타내는 sticky(t) bit.

0~7     : 8진수(octet) 형식 모드 설정 값.
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b4be3be6-1644-4c7c-90c9-27934fafef0c/Untitled.png)

- **파일을 소유한 사용자에 대해 읽고 쓸 수 있는 권한 지정.**
    
    → `chmod u=rw FILE`
    
- **파일이 속한 그룹이 실행할 수 있는 권한 추가.**
    
    → `chmod g+x FILE`
    
- **시스템의 모든 사용자가 읽을 수만 있는 권한 지정**
    
    → `chmod o=r FILE`
    
- **파일을 소유한 그룹과 그 외 사용자의 모든 권한 제거.**
    
    → `chmod go-rwx FILE`
    

파일 또는 디렉토리에 지정된 권한 확인 → `ls -l` 

### 8진수(octal)형식으로 파일 모드 지정 방법

앞서 `ls -l` 명령을 통해 현재 파일의 권한을 확인하는 방법을 알아보았다.
출력된 결과의 가장 첫 번째 항목을 통해 **사용자(u)**, **그룹(g)**, **그 외 사용자(o)**에 대하여
읽기(r), 쓰기(w), 실행(x) 권한을 확인할 수 있었다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/959e12fb-4401-477a-a590-7b2e3c1de8d2/Untitled.png)

**“8진수”** 값을 사용하는 방법은 각 권한을 8진수 형태의 숫자 값으로 변환하여 한번에 지정하는 방법이다. 즉, 위의 그림의 **“rwxrwxrwx”** 중 **“rwx”**를 하나의 8진수 값으로 변환한 다음, 이 값을 연속 세 개로 나열하는 것이다. 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/50126ece-afd9-481b-a2b4-7959bd089689/Untitled.png)

- 읽기(r) → 4
- 쓰기(w) → 2
- 실행(x) → 1
- 권한 없음(-) → 0

### **8진수 형식으로 파일 모드를 지정하는 방법**

- 모든 사용자가 일고 쓰고 실행할 수 없도록 지정
    
    → `chmod 000 FILE`
    
- 모든 사용자가 읽고 쓰고 실행할 수 있도록 권한 지정
    
    → `chmod 777 FILE`
    
- 소유자는 모든 권한, 그룹 및 그 외 사용자는 읽기와 실행만 가능.
    
    → `chmod 755 FILE`
    
- 소유자 및 그룹은 읽기 가능, 그외 사용자는 권한 없음
    
    → `chmod 440 FILE`
    

8진수 형식을 이용할 때는 MODE 파라미터로 전달되는 값이 파일의 권한에 그대로 적용되기 때문에 u, g, o, a 또는 =, +, - 등과 같이 사용할 수 없다.

### **chmod 명령 사용 예제**

```markdown
# 파일 소유 사용자에게 실행권한 추가.
$ chmod u+x FILE  

# 파일 소유 사용자에게 쓰기 권한 추가.
$ chmod u+r FILE

# 파일 소유 사용자에게 읽기, 쓰기, 실행 권한 지정.
$ chmod u=rwx FILE

# 파일 소유 사용자의 실행 권한 제거.
$ chmod u-x FILE

# 파일 소유 그룹에 쓰 권한 추가
$ chmod g+w FILE

# 파일 소유 그룹에 실행 권한 제거
$chmod g-x FILE

# 파일 소유 사용자 및 그룹을 제외한 사용자만 읽기만 가능.
$chmod o=r FILE
```