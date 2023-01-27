## nomard coder - python으로 웹 스크래퍼 만들기 (~ #4)

변수 선언시 앞에  **def** 라는 키워드를 붙이고 뒤에는 **:** 을 붙임

return을 하게 되면 함수 종료됨

String 변수 사용시 앞에 **f** 키워드가 붙고   **{변수} 즉  중괄호 안에 변수명을 적어준다!** 

Make juice

```python
def make_juice(fruit):
  return f"{fruit} + 🥤"

def add_ice(juice):
  return f"{juice} + 🧊"

def add_sugger(iced_juice):
  return f"{iced_juice} + 🧂"

juice = make_juice("🍎")
cold_juice = add_ice(juice)
perfect_juice = add_sugger(cold_juice)

print(perfect_juice)
```

**input** 은 사용자 입력을 기다림  → C언어의 scanf같은 존재

## ex) user의 나이를 물어본 후 답받기

```python
age = int(input("How old are you"))
```

### random 함수

```python
from random import randint // 랜덤 함수 라이브러리 import 해 주기(int형을 사용함 여기선)
rndNum = randint(정수1,정수2) // 정수 1 ~ 정수 2 까지 범위의 랜덤의 숫자가 변수에 들어감 
```

<br>

## **Status code**
```python
### python casino (while문 사용, random함수 사용!)

from requests import get  # request 라이브러리 import

# list -> [], 튜플(tuple) -> (), 딕셔너리(dict) -> {변수명 : 값}

WebSites = (  # 튜플 -> 즉 값 변경 불가능
  "google.com", "https://airbnb.com", "twitter.com", "https://facebook.com",
  "instagram.com")

results = {}  # < - 딕셔너리

for website in WebSites:
  if not website.startswith("https://"):
    website = f"https://{website}"  #문자열 안에 변수를 넣음(f"")
  response = get(website)  #상태코드 얻음

  if response.status_code >= 200 or response.status_code <= 399:
    results[website] = "Ok"
  elif response.status_code >= 400 or response.status_code <= 499:
    results[website] = "Failed"

  elif response.status_code >= 500:
    results[website] = "Server is shutdown"

print(results)

# 대부분 사람들은 list, 튜플을 사용할때 변수명을 복수로 사용함!!
```