## **Python 웹 스크래퍼 sec 5 내용정리**

<br>

### **sec #5.0 ~ 5.9**
```python
# we work remotely에서 원하는 코드찾기
# Beautiful Soup는 코드안에서 매우 쉽게 검색 할 수 있다는 장점이 있음!
"""
def say_hello(name, age):
  print(f"Hello {"Minseo"} your age is {17} years old")

say_hello("minseo",17)  # 이 경우 순서가 중요함
say_hello(age = 17, name = "minseo") # 이 경우는 변수명을 앞에 적어줬기때문에 순서 상관 없음
"""
from requests import get
from bs4 import BeautifulSoup

base_url = "https://weworkremotely.com/remote-jobs/search?term="
search_trm = "python"

response = get(f"{base_url}{search_trm}")
if response.status_code != 200:
  print("Error")
else:
  results = []
  soup = BeautifulSoup(response.text, "html.parser")
  jobs = (soup.find_all('section', class_="jobs"))
  # python 데이터 구조, 즉 entity(개체)
for job_section in jobs:
  job_posts =(job_section.find_all('li'))  
  # section 태그 내부의 li들을 찾는다.
  job_posts.pop(-1)  # pop은 list에서 한 항목 삭제
  for post in job_posts:
    anchors = post.find_all('a')
    anchor = anchors[1]
    link = (anchor['href'])
    # a태그 내부에서 모든 span태그를 찾음.
    company, kind, region = anchor.find_all('span', class_=     "company")
    print(company, kind, region)
    title = anchor.find('span', class_='title')
    # find_all = list를 가져옴(여러개의 항목을 찾은 후 가져옴)
    # find = 결과를 가져옴 (1개의 항목만 찾음)
    print(company.string, region.string, title.string)
    # title_name.string -> string을 붙이면 태그 안의 텍스트를 줌.
    # -------------모든 데이터 얻음!!!-------------------
    job_data =  {
      'link' : f"https://weworkremotely.com{link}",
      'company' : company.string,
      'region' : region.string,
      'position' : title.string    
    }  
    results.append(job_data)  
    #.append -> result라는 list에 매번 추출한 job_data를 넣는다.
    
for result in results:
    print(result)
    print("////////////////")
```