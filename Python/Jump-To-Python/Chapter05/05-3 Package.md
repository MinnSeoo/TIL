## **Package 란 ? ? ?**

파이썬에서 package란 관련 있는 모듈의 집합을 말한다. 패키지는 파이썬 모듈을 계층적(디렉토리 구조)으로 관리할 수 있게 해 준다.

파이썬 패키지는 디렉토리와 파이썬 모듈로 이루어진다.

아래  img는 이 책에서 가상의 game 패키지 구조를 따라 만들어보았다

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8ee4bd27-c573-4822-99c6-59a96e23d7ef/Untitled.png)

game, graphic, play, sound는 디렉토리이고, 확장자가 .py인 파일은 파이썬 모듈이다.

이 중에서 game 디렉토리가 이 패키지의 루트 디렉토리이고 나머진 graphic, play, sound는 서브 디렉토리이다.

<br>

## **패키지 만들기**

---

각각의 디렉토리에  __[init.py](http://init.py)__ 파일을 만들어 준다. (일단 파일만 생성하고 내용은 비워두기!)

(+ 나는 각 디렉토리에 같은 명의 파일이 있을경우 헷갈릴것 같아서 생성자 파일 명 앞에 각 디렉토리의 키워드를 적어줬다.)

그리고 나서 [echo.py](http://echo.py) 파일 안에 아래와 같은 코드를 작성해 준다.

```python
# echo.py
def echo_test():
	print("echo")
```

그리고 나서 [render.py](http://render.py) 파일 안에 아래와 같은 코드를 작성해 준다.

```python
# render.py
def render_test():
	print("render")
```

그 다음 꼭 해줘야 하는 작업이 있다. 바로 PYTHONPATH 환경변수에서 game 패키지를 참조할 수 있도록 해당 디렉토리를 추가해야한다.

```markdown
# 현재경로 위치
  `minnseoo@jeongminseoui-MacBookPro python-test**`**

# 불러올 패키지의 경로
  `export PYTHONPATH=cd/study/python-test/game`
```

PYTHONPATH 환경변수에 불러올 패키지의 경로를 추가해 준다. (python-test 까지만 경로 지정해도 됨.)

> 이번 실습에서는 vscode에서 실행하지 않고 파이썬 인터프리터를 사용하여 실습을 진행하겠다. (vscode 나 다른 IDLE에 실습을 진행하면 오류가 많이 발생하기 때문.)
> 

## **패키지 안의 함수 실행하기**

이제 패키지를 사용하여 위에서 생성한 [echo.py](http://echo.py)와 [render.py](http://render.py) 파일 안의 함수들을 실행해 보겠다.

패키지 안의 함수를 실행하는 방법에는 총 3가지가 있다.

### **[ 1 ] echo, render 모듈 import**

```python
# echo.py 파일 안 함수 실행하기
>>> import game.sound.echo
>>> game.sound.echo.echo_test()
echo

>>> import game.graphic.render
>>> game.graphic.render.render_test()
render
```

### **[ 2 ] echo, render 모듈이 있는 디렉토리까지 from … import**

```python
# from ... import 사용 
# echo.py 파일 안 함수 실행하기
>>> from game.sound import echo
>>> echo.echo_test()
echo

# rander.py 파일 안 함수 실행하기
>>> from game.graphic import render
>>> render.render_test()
render
```

### **[ 3 ] echo, render 모듈의 함수들을 직접 import**

```python
# echo.py 파일 안 함수 import 
>>> from game.sound.echo import echo_test
>>> echo_test()
echo

# render.py 파일 안 함수 import
>>> from game.graphic.render import render_test
>>> render_test()
render
```

echo와 render 모듈의 각각의 함수를 직접 import하여 실행한다.

### **Plus, 잘못된 예**

```python
>>> import game
>>> game.sound.echo.echo_test()

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: module 'game' has no attribute 'sound'
```

위와 같이 echo_test 함수를 사용하는것은 불가능하다. 왜 그럴까???

import game을 수행하면 game 디렉토리에 **__init__.py**에 정의한 내용만 참조할 수 있기 때문이다.

또 다른 잘못된 예를 살펴보자

```python
>>> import game.sound.echo.echo_test

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'game.sound.echo.echo_test'; 
'game.sound.echo' is not a package

```

도트 연산자(.)를 사용해서  `import a.b.c` 처럼 import 할 때 가장 마지막 항목인 c는 반드시 모듈 또는 패키지여야만 한다.

<br>

## **__init __.py의 용도**

`__init.py__` 파일은 해당 디렉토리가 패키지의 일부임을 알려 주는 역할을 한다. 만약 game, sound, graphic 등 패키지에 포함된 디렉토리에 `__init.py__` 파일이 없다면 패키지로 인식되지 않는다.

(python 3.3 ver 부터는 `__init.py__` 파일이 없어도 패기지로 인식하지만, 하위 ver 호환을 위해서 `__init.py__` 파일을 생성하는 것이 안전한 방법이다.)

또한, `__init.py__` ****************파일은 패키지와 관련된 설정이나 초기화 코드를 포함할 수 있다. 그리고 다양한 방법으로 활용이 가능한데 아래와 같은 예제를 보며 살펴보겠다.

### **패키지 변수 및 함수 정의**

패키지 수준에서 변수와 함수를 정의할 수 있다. 예를 들면, game 패키지의 `__init.py__` 파일에 공통 변수나 함수를 정의할 수 있다.

```python
>>> import game   # game 패키지를 import 한다.
>>> print(game.VERSION)  # game 패키지의 VERSION 변수를 출력하겠다. 
3.5

>>> game.print_version_info()  # game 패키지 안의 함수를 불러온다.
The version of the game is 3.5.
```

### **패키지 내 모듈을 미리 import**

`__init.py__` 파일에 패키지 내의 다른 모듈을 미리 import하여 패키지를 사용하는 코드에서 간편하게 접근할 수 있게 한다.

`__init.py__` 파일에 `from .graphic.render import render_test` 코드를 추가한 후 파이썬 인터프리터를 실행시켜 아래와 같은 코드를 입력해 render 파일안의 render_test 함수를 실행시킨다.

```python
>>> import game
>>> game.render_test()
render
```

### 패키지 초기화

`__init.py__` 파일에 패키지를 처음 불러올 때 실행되어야 하는 코드를 작성할 수 있다. 예를 들면 db 연결이나 설정 파일 로드와 같은 작업을 수행할 수 있다.

`__init.py__` 파일에 패키지 초기화 코드를 작성해 준다. 

```python
print("Initializing Game . . .") 
```

이렇게 하면 패키지를 처음 import 할 때 초기화 코드가 실행된다.

```python
>>> import game
Initializing game . . .
```

단, 초기화 코드는 한 번 실행된 후에는 다시 import를 수행하더라도 실행되지 않는다는 점을 유의하자.

### **__all__**

```python
>>> from game.sound import *
Initializing game ...

>>> echo.echo_test()
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
NameError: name 'echo' is not defined
```

위 코드를 보면 game 디렉토리의 sound 패키지의 모든것을 import해 와서 echo 패키지 안의 test 함수를 실행시키려고 했다. 근데 echo라는 이름이 정의되지 않았다는 오류가 발생하였다. 

위 처럼 특정 디렉토리 모듈을 `*` 를 사용하여  import할 때는 다음과 같이 해당 디렉토리의 `__init__.py` 파일에 `__all__` 변수를 설정하고 import할 수 있는 모듈을 정의해야한다.

```python
# sound/__init__.py 에 아래 내용 추가해 주기
__all__ = ['echo']
```

여기에서 `__all__` 이 의미하는 것은 sound 디렉터리에서 `*` 를 사용하여 import할 경우, 이곳에 정의된 echo 모듈만 import된다는 의미이다.

### **relative 패키지**

---

만약 graphic 디렉토리에 [render.py](http://render.py) 모듈에서 sound 디렉토리의 [echo.py](http://echo.py) 모듈을 사용하고 싶은 경우엔 render.py 파일에 다음과 같은 코드를 추가해 주면 된다.

`from game.sound.echo import echo_test()` 

수정한 후 다음과 같이 실행해 보겠다.

```python
>>> from game.graphic.render import render_test
Initializing game ...
>>> render_test()
render
echo
```

위 예제처럼 전체 경로를 사용하여 import할 수도 있지만, 다음과 같이 relative하게 import 하는 것도 가능하다.

```python
# render.py
from ..sound.echo import echo_test # 코드 추가

def render_test():
    print("render")
    echo_test()
```

`from ..sound.echo import echo_test` 에서 `..` 은 [render.py](http://render.py) 파일의 부모 디렉토리를 의미한다.

따라서 [render.py](http://render.py) 파일의 부모 디렉토리는 game이므로 위와 같은 import가 가능한 것이다.

(+ `.` 은 현재 디렉토리를 의미한다.)