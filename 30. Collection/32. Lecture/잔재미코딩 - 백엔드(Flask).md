---
collection:
  - 📼Lecture
---
# 1_understand_fullstack

## 0. 풀스택 서비스 개발 목표

### 목표
- 최종 목표: 
	1. 나만의 풀스택 서비스 개발
	2. 자유자재로 다양한 기술을 익히고 활용할 수 있는 기본기 쌓기
	3. 혼자서도 서비스 개발이 가능한 테크트리
  
### 원칙

1. 가급적 쉬운 기술 사용
2. 최신 기술만 사용
3. 다른 기술과 연결되어 있지 않고, 학습곡선이 높기만한 프레임워크는 배제
4. 학습곡선까지 포함해서, 높은 생산성을 가진 기술 사용
5. 단계별 난이도 고려
6. <b>프로토타입이 아니라, 실제 상용화 수준으로 개발</b>

### 학습 곡선 (러닝 커브)
- 다양한 기술을 익힐 때에는 단계가 있음
- 각 기술마다 학습 곡선 (러닝 커브)가 있음
- [러닝 커브](https://www.google.com/search?q=programming+learning+curve+python+java&tbm=isch&ved=2ahUKEwiI3v-_jOzoAhUFfN4KHSD7CGUQ2-cCegQIABAA&oq=programming+learning+curve+python+java&gs_lcp=CgNpbWcQAzoECAAQHjoGCAAQCBAeUMHKAVi02AFgtNkBaABwAHgAgAFwiAHyCZIBBDAuMTKYAQCgAQGqAQtnd3Mtd2l6LWltZw&sclient=img&ei=h92XXsj-CoX4-Qag9qOoBg&bih=977&biw=1920&rlz=1C5CHFA_enKR883KR883#imgrc=lParFoOQXrDjwM)
- 예:
	- 데이터베이스를 처음 익히려면 SQL을 먼저 익혀야 함
	- 회사에서 오라클(대규모 금융 시스템등에서 사용) 데이터베이스를 쓴다고, 오라클 데이터베이스를 익히면서, 복잡한 오라클 특화 기능을 익히면 SQL, 오라클 둘다 익히는데 큰 어려움을 겪음
	- 실제 자신만의 서비스 개발에도 아무 도움이 안됨


> 낮은 학습 곡선의 기술을 선택한 후, 필요에 따라 높은 학습 곡선을 신중히 선택해야, 원하는 기간 내에 개발이 가능함 <br>
> 유행하는 기술은 수시로 달라짐, 다양한 기술 경험을 쌓는 것이 좋음


### 스타트업 개발 프로세스
- 적은 리소스로 짧은 기간에 고객 반응 확인
- **매해 변경되는 기술 트렌드에 따라 최근 사용을 고려할만한 기술로 이미지를 업데이트하였습니다**

<center><img src="https://davelee-fun.github.io/fixeddata/abtest_process.png"></center>

## 1. 프레임워크란?
- 프레임(Frame, 틀) + 워크(work, 일하다)
  - 미리 만들어진 틀을 가지고 일하다.
<table>
    <tr>
        <td><img src="https://www.fun-coding.org/style/images/ads/lego_frame.jpg"></td>
        <td><img src="https://www.fun-coding.org/style/images/ads/lego_set.jpg"></td>
    </tr>
</table>

#### 템플릿 코드: 크롤링(타이틀)
- 사용법
	- crawling_template(웹주소, css selector)

#### 크롤링 프레임워크를 만들고, crawling_template() 함수를 제공 
- 장점: 크롤링 원리를 몰라도 크롤링 가능
- 단점: 제공하는 기능 외에는 사용 불가, 해당 함수 사용법을 잘 알아도, 프로그래밍 실력이 늘거나, 다른 기술을 익힐 때, 시너지가 없음


```python
import requests
from bs4 import BeautifulSoup

def crawling_template(url, css_selector):
    return_data = list()
    res = requests.get(url)
    soup = BeautifulSoup(res.content, 'html.parser')
    datas1 = soup.select(css_selector)
    for item in datas1:
        return_data.append(item.get_text())
    return return_data
```

### Why flask? : 가장 짧은 시간에 익히고, 가장 빠르게 구현할 수 있음!
- 백엔드 기술을 처음 익히는데 적합
- 파이썬을 사용하므로, 다양한 파이썬 라이브러리 활용 가능함 (확장성이 매우 큼)
- 처음 익힐 시에는 복잡도를 낮춰야 함
	- 새로운 언어 + 처음 익히는 백엔드 조합은 복잡도가 훨씬 높아져서, 아무것도 익힐 수 없음
- flask 로 백엔드를 익히면, 기본적인 백엔드 기술에 대해 이해도가 높아지고, 다른 기술을 익히는데 도움이 됨
	- Rest API, CORS, 데이터베이스 연결, MVC 등 가장 기본적인 기술을 다룰 수 있으며, 이는 다른 언어/프레임워크에 그대로 적용 가능
	- 백엔드 이해와 구현 경험을 기반으로 JAVA Spring/Go 등 다른 언어로 구현을 대체하면 빠르게 다양한 기술을 익힐 수 있음

>*잔재미코딩 Dave Lee 추가 의견*
이 강의는 백엔드 기술을 처음 배우는 분들이 파이썬을 통해 쉽게 백엔드를 익히고 활용할 수 있도록 설계되었습니다. 백엔드는 개발자 수준의 IT 역량이 필요하기 때문에, 파이썬 중급 기술과 백엔드 기술을 함께 다루어 개발자 역량을 쌓고, 백엔드의 높은 진입장벽을 가장 쉬운 방법으로 극복할 수 있도록 했습니다. 
다만, 백엔드 기술을 배우려면 객체지향 프로그래밍(OOP) 기법에 익숙해야 하지만, OOP는 내용이 방대하고 본 강의 주제와 거리가 있어 강의 내에서 다루지 않습니다. 따라서 OOP에 익숙하지 않은 분들은 본 강의와 함께 다음 강의 자료 모음에서 <b>파이썬과 객체지향 프로그래밍 챕터</b> 전 문서를 정독하신 후에 본 강의를 들으시는 것을 추천드립니다.
또한, Flask를 배우면 비슷한 문법으로 FastAPI도 바로 익히고 활용할 수 있습니다. FastAPI는 Flask와 구조 및 문법이 유사하면서도 성능이 더 뛰어나니, 강의 수강 후 FastAPI도 함께 살펴보시면 좋습니다. Flask와 FastAPI를 비교하며 학습하면 두 기술의 유사성과 차이점을 이해하고, 새로운 기술에 적응하는 개발자적 접근법을 익힐 수 있습니다.

### 같은 파이썬 기반인데, Django를 선택하지 않은 이유
- 학습곡선이 높고, 다른 기술과 연결되어 있지 않음
  - 즉, 이 기술의 사용법을 익힌다고 해서, 다른 기술등을 익히는데 도움이 안됨 
    - Django 함수 사용법만 익히는 것이므로, 다른 언어/프레임워크에 적용 안됨
  - <b>Django 만</b> 잘하는 개발자를 채용하는 거의 없다고 봐야함
    - 비즈니스 변화에 따라 다양한 기술을 빠르게 익히고 활용할 수 있는 개발자를 원함
    
> 기술 트랜드가 수시로 변화하므로 최근 글로벌로 사용하는 백엔드 기술 기반 공식 이미지도 공유드립니다

<img src="https://davelee-fun.github.io/fixeddata/framework2023.png">

## 프론트엔드와 백엔드 기본 구성
- 백엔드는 다양하게 구성 가능하고, architecturing 을 할 수 있음
- 주로 동시 접속자 수 규모에 따라, 변경 
<img src="https://www.fun-coding.org/00_Images/fullstack_web.jpg">

## 2. 웹서비스 개발과 파이썬 flask 를 활용한 웹서비스 개발
* 넓게 큰 그림으로 이해하는 웹 서비스 개발 동향
	- 1세대: USER ---- INTERNET --- WEB SERVER (Read static HTML)
	- 2세대: USER ---- INTERNET --- WEB SERVER (Create request-based HTML from CGI + DB)  
	- 3세대: USER ---- INTERNET --- WEB SERVER MVC 패턴 기반 프레임워크 활용 
		- MVC: Model - View - Control 패턴으로 구조화된 프레임워크를 사용, 빠르게 다양한 기능을 제공
	- 4세대: OpenAPI, RestAPI 를 혼합하여 다양한 서비스 제공, 다양한 웹 서비스 환경 개발



# 2_flask_basic

## 0. 풀스택 프레임워크와 마이크로 프레임워크
> 여기서 말하는 풀스택은 프레임워크 안에 모든 기능을 가지고 있다는 의미

#### 풀스택 프레임워크: 웹 개발에 관련된 모든 기능을 제공 
- 대표적 프레임워크: JAVA Spring, Python Django, Ruby on Rails  
  - 요청/응답 추상화, 세션 상태 관리, 사용자 인증/권한 관리, 웹페이지 템플릿, URL 매핑, 데이터베이스 접근, 보안, 캐시, 데이터 접근 추상화등 다양한 기능을 제공
  - 각 프레임워크를 활용하는데 학습곡선이 큼
  - 하나의 웹서비스를 구축하는데에도 다양한 프레임워크 기능을 이해하고, 불필요한 부분까지 구축해야함

#### 마이크로 프레임워크: 웹 개발에 필요한 최소 기능만 제공, 나머지 기능은 자신이 원하는 다른 라이브러리나 프레임워크를 확장해 사용
- 빠르게 원하는 기능을 기반으로 웹서비스 구축 가능, 이후 필요한 기능만 확장 가능 

#### Flask (플라스크) 특징
* 마이크로 프레임워크 기반
* 웹 개발 최소 기능 제공, RESTful 요청 처리, 유니코드 기반, 필요한 부분은 추가해서 확장 가능 
* 참고: http://flask.pocoo.org/

## 1. flask 기본 사용법

### 1.1. Flask 모듈 임포트 (보통 다음과 같이 임포트)
* pip install flask

```python
!pip install flask
```

```python
from flask import Flask
```

### 1.2. Flask 객체를 app에 할당

```python
app = Flask(__name__)
```

```python
__name__
```
    '__main__'

#### \_\_name\_\_ 이란?
-  \_\_name\_\_ 이라는 변수는 모듈의 이름이 저장됨
- 실행하는 코드에서는 \_\_main\_\_ 값이 들어감

#### test.py

```python
print ('test.py __name__:', __name__)
```

#### start.py

```python
import test

print ('start.py __name__:', __name__)
```

> start.py 를 실행하면

```bash
test.py __name__: test
start.py __name__: __main__
```

#### 시작점(entry point)
- C, JAVA 와 같은 보통의 언어는 코드를 시작하는 시작점(entry point)를 가지고 있음
- 예:
```c
int main(int argc, char *argv[])      // 옵션의 개수와 옵션 문자열을 배열로 받음
{
    return 0;
}
```

#### 파이썬과 시작점(entry point)
- 파이썬은 스크립트 언어
- 스크립트 언어는 전통적으로 시작점없이 스크립트 코드를 바로 실행함

#### 모듈이 아니라, 해당 코드 직접 실행시만 실행되는 코드

```python
def add_one(data):
    return data + 1
 
def add_two(data):
    return data + 2
 
if __name__ == '__main__': # 모듈이 아니라, 해당 코드 직접 실행시만 실행
    print(add_one(10))
    print(add_two(10))
```
    11
    12

#### flask 객체 생성

- Flask(`__name__`) 으로 설정하여, 현재 위치를 flask 객체에 알려줘야 함
  - 이름을 변경해도 정상 실행되지만, 일부 확장 기능 사용시에는 해당 이름을 정확히 알려주지 않을 경우, 정상 동작되지 않음

```python
from flask import Flask
app = Flask(__name__)
```

```python
app
```
    <Flask '__main__'>

### 1.3. 라우팅 경로를 설정

#### URL 이란
- Uniform Resource Locator
- 인터넷 상의 자원 위치 표기를 위한 규약
- WWW 주요 요소 중 하나: HTML, URL, HTTP


#### 참고: URL vs URI
- URI(Uniform Resource Identifier): 통합 자원 식별자
- URI의 하위 개념이 URL

  - https://www.fun-coding.org 주소
    - https://www.fun-coding.org 라는 서버를 나타내는 URL이면서 URI
  - https://www.fun-coding.org/input?id=dave&pw=1111 주소
    - https://www.fun-coding.org/input 은 URL
      - https://www.fun-coding.org/input?id=dave&pw=1111 은 URI 
      - 내가 원하는 정보를 얻기 위해서는 **?id=dave&pw=1111** 라는 식별자가 필요하기 때문

> 두 용어는 혼용하고 있으므로, 참고로만 이해

#### 라우팅(route)이란?
- 적절한 목적지를 찾아주는 기능 
- URL 을 해당 URL 에 맞는 기능과 연결해 줌
  - 예:
    - http://www.fun-coding.org/hello
    - http://www.fun-coding.org 서버에서 hello 이라는 목적지에 맞는 함수를 호출해줌 


```python
@app.route("/hello")
def hello():                           
    return "<h1>Hello World!</h1>"
```

- @ 으로 시작하는 코드는 데코레이터라고 함 (별도 챕터로 설명)

### 1.4. 메인 모듈로 실행될 때 flask 웹 서버 구동 
- 서버로 구동한 IP 와 포트를 옵션으로 넣어줄 수 있음
- app.run() 함수로 서버 구동 가능
  - host, port, debug 를 주로 사용함
    - host: 웹주소
    - port: 포트
    - debug: True or False

```python
run(host=None, port=None, debug=True)
```

#### 참고: Web Server 와 WAS 프레임워크

* 웹서버는 정적인 HTML 페이지를 반환한다.
  - 요청에 따른 정적인 데이터를 반환한다.
* 웹서버가 동적으로 데이터를 반환하도록 하기 위해서는, WAS 프레임워크가 필요하다.
  - 주요 WAS 프레임워크로는 flask, django, rails, node.js 등이 있다.
  
> 상용화를 위해서는 별도 전문 웹서버를 사용해야 하지만, <br>
> flask 는 기본 Web Server 도 간단한 명령으로 제공함 

<img src="https://www.fun-coding.org/style/images/ads/fullstack_web.jpg">

#### 기본 개발 프로세스
- 자신의 PC 에서 웹서비스 구현
  - localhost, 127.0.0.1, 또는 0.0.0.0 으로 host 설정
  - app.run() 함수로 자체 웹서버 구현 가능

```python
host_addr = "0.0.0.0"
port_num = "8080"
```

```python
if __name__ == "__main__":              
    app.run(host=host_addr, port=port_num)
```

     * Serving Flask app '__main__'
     * Debug mode: off
    WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
     * Running on all addresses (0.0.0.0)
     * Running on http://127.0.0.1:8080
     * Running on http://192.168.0.15:8080
    Press CTRL+C to quit
    

### 1.5. 전체 기본 코드


```python
from flask import Flask

app = Flask(__name__)
@app.route("/hello")
def test():                           
    return "Hello Flask!"

if __name__ == "__main__":              
    app.run(host="127.0.0.1", port="8080")
```
     * Serving Flask app '__main__'
     * Debug mode: off
    WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
     * Running on http://127.0.0.1:8080
    Press CTRL+C to quit
    127.0.0.1 - - [24/Jul/2025 07:26:22] "GET /hello HTTP/1.1" 200 -
    
* flask 라이브러리를 사용한 코드는 보통 파일이름.py 로 작성한 후
  - python 파일이름.py
* 위와 같이 서버에서 실행하는 것이 일반적
* 노트북에서는 실행 후, 테스트 끝나면, Terminate를 눌러줘야 함



# 3_python_decorator

## 2. 파이썬 중급: 데코레이터의 이해
- 데코레이터는 단지 파이썬 flask 뿐만 아니라, 다양한 언어 전반에 걸쳐서 많이 사용됨
- 파이썬 flask 에서 나오는 데코레이터를 쓰기 전에, 언어 전반에 걸친 데코레이터 관련 기술을 이해하기로 함
- 한번 이해해놓으면, 다양한 언어 전반에서 데코레이터를 만났을 때마다 꾸준히 도움이 됨

### 2.1. 중첩 함수 (Nested function)
* 함수 내부에 정의된 또 다른 함수
* 중첩함수는 해당 함수가 정의된 함수 내에서 호출 및 반환 가능
* 함수 안에 선언된 변수는 함수 안에서만 사용 가능한 원리와 동일 (로컬 변수)

```python
def outer_func():
    print('call outer_func function')
    
    # 중첩 함수의 정의
    def inner_func():
        return 'call inner_func function'
    
    # 중첩 함수 호출 
    print(inner_func())
```

```python
outer_func()
```
    call outer_func function
    call inner_func function

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">생각해보기</font><br>
outer_func() 함수의 출력을 보면서 왜 이렇게 출력이 되었는지 생각해보기~
</div>


```python
# 중첩함수는 함수 밖에서는 호출 불가 (outer_func 함수 안에서 선언되었으니, outer_func 함수 안에서만 호출 가능)
inner_func()
```
    ---------------------------------------------------------------------------
    NameError                                 Traceback (most recent call last)
    Cell In[7], line 2
	  1 # 중첩함수는 함수 밖에서는 호출 불가 (outer_func 함수 안에서 선언되었으니, outer_func 함수 안에서만 호출 가능)
    ----> 2 inner_func()
    NameError: name 'inner_func' is not defined


#### 그런데 중첩함수를 함수 밖에서도 호출할 수 있는 방법이 있다. 이 방법을 이해하기 위해 First-class function, closure 에 대해 다음 장에서 알아보자.


```python
def outer_func(num):
    # 중첩 함수에서 외부 함수의 변수에 접근 가능
    def inner_func():
        print(num)
        return 'complex'
    
    return inner_func

fn = outer_func(10)    # <--- First-class function
print(fn())            # <--- Closure 호출 
```

### 2.2. First-class function 

#### First-class 함수 
- 다음과 같이 다룰 수 있는 함수를 First-class 함수라고 부름
  - 함수 자체를 변수에 저장 가능
  - 함수의 인자에 다른 함수를 인수로 전달 가능
  - 함수의 반환 값(return 값)으로 함수를 전달 가능

#### 파이썬과 First-class 함수
- 사실 파이썬에서는 모든 것이 객체!
- 파이썬 함수도 객체로 되어 있어서, 기본 함수 기능 이외 객체와 같은 활용이 가능 
  - 즉, 파이썬의 함수들은 First-class 함수로 사용 가능

> <font color='#BF360C'>지금까지 배운 언어의 맥락과는 뿌리가 다른 사고 - 함수형 프로그래밍에서부터 고안된 기법</font>

#### 참고: 언어별 First-class 함수 지원 여부
- python, Go, javascript, Kotlin 은 First-class 함수 지원
- C 언어등은 First-class 함수 미지원

#### 다른 변수에 함수 할당 가능

```python
def calc_square(digit):
    return digit * digit
```

```python
calc_square(2)
```

```python
# 1. func1 이라는 변수에 함수를 할당 가능
func1 = calc_square
```

```python
print (func1)
```

```python
func1(4)
```

#### 함수가 할당된 변수는 동일한 함수처럼 활용 가능 

```python
# 2. func1 이라는 변수는 calc_square 함수를 가리키고, calc_square 와 마찬가지로 인자도 넣어서 결과도 얻을 수 있음 (완전 calc_square와 동일)
print (func1)
func1(2)
```

#### 함수를 다른 함수에 인자로 넣을 수도 있음

```python
def calc_square(digit):
    return digit * digit

def calc_plus(digit):
    return digit + digit

def calc_quad(digit):
    return digit * digit * digit * digit
```

```python
def list_square(function, digit_list):
    result = list()
    for digit in digit_list:
        result.append(function(digit)) 
    print (result)
```

```python
num_list = [1, 2, 3, 4, 5]
```

```python
list_square(calc_square, num_list)
list_square(calc_plus, num_list)
list_square(calc_quad, num_list)
```

#### 함수의 결과값으로 함수를 리턴할 수도 있음

```python
def logger(msg):
    message = msg
    def msg_creator():    # <--- 함수 안에 함수를 만들 수도 있음
        print ('[HIGH LEVEL]: ', msg)
    return msg_creator
```

```python
log1 = logger('Dave Log-in')
```

```python
print(log1)
```

```python
log1()
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">생각해보기</font><br>
1. 함수 안에 선언된 변수를 칭하는 용어는?<br>
2. 함수 안에 선언된 변수 값이 유지되는 기간은?<br>
3. 위 코드에서 log1() 결과값에서 특이한 점은?
</div>

> logger 함수를 삭제해도 log1() 함수는 logger 함수 안에 있는 msg_creator 함수와 msg 값을 유지

```python
del logger
```

```python
log1()
```

#### First-class 함수 활용

```python
def html_creator(tag):
    def text_wrapper(msg):
        print ('<{0}>{1}</{0}>'.format(tag, msg))
    return text_wrapper
```

```python
h1_html_creator = html_creator('h1') #1
print (h1_html_creator)
```
    <function html_creator.<locals>.text_wrapper at 0x7fc9f6c56710>
    

```python
h1_html_creator('H1 태그는 타이틀을 표시하는 태그입니다.')
```
    <h1>H1 태그는 타이틀을 표시하는 태그입니다.</h1>
    

```python
p_html_creator = html_creator('p')
p_html_creator('P 태그는 문단을 표시하는 태그입니다.')
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">생각해보기</font><br>
위와 같이 출력되는 이유를 생각해봅니다.
</div>

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">연습</font><br>
스트링으로 된 문자열이 주어지면, 정해진 목차 기호로 나열해주는 First-class 함수를 만들어보세요<br>
<pre>
예: 
func1 = index_creator('-')
func1(list_data)

출력:
* ....
* ....
* ....
</pre>
</div>


```python
def list_creator(tag):
    def text_wrapper(list_data):
        for item in list_data:
            print ('{0} {1}'.format(tag, item))
    return text_wrapper

data_list_minus = list_creator('-')
data_list_minus(['안녕', '하세요'])

data_list_mul = list_creator('*')
data_list_mul(['안녕', '하세요'])

data_list_x = list_creator('X')
data_list_x(['안녕', '하세요'])

```

    - 안녕
    - 하세요
    * 안녕
    * 하세요
    X 안녕
    X 하세요
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">도전 과제 (크롤링 기술을 익히신 분만 해당) </font><br>
위에서 만든 First-class 함수로 다음 사이트의 나만의 엣지있는 블로그 사이트 만들기 (취미로 익히는 IT)' 코스 리스트를 출력해보세요
    
https://davelee-fun.github.io/blog/crawl_html_css.html
    
</div>


```python
import requests
from bs4 import BeautifulSoup

res = requests.get('https://davelee-fun.github.io/blog/crawl_html_css.html')
soup = BeautifulSoup(res.content, 'html.parser')
# a 태그이면서 href 속성 값이 특정한 값을 갖는 경우 탐색
link_titles = soup.select("ul#hobby_course_list > li")
data = list()
for link_title in link_titles:
    data.append(link_title.get_text())

data_list_minus(data)
```

    - (왕초보) - 클래스 소개
    - (왕초보) - 블로그 개발 필요한 준비물 준비하기
    - (왕초보) - Github pages 설정해서 블로그 첫 페이지 만들어보기
    - (왕초보) - 초간단 페이지 만들어보기
    - (왕초보) - 이쁘게 테마 적용해보기
    - (왕초보) - 마크다운 기초 이해하고, 실제 나만의 블로그 페이지 만들기
    - (왕초보) - 다양한 마크다운 기법 익혀보며, 나만의 블로그 페이지 꾸며보기
    

### 2.3. Closure function
* 함수와 해당 함수가 가지고 있는 **데이터를 함께 복사, 저장해서 별도 함수**로 활용하는 기법으로 First-class 함수와 동일
* 외부 함수가 소멸되더라도, 외부 함수 안에 있는 로컬 변수 값과 중첩함수(내부함수)를 사용할 수 있는 기법
* <font color='#BF360C'>지금까지 배운 언어의 맥락과는 뿌리가 다른 사고 - 함수형 프로그래밍에서부터 고안된 기법</font>
* <font color='#BF360C'>그래서 처음에 접하면 매우 이해하기 어려움, 예제 코드로 보면서 이해하자</font>



```python
def outer_func(num):
    # 중첩 함수에서 외부 함수의 변수에 접근 가능
    def inner_func():
        print(num)
        return '안녕'
    
    return inner_func                 # 중첩 함수 이름을 리턴합니다.
```


```python
closure_func = outer_func(10)    # <--- First-class function
closure_func()            # <--- Closure 호출 
```

#### 예제 코드로 이해하는 closure
* 위의 예제에서 closure_func이 바로 closure 임
* closure_func = outer_func(10) 에서 outer_func 함수는 호출 종료
* closure_func() 은 결국 inner_func 함수를 호출
* outer_func(10) 호출 종료시 num 값은 없어졌으나, closure_func()에서 inner_func이 호출되면서 이전의 num값(10)을 사용함


```python
del outer_func
```

#### 심지어 outer_func 함수를 아예 삭제해버려도 fn(), 즉 inner_func() 와 num값(10)은 살아있음


```python
closure_func()
```

### 언제 closure를 사용할까?
* closure는 객체와 유사
* 일반적으로 제공해야할 기능(method)이 적은 경우, closure를 사용하기도 함
* 제공해야할 기능(method)가 많은 경우등은 class를 사용하여 구현


```python
def calc_square(digit):
    return digit * digit

def calc_power_3(digit):
    return digit * digit * digit

def calc_quad(digit):
    return digit * digit * digit * digit
```


```python
print (calc_square(2))
print (calc_power_3(2))
print (calc_quad(2))
```


```python
def calc_power(n):
    def power(digit):
        return digit ** n
    return power
```


```python
power2 = calc_power(2)
power3 = calc_power(3)
power4 = calc_power(4)
```


```python
print (power2(2))
print (power3(2))
print (power4(2))
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">연습</font><br>
1에서 5까지 1승부터 5승까지 출력하기 (위 calc_power() 함수를 사용해서 list_data 리스트 변수에 1승부터 5승까지 계산 클로져 함수를 넣어서 사용)
</div>


```python
list_data = list()
for num in range(1, 6):
    list_data.append(calc_power(num))

for func in list_data:
    print(func(2))
```

### 2.4. 데코레이터 (Decorator)
 - 함수 앞뒤에 기능을 추가해서 손쉽게 함수를 활용할 수 있는 기법
 - Closure function을 활용
 - https://www.python.org/dev/peps/pep-0318/


#### 혹시 다음과 같이 @ 가 사용된 파이썬 코드를 본 적이 있으신지?
<pre>
@decorator_func
def function():
    print ("what is decorator?")
</pre>
#### 위 코드에서 @decorator_func 부분이 데코레이터임 


```python
# 다음 함수를 함 보자
def logger_login():
     print ("Dave login")

logger_login()
```


```python
# 시간을 앞뒤로 추가하고 싶다.
# 이렇게 넣으면 됩니다.
import datetime

def logger_login():
    print (datetime.datetime.now())
    print ("Dave login")
    print (datetime.datetime.now())

logger_login()
```


```python
# 아차 다른 비슷한 함수도 다 넣으려면.... 이걸 좀 깔끔하게...
def logger_login_david():
     print ("David login")

def logger_login_anthony():
     print ("Anthony login")

def logger_login_tina():
     print ("Tina login")
```

#### 직접 각 함수에 기능을 앞뒤로 코드로 넣어도 되긴 되지 않을까?
* 여러 함수에 동일한 기능을 @데코레이터 하나로 간편하게 추가할 수 있고,
* 예를 들어, 파라미터가 있는 함수에 파라미터의 유효성 검사가 필요할 때
  - 파라미터가 있는 함수가 있을 때마다, 유효성 검사 코드를 넣기가 불편!
  - 만약 유효성 검사 코드 수정이 필요하다면 관련 함수를 모두 수정해야 하므로 매우 불편

### 2.5. 데코레이터 작성법


```python
# 데코레이터 작성하기
def datetime_decorator(func):           # <--- datetime_decorator 는 데코레이터 이름, func 가 이 함수 안에 넣을 함수가 됨
    def wrapper():                      # <--- 호출할 함수를 감싸는 함수
        print ('time ' + str(datetime.datetime.now())) # <--- 함수 앞에서 실행할 내용
        func()                          # <--- 함수  
        print (datetime.datetime.now()) # <--- 함수 뒤에서 실행할 내용
    return wrapper                      # <--- closure 함수로 만든다.
```


```python
# 데코레이터 적용하기
@datetime_decorator    # @데코레이터
def logger_login_david():
     print ("David login")

logger_login_david()
```


```python
@datetime_decorator    # @데코레이터
def logger_login_anthony():
     print ("Anthony login")

logger_login_anthony()
```


```python
@datetime_decorator    # @데코레이터
def logger_login_tina():
     print ("Tina login")

logger_login_tina()
```

### Nested function, Closure function 과 함께 데코레이터를 풀어서 작성해보자 


```python
# decorator 함수 정의
def outer_func(function):
    def inner_func():
        print('decoration added')
        function()
    return inner_func

# decorating할 함수
def log_func():
    print('logging')
```


```python
# 본래 함수
log_func()
```


```python
# log_func 함수에 inner_func 함수의 기능을 추가한 decorated_func 함수
decorated_func = outer_func(log_func)
decorated_func()  # <--- 결과는 데코레이터를 사용할 때와 동일함
```

### 이것을 한번에 데코레이터로 작성하면!


```python
@outer_func
def log_func():
    print('logging')

log_func()
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">생각해보기</font><br>
1. 위 코드에서 Nested function은?<br>
2. 위 코드에서 Closure function은?<br>
</div>

### 파라미터가 있는 함수에 Decorator 적용하기
* 중첩함수에 꾸미고자 하는 함수와 동일하게 파라미터를 가져가면 됨


```python
# 데코레이터
def outer_func(function):
    def inner_func(digit1, digit2):
        if digit2 == 0:                       # <--- 유효성 검사의 예
            print('cannot be divided with zero')
            return
        function(digit1, digit2)
    return inner_func
```


```python
# 데코레이터 사용하기 (유효성 검사)
@outer_func
def divide(digit1, digit2):
    print (digit1 / digit2)
```


```python
divide(4, 2)
```


```python
divide(9, 0)
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">연습</font><br>
type_checker 데코레이터 만들기 (인자 유효성 검사)<br>
digit1, digit2 를 곱한 값을 출력하는 함수 만들기<br>
type_checker 데코레이터로 digit1, digit2 가 정수가 아니면 'only integer support' 출력하고 끝냄<br>
if (type(digit1) != int) or (type(digit2) != int):
</div>


```python
# 데코레이터
def type_checker(function):
    def inner_func(digit1, digit2):
        if (type(digit1) != int) or (type(digit2) != int):                       # <--- 유효성 검사의 예
            print('the only int is supported')
            return 
        return function(digit1, digit2)
    return inner_func

# 데코레이터 사용하기 (유효성 검사)
@type_checker
def divide(digit1, digit2):
    return digit1 * digit2

divide(0.1, 1)
```

### 파라미터와 관계없이 모든 함수에 적용 가능한 Decorator 만들기
* 파라미터는 어떤 형태이든 결국 (*args, ***kwargs) 로 표현 가능
* 데코레이터의 내부함수 파라미터를 (*args, ***kwargs) 로 작성하면 어떤 함수이든 데코레이터 적용 가능


```python
# 데코레이터 작성하기
def general_decorator(function):
    def wrapper(*args, **kwargs):
        print('function is decorated')
        return function(*args, **kwargs)
    return wrapper
```


```python
# 데코레이터 적용하기
@general_decorator
def calc_square(digit):
    return digit * digit

@general_decorator
def calc_plus(digit1, digit2):
    return digit1 + digit2

@general_decorator
def calc_quad(digit1, digit2, digit3, digit4):
    return digit1 * digit2 * digit3 * digit4
```


```python
# 함수 호출하기
print (calc_square(2))
print (calc_plus(2, 3))
print (calc_quad(2, 3, 4, 5))
```

### 한 함수에 데코레이터 여러 개 지정하기
* 함수에 여러 개의 데코레이터 지정 가능 (여러 줄로 @데코레이터를 써주면 됨)
* 데코레이터를 나열한 순서대로 실행됨 


```python
# 여러 데코레이터 작성하기
def decorator1(function):
    def wrapper():
        print('decorator1')
        function()
    return wrapper
 
def decorator2(function):
    def wrapper():
        print('decorator2')
        function()
    return wrapper
```


```python
# 여러 데코레이터를 함수에 한번에 적용하기
@decorator1
@decorator2
def hello():
    print('hello')
```


```python
hello()
```

    decorator1
    decorator2
    hello
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">도전 과제</font><br>
다음 그림에 있는 HTML 웹페이지 태그를 붙여주는 데코레이터 만들기<br>
해당 데코레이터를 사용해서 안녕하세요 출력해보기<br>
<img src="https://www.fun-coding.org/00_Images/tag.png" />
</div>


```python
def mark_bold(function):
    def wrapper(*args, **kwargs):
        return '<b>' + function(*args, **kwargs) + '</b>'
    return wrapper

def mark_italic(function):
    def wrapper(*args, **kwargs):
        return '<i>' + function(*args, **kwargs) + '</i>'
    return wrapper

@mark_bold
@mark_italic
def add_html(string):
    return string

print (add_html('안녕하세요'))
```

    <b><i>안녕하세요</i></b>
    


```python
%%html
<b>안녕</b>
<i>안녕</i>
<b><i>안녕</i></b>
```


<b>안녕</b>
<i>안녕</i>
<b><i>안녕</i></b>



### Method Decorator
* 클래스의 method에도 데코레이터 적용 가능
  - 클래스 method는 첫 파라미터가 self 이므로 이 부분을 데코레이터 작성시에 포함시켜야 함


```python

```


```python
# 데코레이터 작성하기 (for method)
def h1_tag(function):
    def func_wrapper(self, *args, **kwargs):            # <--- self 를 무조건 첫 파라미터로 넣어야 메서드에 적용가능
        return "<h1>{0}</h1>".format(function(self, *args, **kwargs))  # <--- function 함수에도 self 를 넣어야 함
    return func_wrapper
```


```python
# 클래스 선언시 메서드에 데코레이터 적용하기
class Person:
    def __init__(self, first_name, last_name):
        self.first_name = first_name
        self.last_name = last_name

    @h1_tag
    def get_name(self):
        return self.first_name + ' ' + self.last_name
```


```python
# 데코레이터 적용 확인해보기
davelee = Person('Lee', 'Dave')
print(davelee.get_name())
```

    <h1>Lee Dave</h1>
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">파이썬 format() 함수 이해하기</font><br>
다음 코드 실행 결과 예상하고, 확인하기
</div>


```python
print('{} {}'.format(10, 100))
```

    10 100
    


```python
print('{0} {2} {0} {1}'.format(10, 100, 20))
```

    10 20 10 100
    


```python
print('{1} {0}'.format(10, 100))
```


```python
print('{aa} {bb}'.format(aa = 'aaaa', bb = 'cccc'))
```

### 파라미터가 있는 Decorator 만들기 (심화)
* decorator에 파라미터를 추가 가능


```python
# 중첩 함수의 하나 더 깊게 두어 생성
def decorator1(num):
    def outer_wrapper(function):
        def innter_wrapper(*args, **kwargs):
            print('decorator1 {}'.format(num))
            return function(*args, **kwargs)
        return innter_wrapper
    return outer_wrapper
```


```python
def print_hello():
    print ('hello')
```


```python
# 위와 같이 작성하면, 다음과 같이 호출할 수 있다.
print_hello2 = decorator1(1)(print_hello)
print_hello2()
```

    decorator1 1
    hello
    


```python
# 이를 데코레이터로 표현하면 다음과 같다.
@decorator1(1)
def print_hello():
    print('hello')
```


```python
print_hello()
```

    decorator1 1
    hello
    


```python
# 이를 데코레이터로 표현하면 다음과 같다.(이렇게 써도 됨)
@decorator1(num=2)
def print_hello():
    print('hello')
```


```python
print_hello()
```

    decorator1 2
    hello
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">도전 과제</font><br>
다음 그림에 있는 HTML 웹페이지 태그와 같이 태그 이름을 넣으면 HTML 문법에 맞게 출력해주는 데코레이터를 만들기<br>
해당 데코레이터를 사용해서 b, i, h1, h2, h3, h4, h5, h6, center 태그를 리스트로 넣어서 안녕하세요 출력해보기<br>

```python
@mark_html('b')
def print_title(title):
    return title
print ('잔재미코딩 Dave Lee 입니다.')
출력:
    <b>잔재미코딩 Dave Lee 입니다.</b>    
```
</div>


```python
def mark_html(tag):
    def outer_wrapper(function):
        def inner_wrapper(*args, **kwargs):
            return '<' + tag + '>' + function(*args, **kwargs) + '</' + tag + '>'
        return inner_wrapper
    return outer_wrapper

@mark_html('b')
def print_bold(title):
    return title

@mark_html('h1')
def print_title(title):
    return title

print(print_title('잔재미코딩 Dave Lee 입니다.'))
```

    <h1>잔재미코딩 Dave Lee 입니다.</h1>
    

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 4_flask_basic
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 3. flask 와 Rest API
- HTML 언어는 프론트엔드 강의에서 보다 상세하게 다루며, 본 강의에서는 파이썬 기초와 크롤링 부트캠프에서 설명한 HTML 태그 구조에 대한 이해만을 기반으로 함

### 정적 페이지 리턴하기 (HTML)
* 복잡한 URI를 함수로 쉽게 연결하는 방법 제공
* h1 ~ h6 는 HTML 제목 태그


```python
from flask import Flask

app = Flask(__name__)
@app.route("/")
def hello():                           
    return "<h1>Hello World!</h1>"

@app.route("/hello")
def hello_flask():
    return "<h1>Hello Flash!</h1>"

@app.route("/first")
def hello_first():
    return "<h3>Hello First</h3>"

if __name__ == "__main__":              
    app.run(host="0.0.0.0", port="8080")
```

     * Serving Flask app "__main__" (lazy loading)
     * Environment: production
    [31m   WARNING: This is a development server. Do not use it in a production deployment.[0m
    [2m   Use a production WSGI server instead.[0m
     * Debug mode: off
    

     * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    127.0.0.1 - - [05/Aug/2020 11:38:30] "[37mGET / HTTP/1.1[0m" 200 -
    127.0.0.1 - - [05/Aug/2020 11:43:17] "[37mGET / HTTP/1.1[0m" 200 -
    127.0.0.1 - - [05/Aug/2020 11:43:44] "[37mGET /hello HTTP/1.1[0m" 200 -
    127.0.0.1 - - [05/Aug/2020 11:43:56] "[37mGET /first HTTP/1.1[0m" 200 -
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://0.0.0.0:8080/first 로 접속시, h3 태그로 Hello First 출력하기
</div>

### 복잡한 라우팅: 데이터 전달하기

* URI를 변수로 사용
  - 다음 코드 추가 후, http://0.0.0.0:8080/profile/dave 접속
  
```python
@app.route("/profile/<username>")
def get_profile(username):
    return "profile: " + username
```


```python
from flask import Flask

app = Flask(__name__)
@app.route("/")
def hello():                           
    return "<h1>Hello World!</h1>"

@app.route("/profile/<username>")
def get_profile(username):
    return "profile: " + username

@app.route("/first/<username>")
def get_first(username):
    return "<h3>Hello " + username + "!</h3>"

if __name__ == "__main__":              
    app.run(host="0.0.0.0", port="8080")
```

     * Serving Flask app "__main__" (lazy loading)
     * Environment: production
    [31m   WARNING: This is a development server. Do not use it in a production deployment.[0m
    [2m   Use a production WSGI server instead.[0m
     * Debug mode: off
    

     * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    127.0.0.1 - - [05/Aug/2020 11:57:54] "[37mGET /first/3 HTTP/1.1[0m" 200 -
    127.0.0.1 - - [05/Aug/2020 11:57:59] "[37mGET /first/end HTTP/1.1[0m" 200 -
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://0.0.0.0:8080/first/userid 로 접속시, h3 태그로 Hello userid ! 출력하기
</div>

* URI를 변수로 사용, 변수에 데이터 타입도 줄 수 있음
  - 데이터 타입이 없으면 문자열로 인식
  - int 이외에 float 도 데이터 타입으로 줄 수 있음
  - 다음 코드 추가 후, http://0.0.0.0:8080/message/1 접속


```python
@app.route("/message/<int:message_id>")
def get_message(message_id):
    return "message id: " + message_id
```


```python
from flask import Flask

app = Flask(__name__)

def add_file(data):
    return data + 5

@app.route("/")
def hello():                           
    return "<h1>Hello World!</h1>"

@app.route("/message/<int:message_id>")
def get_message(message_id):
    return "message id: %d" % message_id   # %d 는 int, %f 는 float, %s 는 string

@app.route("/first/<int:messageid>")
def get_first(messageid):
    data = add_file(messageid)
    return "<h1>%d</h1>" % (data)


if __name__ == "__main__":              
    app.run(host="0.0.0.0", port="8080")
```

     * Serving Flask app "__main__" (lazy loading)
     * Environment: production
    [31m   WARNING: This is a development server. Do not use it in a production deployment.[0m
    [2m   Use a production WSGI server instead.[0m
     * Debug mode: off
    

     * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    127.0.0.1 - - [05/Aug/2020 12:01:44] "[37mGET / HTTP/1.1[0m" 200 -
    127.0.0.1 - - [05/Aug/2020 12:01:56] "[37mGET /message/1 HTTP/1.1[0m" 200 -
    127.0.0.1 - - [05/Aug/2020 12:02:22] "[37mGET /first/1 HTTP/1.1[0m" 200 -
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://0.0.0.0:8080/first/숫자 로 접속시, h1 태그로 숫자 + 5 출력하기
</div>

### 3. flask 로 REST API 구현하기


### HTTP(Hypertext Transfer Protocol)
- Server/Client 모델로 Request/Response 사용
  - Client에서 요청(Request)을 보내면, Server에서 응답(Response)을 준다.


<center><img src="https://www.fun-coding.org/00_Images/web_http.png" height=350 /></center>

> 프로토콜 (protocol): 컴퓨터간 통신을 하기 위한 규칙 

### HTTP(Hypertext Transfer Protocol) Request/Response

- Request
<center><img src="https://www.fun-coding.org/00_Images/http_request.png" /></center>


### HTTP(Hypertext Transfer Protocol) Request/Response

- Response
<center><img src="https://www.fun-coding.org/00_Images/http_response.png" /></center>


### REST
- REST(REpresentational State Transfer)
  - 자원(resource)의 표현(representation)에 의한 상태 전달
  - HTTP URI를 통해 자원을 명시하고, HTTP Method를 통해 자원에 대한 CRUD Operation 적용
    - CRUD Operation와 HTTP Method
      - Create: 생성 (POST)
      - Read: 조회 (GET)
      - Update: 수정 (PUT)
      - Delete: 삭제 (DELETE)

### REST API
- REST 기반으로 서비스 API를 구현한 것
- 마이크로 서비스, OpenAPI(누구나 사용하도록 공개된 API) 등에서 많이 사용됨

### flask 로 REST API 구현 방법
- 특정한 URI를 요청하면 JSON 형식으로 데이터를 반환하도록 만들면 됨
- 즉, 웹주소(URI) 요청에 대한 응답(Response)를 JSON 형식으로 작성
- Flask에서는 dict(사전) 데이터를 응답 데이터로 만들고, 이를 jsonify() 메서드를 활용해서 JSON 응답 데이터로 만들 수 있음

### REST API 테스트를 위한 준비

### httpie 설치
- https://httpie.org/

!pip install httpie

### httpie 기본 사용법

> **💡 주의:** 윈도우 환경에서는 `cmd`보다 **Powershell**에서 사용하는 것을 권장합니다. (`cmd`에서는 일부 기능 사용 문법이 달라서, 정상적으로 동작하지 않을 수 있습니다.)

#### 1. 기본 요청 보내기

-   **명령 형식:** `http [HTTP메서드] <URI>`
-   지정한 URI로 HTTP 요청을 보냅니다.
-   `HTTP메서드`를 생략하면 기본값인 `GET`으로 요청합니다.

**예시:**
```bash
# GET 요청 (메서드 명시)
http GET http://localhost:8080/json_test

# GET 요청 (메서드 생략 - 위와 동일)
http http://localhost:8080/json_test
```

#### 2. 요청/응답 상세 정보 보기 (`-v` 옵션)

-   **명령 형식:** `http -v [HTTP메서드] <URI>`
-   `-v` (verbose) 옵션을 사용하면 요청 헤더, 요청 본문 등 **송신**하는 HTTP 프로토콜 데이터까지 함께 출력되어 디버깅에 유용합니다.

**예시:**
```bash
http -v GET http://localhost:8080/json_test
```


### REST API 구현


```python
from flask import Flask, jsonify
app = Flask(__name__)
```

* data를 사전 데이터로 만들고, 이를 jsonify() 메서드에 넣어서 return 해주면 됨

### flask jsonify() 함수
- 리턴 데이터를 JSON 포맷으로 제공

> 혹시 JSON 포맷에 대한 이해가 필요할 시에는 파이썬 입문과 크롤링 부트캠프 또는 처음하는 파이썬 데이터 분석 강의 수강

#### 참고
- 사실 `return [JSON 데이터]` 로 작성해도 json 포멧을 자동 인식하여, 정상적으로 전달해줌
- 단, `jsonify()`를 사용하는 것이 더 명시적이며 표준적인 방법임
  - 보다 기술적으로는 `jsonify()`는 내부적으로 `Response` 객체를 생성하고 `Content-Type: application/json` 헤더를 명시적으로 설정함


```python
@app.route('/json_test')
def hello_json():
    data = {'name' : '김대리', 'family' : 'Byun'}
    return jsonify(data)

@app.route('/server_info')
def server_json():
    data = { 'server_name' : '0.0.0.0', 'server_port' : '8080' }
    return jsonify(data)
```


```python
if __name__ == "__main__":              
    app.run(host="0.0.0.0", port="8081")
```

     * Serving Flask app '__main__'
     * Debug mode: off
    

    WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
     * Running on all addresses (0.0.0.0)
     * Running on http://127.0.0.1:8081
     * Running on http://172.30.1.24:8081
    Press CTRL+C to quit
    127.0.0.1 - - [02/May/2025 15:36:33] "GET /json_test HTTP/1.1" 200 -
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
- http GET http://localhost:8080/json_test <br>
- http GET http://localhost:8080/server_info <br>
        
</div>

### Visual Studio Code 에디터 설치해보기
> 기본적으로 주피터 노트북에서 코드 조각을 테스트하고, 최종 파일을 작성하여 실행 <br>
> 단, 여러 파일로 코드가 이루어져 있고, 서로 연결되어 실행되어야 할 경우에는 코드 에디터를 사용하는 편이 좋음

- 코드 에디터
  - 코드 작성을 도와주는 툴
  - 파이썬의 경우, Pycharm, Visual Studio Code 를 많이 사용
  - Visual Studio Code 는 파이썬 외에도 다양한 언어 지원
    - 반면에, Pycharm 은 파이썬 전용 에디터
  
> 장기적으로 파이썬 외에도 다양한 언어를 구현해야 하고, 최근에 Visual Studio Code 가 많이 사용되므로, Visual Studio Code 선택 <br>
> 회사에서도 한 개발팀에서는 동일한 에디터를 쓰는 경우가 많으므로, 가장 많이 쓰는 툴을 쓰는 것이 더 좋음

### Visual Studio Code 설치 방법
- https://code.visualstudio.com/ 에서 프로그램 다운로드 및 설치
- Visual Studio Code 실행 후, Extension 메뉴에서 다음 플러그인 설치
  - Python
  - Python Extension Pack
  
- Python Interpreter 설정
  - 파이썬 인터프리터(컴파일러) 위치는 다음 명령으로 터미널에서 확인
    - 맥: `which python`
    - 윈도우 (Powershell 에서 실행 추천): `where.exe python`

### 프론트엔드와 백엔드 flask 로 한번에 구현해보기
- 01_flask_test 폴더에 login_test.py 파일 작성
- GET 요청으로 받는 url은 아래와 같이 코드 작성

```python
from flask import Flask, jsonify, request
app = Flask(__name__)


@app.route('/login')
def login():
    username = request.args.get('user_name')
    if username == 'dave':
        return_data = {'auth':'success'}
    else:
        return_data = {'auth':'failed'}
    return jsonify(return_data)

if __name__ == '__main__':
    app.run(host="0.0.0.0", port="8080")
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http "http://localhost:8080/login?user_name=222" <br>
http "http://localhost:8080/login?user_name=dave"
</div>

### Rest API 요청시 파라미터/파라미터값 넣기
- HTTP 의 요청 방식 중, 가장 많이 사용되는 방식이 GET 방식
  - GET 방식에서는 URI 상에 파라미터와 파라미터 값을 넣을 수 있음
    - 규칙: URL?파라미터1=파라미터1값&파라미터2=파라미터2값 
    - URL 이후 첫 파라미터 이름 전에 ? 를 표시하고, 추가 파라미터가 있을 시에는 & 표시를 해야 함
<center><img src="https://www.fun-coding.org/00_Images/http_method_get.png"/></center>

### 프론트엔드, HTML 코드와 연계해서 구현해보기
- Visual Studio Code 에 Emmet 기능이 구현되어 있음
  - Emmet 기능은 특정 약어로 템플릿 코드 생성
  
  ```
  html:5 라고 쓰고 <탭 키> 를 누르면 HTML5 기본 템플릿 생성
  ```

> HTML 기본적인 부분은 파이썬 기초와 크롤링 부트캠프 강의에서 다룬 부분을 참조! <br>
> 매우 상세한 HTML/CSS 코드 작성은 프론트엔드 과정에서 설명 예정 (백엔드 flask 에 집중!)

### 폴더 구조를 다음과 생성하고, login.html 생성

```
/login_test.py
/templates
    /login.html
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <form action="/login" method="get">
      <p>Enter Name:</p>
      <p><input type="text" name="user_name" /></p>
      <p><input type="submit" value="submit" /></p>
    </form>
  </body>
</html>
```

### flask 로 정적 웹페이지 로드하기 
> 프론트엔드 페이지도 flask 로 보여줄 수 있음

- flask render_template(HTML파일명): HTML 파일 전송하기
  - HTML파일은 flask 가 실행되는 하위 폴더인 templates 폴더 안에 위치해야 함

```python
@app.route('/html_test')
def hello_html():
    # html file은 templates 폴더에 위치해야 함
    return render_template('login.html')
```

### login_test.py 파일 업데이트
- flask 의 render_template 함수 추가
- @app.route('html_test') 추가

```python
from flask import Flask, jsonify, request, render_template
app = Flask(__name__)


@app.route('/login')
def login():
    username = request.args.get('user_name')
    if username == 'dave':
        return_data = {'auth': 'success'}
    else:
        return_data = {'auth': 'failed'}
    return jsonify(return_data)


@app.route('/html_test')
def hello_html():
    # html file은 templates 폴더에 위치해야 함
    return render_template('login.html')


if __name__ == '__main__':
    app.run(host="0.0.0.0", port="8080")
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
login_test.py 실행 후, http://localhost:8080/html_test 웹페이지 브라우저로 오픈하기
</div>

### bootstrap 과 static_url_path
- 03_flask_bootstrap 폴더

> 수시로 소스가 달라지므로, 현재 제공해드린 소스를 기반으로 소스가 어떻게 구성되었는지만 설명

### flask 로 정적 페이지 로드시, 경로를 찾지 못함
- 가장 합리적인 방법은 static_url_path 를 flask 객체 생성시 선언해주는 것임
```
from flask import Flask, jsonify, request, render_template
app = Flask(__name__, static_url_path='/static')
```

- html 상의 경로 변경
```html
<link rel="canonical" href="https://getbootstrap.com/docs/4.5/examples/sign-in/" />
<link href="/static/dist/css/bootstrap.min.css" rel="stylesheet" />
```



<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 5_flask_jinja2
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 5. 웹페이지(HTML)를 파이썬 flask로 만들기

### Jinja2 템플릿
- 웹페이지에 필요한 부분을 변경할 필요가 있을 때 사용하는 간단한 문법
- 웹페이지에서 파이썬 프로그래밍이 가능
- 문법이므로 세세한 기능이 있지만, 처음 익힐 때는 핵심에 집중
- 다음 두 가지 문법이 핵심

```python
{{ 변수명 }}

{% 파이썬 소스코드 %}
```

###  Jinja2 템플릿 엔진
 - jinja2 템플릿 엔진이 해당 HTML 코드를 템플릿으로 만들고, 템플릿 안에 파이썬 코드를 실행하여, 템플릿을 채운 후 최종 HTML 파일 생성

### 5.1. 변수 (Jinja2 template 문법)

### 폴더 구조

```
/variable_test.py
/templates
    /variable.html
```

### variable_html.py
- render_template() 함수에 템플릿 코드에서 사용하는 변수값을 넣어서 보내줘야 함


```python
from flask import Flask, render_template
app = Flask(__name__)

@app.route('/hello/<user>')
def hello_name(user):
   return render_template('variable.html', name=user)

if __name__ == '__main__':
    app.run(host="0.0.0.0", port="8080")
```

### variable.html
- 변수값이 씌여질 곳에 다음과 같이 작성함

```
{{ 변수명 }}
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Hello {{ name }}</h1>
  </body>
</html>
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://localhost:8080/hello/dave 로 테스트해보기
</div>

### 5.2. 반복문 (Jinja2 template 문법)

### 폴더 구조

```
/loop_test.py
/templates
    /loop.html
```

### Jinja2 템플릿에서의 반복문 문법
- 기본 문법: for 로 선언하고, endfor 로 끝나야 함

```
{% for %} {% endfor %} 
```

- 예:
  - 인덴테이션(들여쓰기)는 안해도 됨   

```
{% for value in values %}
{{ value }}
{% endfor %}
```

### loop_test.py


```python
from flask import Flask, render_template
app = Flask(__name__)

@app.route('/hello_loop')
def hello_name():
    value_list = ['list1', 'list2', 'list3']
    return render_template('loop.html', values=value_list)

if __name__ == '__main__':
    app.run(host="0.0.0.0", port="8080")
```

### loop.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <ul>
      {% for value in values %}
      <li>{{ value }}</li>
      {% endfor %}
    </ul>
  </body>
</html>
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://localhost:8080/hello_loop 로 테스트해보기
</div>

### 반복문 추가 문법
- range() : 파이썬과 동일
  - for index in range(len(values)) 는 정상동작하지 않음
  
- len(values) : values | length 로 작성해야 함
- loop.index : 반복문 횟수를 반복문 안에서 가져올 수 있음
- value[index] : 파이썬 리스트와 동일



```html
    <ul>
      {% for index in range(values | length) %}
      <li>{{ values[index] }} {{ loop.index }}</li>
      {% endfor %}
    </ul>
```

### 5.3. 조건문 (Jinja2 template 문법)

### 폴더 구조

```
/condition_test.py
/templates
    /condition.html
```

### Jinja2 템플릿에서의 조건문 문법
- 기본 문법: if, elif, else, endif 로 구성 가능
  - 당연히 elif, else 는 조건에 따라 안써도 됨
```
{% if %} {% elif %} {% else %} {% endif %} 
```

- 예:
  - 인덴테이션(들여쓰기)는 안해도 됨   

```
    {% if data >= 30 %}
    <h3>30보다 큽니다.</h3>
    {% elif data > 25 %}
    <h3>25보다 큽니다.</h3>
    {% else %}
    <h3>{{ data }}</h3>
    {% endif %}
```

### condition_test.py


```python
from flask import Flask, render_template
app = Flask(__name__)

@app.route('/hello_if')
def hello_html():
    value = 27
    return render_template('condition.html', data=value)

if __name__ == "__main__":
    app.run(host="0.0.0.0", port="8080")
```

### condition.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    {% if data >= 30 %}
    <h3>30보다 큽니다.</h3>
    {% elif data > 25 %}
    <h3>25보다 큽니다.</h3>
    {% else %}
    <h3>{{ data }}</h3>
    {% endif %}
  </body>
</html>
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://localhost:8080/hello_if 로 테스트해보기
</div>

### 5.4. 주석 (Jinja2 template 문법)
- {# #} 으로 주석 표시 가능
```
{# #} 
```

### condition.html 수정

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    {% if data >= 30 %}
    <h3>30보다 큽니다.</h3>
    {% elif data > 25 %}
    <h3>25보다 큽니다.</h3>
    {# 
    {% else %}
    <h3>{{ data }}</h3>
    #} 
    {% endif %}
  </body>
</html>
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://localhost:8080/hello_if 로 테스트해보기
</div>

### 5.5. 흥미있는 테스트: 크롤링 데이터를 그대로 뿌려보면!


```python
from flask import Flask 
import requests

app = Flask(__name__)   

@app.route("/google")
def get_google():
    response = requests.get("http://www.google.co.kr")
    return response.text 

if __name__ == "__main__":
    app.run(host="0.0.0.0", port="8080")
```

     * Serving Flask app "__main__" (lazy loading)
     * Environment: production
    [31m   WARNING: This is a development server. Do not use it in a production deployment.[0m
    [2m   Use a production WSGI server instead.[0m
     * Debug mode: off
    

     * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    127.0.0.1 - - [11/Aug/2020 13:49:28] "[37mGET /google HTTP/1.1[0m" 200 -
    127.0.0.1 - - [11/Aug/2020 13:49:29] "[33mGET /images/branding/googlelogo/1x/googlelogo_white_background_color_272x92dp.png HTTP/1.1[0m" 404 -
    127.0.0.1 - - [11/Aug/2020 13:49:29] "[33mGET /textinputassistant/tia.png HTTP/1.1[0m" 404 -
    127.0.0.1 - - [11/Aug/2020 13:49:29] "[33mGET /client_204?&atyp=i&biw=1280&bih=601&ei=WCMyX4_mMcWo-Qbci5kw HTTP/1.1[0m" 404 -
    127.0.0.1 - - [11/Aug/2020 13:49:29] "[33mGET /images/nav_logo229.png HTTP/1.1[0m" 404 -
    127.0.0.1 - - [11/Aug/2020 13:49:29] "[33mGET /xjs/_/js/k=xjs.hp.en.8iDfQQEpWd0.O/m=sb_he,d/am=AJ5gcw/d=1/rs=ACT90oEyS-XCWHQjXp8ZwaF55L7rwkeVoA HTTP/1.1[0m" 404 -
    127.0.0.1 - - [11/Aug/2020 13:49:29] "[33mGET /images/nav_logo229.png HTTP/1.1[0m" 404 -
    

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://localhost:8080/google 로 테스트해보기
</div>

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 6_flask_restapi_with_vue
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 4. 실제 프론트엔드(vue)와 flask  기반 Rest API

### CDN이란?
- CDN(Contents Delivery Network) 은 지리적, 물리적으로 떨어져 있는 사용자에게 컨텐츠 제공자의 컨텐츠를 더 빠르게 제공할 수 있는 기술을 의미
- 사용자가 멀리 있는 서버로부터 컨텐츠를 다운로드 받으면, 시간이 오래 걸리므로, 사용자와 가까운 곳에 위치한 Cache Server에 해당 컨텐츠를 저장해놓고, 컨텐츠 요청시, 서버가 아닌,  Cache Server가 응답을 주는 기술
- 예: https://getbootstrap.com/docs/4.5/getting-started/introduction/

### 폴더 구성
- vue 폴더와 flask 폴더 구분
- vue 폴더에 vue_test.html 파일 생성
  - https://getbootstrap.com/docs/4.5/getting-started/introduction/ 에서 다음 템플릿 코드 복사

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
  </body>
</html>
```


> CDN 활용법: 주요 javascript, css 파일을 서버에 놓지 않고, 특정 주소를 통해 웹페이지 오픈시 자동으로 다운로드되도록 하는 방법

### Vue 코드 추가
1. ```<body>``` 태그 안에 ```<div id="app"></div>``` 로 표시될 부분을 감싸기
2. ```</body>``` 바로 위에 vue 파일을 CDN 주소로 연결

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <div id="app">      
    <h1>Hello, world!</h1>
    </div>
    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>

    <!-- Vue Start -->
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
  </body>
</html>
```

### Vue + Axios 코드 추가
- axios 로 flask Rest API 호출

- bootstrap 으로 버튼 추가

```html
      <button type="submit" class="btn btn-secondary" v-on:click="axios_test">
        GET TEST
      </button>

```

```html
    <script>
      const app = new Vue({
        el: "#app",
        methods: {
          axios_test() {
            axios("http://localhost:8082/test", {
              method: "get",
            })
              .then((response) => {
                console.log(response);
              })
              .catch((error) => {
                console.log(error);
              });
          },
        },
      });
    </script>
```

### 3. CORS(Cross Origin Resource Sharing)

- 웹에서 사용하는 HTTP request는 기본적으로 다른 도메인의 데이터를 요청할 수 있음
  - 예:
    - 내가 접속한 웹페이지: www.fun-coding.org/index.html
    - 해당 웹페이지 안에서 `<img>` 태그로 www.kkk.co.kr/google.jpg 파일을 가져와서 이미지로 보여줄 수 있음
    - 해당 웹페이지 안에서 `<link>` 태그로 www.kkk.co.kr/style.css 파일을 가져와서 CSS 스타일을 적용할 수 있음
    - **하지만! 다음 스크립트 태그로 둘러싸인 스크립트 코드에서 실행되는 HTTP request 는 www.fun-coding.org 에만 요청할 수 있음**
      - `<script></script>`
      - 정확하게는 프로토콜, 호스트명, 포트가 동일해야 함
      - 이를 **Same Origin Policy** 라고 함
      
> ajax, axios 와 같이 `<script></script>` 안에서 HTTP request 를 보낼 수 있는 기능이 생김에 따라, 
> `<script></script>` 안에서도 다른 사이트의 데이터 요청을 지원해야 한다라는 요구가 생겨서 CORS 라는 가이드가 마련됨 (각 언어별 구현)

#### Error
- HTTP Response 의 헤더에 Access-Control-Allow-Origin 관련 정보가 없으므로 브라우저 정책에 따라 Cross Domain 을 허용하지 않음
```text
Access to XMLHttpRequest at 'http://localhost:5000/payment/verify' from origin 'null' has been blocked by CORS policy: Response to preflight request doesn't pass access control check: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

### CORS 지원
- flask_cors 라이브러리 사용

```bash
pip install flask_cors
```

#### 전체 flask 서비스에 CORS 지원시


```python
from flask_cors import CORS

app = Flask(__name__)
CORS(app) # 이와 같이 선언해주면 전 요청/응답 헤더에 CORS 지원 헤더 정보를 넣어서, CORS 를 지원해줌
```

###  REST API 구현해보기
 - 특정한 URI를 요청하면 JSON 형식으로 파라미터값을 가져오고, JSON 형식으로 데이터를 반환하도록 만들면 됨
 - flask에서는 dict(사전) 데이터를 응답 데이터로 만들고, 이를 jsonify() 메서드를 활용해서 JSON 응답 데이터로 만들 수 있음

### REST API method 정의하기
- flask API 정의시, methods 에 지원하는 request method 를 작성하면 됨
  - 각 요청 메서드마다 요청 메서드에 함께 오는 파라미터값을 추출하는 방식이 다름 
    - GET/PUT/DELETE 는 동일, POST 만 다름
- API 리턴값은 flask 의 jsonify() 함수를 사용해서, JSON 형식으로 리턴값을 넣어서 보내면 됨

```python
@app.route("/test", methods=['GET', 'POST', 'PUT', 'DELETE'])
def test():
    if request.method == 'POST':
        print ('POST')
        data = request.get_json()
        print (data['email'])
    if request.method == 'GET':
        print ('GET')
        user = request.args.get('email')
        print (user)
    if request.method == 'PUT':
        print ('PUT')
        user = request.args.get('email')
        print (user)
    if request.method == 'DELETE':
        print ('DELETE')
        user = request.args.get('email')
        print (user)

    return jsonify(
        {'status': 'success'}
    )
```

### axios (frontend) 에서 각 요청 메서드와 파라미터값 전달하기

- vue template 에서 각 버튼 클릭시, 각 버튼에 연결된 함수를 호출하는 코드

```html
    <button type="submit" class="btn btn-secondary" v-on:click="test_get">GET TEST</button>
    <button type="submit" class="btn btn-secondary" v-on:click="test_post">POST TEST</button>
    <button type="submit" class="btn btn-secondary" v-on:click="test_put">PUT TEST</button>
    <button type="submit" class="btn btn-secondary" v-on:click="test_delete">DELETE TEST</button>
```

- vue 에서 axios 로 HTTP를 요청하는 코드
  - HTTP 요청 메서드는 method: 에 넣으면 됨
  - GET, PUT, DELETE 는 params 에 데이터를 JSON 형식으로 넣으면 됨
  - POST 는 data 에 데이터를 JSON 형식으로 넣으면 됨

- flask 의 jsonify() 함수를 사용해서, JSON 형식으로 리턴된 리턴값은 response.data 에 담겨져 있으므로, 해당 데이터를 JSON 데이터를 꺼내듯이 추출하면 됨

```javascript
          test_get: () => {
            axios("http://localhost:5000/test", {
              method: "get",
              params: {
                email: "test@test.com",
              }
            })
              .then((response) => {
                console.log(response.data['status']);
              })
              .catch((error) => {
                console.log(error);
              });
          },
          test_post: () => {
            axios("http://localhost:5000/test", {
              method: "post",
              data: {
                email: "test@test.com",
              }
            })
              .then((response) => {
                console.log(response.data["status"]);
              })
              .catch((error) => {
                console.log(error);
              });
          },
          test_put: () => {
            axios("http://localhost:5000/test", {
              method: "put",
              params: {
                email: "test@test.com",
              }
            })
              .then((response) => {
                console.log(response.data["status"]);
              })
              .catch((error) => {
                console.log(error);
              });
          },
          test_delete: () => {
            axios("http://localhost:5000/test", {
              method: "delete",
              params: {
                email: "test@test.com",
              }
            })
              .then((response) => {
                console.log(response.data["status"]);
              })
              .catch((error) => {
                console.log(error);
              });
          }
```

### HTTP 요청 메서드 (request method)
- 클라이언트(client)가 서버(server)에 HTTP 요청시 요청 목적을 알리는 표시
- 크게 GET, POST, PUT, DELETE 방식이 있으며, 이 중에서 GET 과 POST 방식을 많이 사용함
- 요청 메서드에 따라 요청 데이터를 전달하는 방식에 차이가 있음

### 주요 Request Method in HTML
- HTML 에서는 GET 과 POST 만 지원함

- GET: 정보 읽기(SELECT)
  - 전달이 필요한 파라미터들은 URL을 통해 전달
<center><img src="https://www.fun-coding.org/00_Images/http_method_get.png"/></center>

- POST: 정보 입력하기(INSERT)
  - 전달이 필요한 파라미터들은 HTTP body에 포함되어 전달되므로, 사용자는 직접적인 확인 불가
<center><img src="https://www.fun-coding.org/00_Images/http_method_post.png"/></center>

- PUT: 정보 수정하기(UPDATE), DELETE: 정보 삭제하기(DELETE)
  - GET 과 마찬가지로 파라미터들이 URL을 통해 전달

> 사실상 GET 또는 POST 방식을 많이 사용하며, POST 방식이 파라미터 정보를 노출하지 않으므로 POST 방식을 선호 <br>
> 단, 요청 기능에 따라 GET, POST, PUT, DELETE HTTP 메서드를 쓰는 것을 권장하고는 있음 ('Restful 하다' 라고 이야기함)


<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 7_flask_others
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 6. flask 다양한 기능

### 6.1. 에러(error) 다루기

* errorhandler를 사용하여 HTTP 오류 코드가 나오는 페이지를 정의할 수 있음
  - return 의 두번째 인자로 에러코드를 넘겨주지 않으면 200 성공으로 인지함
  
> HTTP 응답코드와 프로토콜에 대해서는 별도 챕터에서 설명


```python
@app.errorhandler(404)  # 없는 페이지를 요청했을 때의 에러
def page_not_found(error):
    return "<h1>404 Error</h1>", 404
```


```python
from flask import Flask 
import requests

app = Flask(__name__)   

@app.errorhandler(404)
def page_not_found(error):
    return "<h1>404 Error</h1>", 404

@app.route("/google")
def get_google():
    response = requests.get("http://www.google.co.kr")
    return response.text 

if __name__ == "__main__":
    app.run(host="0.0.0.0", port="8080")
```

### 6.2. 로깅(logging) 다루기
- 서버는 24시간 동작하므로, 문제가 있을 때, 어떤 문제가 있었는지, 파악하기 위해 로깅 기능을 사용함
- 사용자 모니터링, 해킹 확인등 다양한 상용화시 문제에 대해서도 로깅 기능을 활용할 수 있음

> 로깅은 개발 단계에서는 크게 필요하지 않으므로, 가볍게 참고로만 알아둠 <br>
> 추후 상용화 단계에서 추가 기능을 넣어서 구현 예정

### 간단한 logging 라이브러리 사용법

- 파이썬에는 로그를 다루는 logging 라이브러리가 있음
- 로딩 정보는 레벨이 있음
- 로깅 정보는 로그의 레벨에 따라서 출력을 제한 할 수 있음
  - DEBUG > INFO > WARNING > ERROR > Critical


```python
import logging
# 파일로 남기기 위해서는 filename='test.log' 파라미터, 어느 로그까지 남길 것인지를 level 로 설정 가능
logging.basicConfig(filename='test.log', level=logging.ERROR)

# 로그를 남길 부분에 다음과 같이 로그 레벨에 맞추어 출력해주면 해당 내용이 파일에 들어감
logging.debug("debug")
logging.info("info")
logging.warning("warning")
logging.error("error")
logging.critical("critical")
```

### flask 와 logging
- logging 라이브러리와 함께 flask logging 기능 사용 가능
- 주요 logging 핸들러 (어떻게 로그를 다룰 것인지에 대해 미리 구현된 함수들을 제공)
  - FileHandler - 파일로 로그를 저장
  - RotatingFileHandler - 파일로 로그를 저장하되, 파일이 정해진 사이즈를 넘어가면, 새로운 파일로 생성
    - maxBytes=하나의파일사이즈, backupCount=파일갯수
    - 전체 파일을 다 쓰면, 다시 처음부터 씀
  - NTEventLogHandler - 윈도우 시스템 로그로 남김
  - SysLogHandler - 유닉스 계열 시스템의 syslog 로 남김

> 서버 상에서는 로그 파일이 전체 디스크를 채울 경우, 비정상동작을 할 수 있으므로 RotatingFileHandler 가 일반적인 경우에는 적합 

- 다음과 같이 작성해서 로그로 남길지 여부를 설정 가능

```python
import logging
from logging.handlers import RotatingFileHandler # logging 핸들러 이름을 적어줌

app.debug = True
if app.debug:
    file_handler = RotatingFileHandler('dave_server.log', maxBytes=2000, backupCount=10) 
    file_handler.setLevel(logging.WARNING) # 어느 단계까지 로깅을 할지를 적어줌
    app.logger.addHandler(file_handler) # app.logger.addHandler() 에 등록시켜줘야 app.logger 로 사용 가능
```

### @app.errorhandler 와 HTTP 상태 코드 (요약 리스트)

* **가장 일반적인 사용법:** `@app.errorhandler()`에 **HTTP 상태 코드(정수)**를 인자로 전달합니다.
* **목적:** 특정 HTTP 오류 발생 시 실행될 함수를 지정합니다.
* **주요 예시:**
    * `@app.errorhandler(404)`: 페이지 찾을 수 없음 (Not Found)
    * `@app.errorhandler(500)`: 서버 내부 오류 (Internal Server Error)
    * `@app.errorhandler(403)`: 접근 권한 없음 (Forbidden)
    * `@app.errorhandler(400)`: 잘못된 요청 (Bad Request)


```python
from flask import Flask 
import logging
from logging.handlers import RotatingFileHandler # logging 핸들러 이름을 적어줌

app = Flask(__name__)

app.debug = True
if app.debug:
    file_handler = RotatingFileHandler('dave_server.log', maxBytes=2000, backupCount=10) 
    file_handler.setLevel(logging.WARNING) # 어느 단계까지 로깅을 할지를 적어줌
    app.logger.addHandler(file_handler) # app.logger.addHandler() 에 등록시켜줘야 app.logger 로 사용 가능

@app.errorhandler(404)
def page_not_found(error):
    app.logger.error(error)
    return "<h1>404 Error</h1>", 404

if __name__ == "__main__":
    app.run(host="0.0.0.0", port="8080")
```

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">실습하기</font><br>
http://localhost:8080/test 로 테스트해보기
</div>

### 6.3. 다양한 데코레이터
* before_request : HTTP 요청이 들어올 때마다 실행
  - before_request는 인자를 전달할 수는 없음
* after_request : HTTP 요청 처리가 끝나고 브라우저에 응답하기 전에 실행
  - response 를 인자로 받아야 하고, response 를 리턴해야 함


```python
from flask import Flask, request

app = Flask(__name__)

# 첫 번째 요청 여부를 추적하기 위한 전역 변수
initialized = False

# 첫 번째 요청 전에 실행될 함수
def before_first_request():
    print("flask 실행 후 첫 요청 때만 실행")

# 모든 요청 전에 실행될 함수
@app.before_request
def before_request():
    global initialized
    if not initialized:
        before_first_request()
        initialized = True
    print("HTTP 요청이 들어올 때마다 실행")

# 모든 요청 후에 실행될 함수
@app.after_request
def after_request(response):
    print("HTTP 요청 처리가 끝나고 브라우저에 응답하기 전에 실행")
    return response

@app.route("/hello")
def hello():
    return "<h1>Hello Flask!</h1>"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=8080)
```

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 8_flask_blog_start
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 7. 핵심 기능을 가진 웹서비스 구현

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">지금까지 익힌 flask 기술 기반으로도 풀스택 웹서비스 구현 가능</font><br>
- flask 를 기반으로 백엔드/프론트엔드 구현 <br>
- HTML/CSS 등 프론트엔드 요소는 부트스트랩 UI 프레임워크의 예제를 간단히 수정만 해서 사용 <br>
  - 백엔드를 익히는 강좌이므로, 관련 부분에 대해서는 모른다고 가정하고, 가볍게 예제 기반, 수정 방법을 가이드함
- 실제 현업과 마찬가지로 가벼운 기획과 MVP 설정 <br>
    - <b>현업 이해도를 높이기 위해 초간단 웹서비스 ABTest 기능 구현</b> <br>
</div>

### 웹서비스 기획에 대한 가벼운 이해

### MVP (Minimum Viable Product)
- 최소한의 기능을 구현한 제품
- 고객의 피드백을 받아서, 기능을 점차적으로 개선
- 최근 스타트업이 개발하는 방식


### 기본 목표 프로그램
- 블로그 사이트를 구현 예정
  - 블로그 페이지를 웹으로 오픈
  - ABTest 로 고객에게 다른 페이지를 보여주는 기능
  - 각 페이지마다 고객 이메일 구독 유도 기능
  - 이메일 구독시, 이메일 저장 기능
  - 이메일 구독시, 고객에게 이메일 구독중임을 알려주는 기능
  - 각 페이지에 얼마나 많은 사람들이 접근했는지 접근 시간 저장 기능



### 웹서비스 구현을 위해 알아둬야 하는 MVC 패턴
- **M**odel-**V**iew-**C**ontroller : **소프트웨어 공학 학문 분야**에서 나온 아키텍쳐 
  - Model: 응용 프로그램의 데이터를 나타냄 (주로 데이터베이스)
  - View: 텍스트, 버튼등 사용자 인터페이스를 나타냄 (웹페이지)
  - Controller: Model 과 View 를 제어하는 중간 역할 (중간 제어 코드)
- MVC 패턴대로 코드를 작성하면, 유지보수가 쉬워진다는 주장을 한 것임

#### 실제로는 그렇지 않은 경우가 많음
- MVC 패턴은 하나의 기능을 구현하는데 각 기능이 여러 파일에 쪼개져 있으므로, 코드 이해/디버깅이 어려움
- 코드 수정시, 결국 MVC 특정 부분만 수정하기 보다, 전체 연결된 기능 관련 코드를 수정하는 경우가 더 많아지는 경우도 많음

> 기존 코드가 MVC 패턴이면, 기존 코드 구조에 맞게 작성, 그렇지 않으면 참고만 하세요

### 구현할 기능
- flask 로 프론트엔드와 백엔드를 모두 구현
- 블로그 페이지 제목만 변경하여, 두 가지 버전 구현
- 동일한 라우팅 경로 접속시마다 두 가지 버전 중 하나가 보여지도록 함 (A: 50%, B: 50%)
  - 접속 IP 와 접속시간을 로그로 남김
- 구독시 이메일 주소를 받아서 저장함
  - 해당 사용자는 flask 서버가 재실행되지 않는 이상, 동일 블로그 페이지가 보여지고, 구독창이 더이상 뜨지 않도록 함
  
> 이런 서비스 구현 후, 많은 사용자를 기반으로 실험해본다면, 어떤 블로그 제목이 더 구독자를 많이 끌어모을 수 있는지를 로그 분석을 기반으로 알 수 있음 <br>
> 라우팅 경로를 무한히 만들어, 다양한 블로그 서비스 가능

### MVC 패턴과 flask blueprint

- 한 파일에 모든 기능 코드를 넣으면, 복잡해지고, 관리가 어려움
- re-usability 를 항상 생각해야 함
  - 다만, 그렇다고 대형 프로그램에서나 필요한 구조를 가져갈 필요는 없음

### flask 백엔드 코드 구조
- 기능별로 폴더/파일 구분 (blueprint 를 사용해서, 기능별로 추가/삭제가 쉽도록 구성)
- MVC 에서 View 에 해당하는 부분은 없음 (순수 Rest API 서버로, 추후 해당 API 를 사용한 프론트앤드 별도 구축)
- C 는 API, M 은 데이터베이스/데이터 모델 로만 구성하면 됨

> **Simple is Best!**

### 기능별로 폴더를 나눠서 코드 구현하기로 함
- 간단한 코드일 경우, MVC 패턴을 사용하면, 코드 구현 및 확인을 위해 여러 소스파일을 참고해야 하므로 오히려 시간이 많이 걸림
  - MVC 패턴은 매우 복잡한 기능을 가진 큰 규모의 시스템에서, 일부 유용할 수 있음
- 하지만, 기본적인 MVC 패턴 이해를 위해, 다음과 같이 구성
  - flask 서버: blog_abtest.py 
  - <b>M</b>odel: db_model
  - <b>V</b>iew: blog_view
  - <b>C</b>ontrol: blog_control
  - 이외에 
    - static 은 부트스트랩등 HTML 파일에서 필요로 하는 동일 서버 내의 javascript 와 css 파일
    - templates 는 flask 서버가 지원하는 HTML 파일
    
```bash
.
├── blog_abtest.py
├── blog_control
│   ├── session_mgmt.py
│   └── user_mgmt.py
├── blog_view
│   └── blog.py
├── db_model
│   ├── mongodb.py
│   └── mysql.py
├── schema.sql
├── static
│   ├── blog.css
│   ├── brand
│   └── dist
└── templates
    ├── blog_A.html
    └── blog_B.html
```

### flask blueprint
- 여러 소스 파일에 flask 코드를 작성할 수 있도록 하는 기능

- 메인 코드 파일 내

```python
from flask import Flask
from 하위폴더명(폴더명이 blog_view 이면 blog_view) import 하위폴더의소스파일명(blog.py 이면 blog)

app = Flask(__name__)
app.register_blueprint(하위폴더의소스파일명.블루프린트객체이름, url_prefix='/blog')
```
- url_prefix=기본경로명
  - 하위폴더의 소스파일에 있는 라우팅 경로는 URL/기본경로명/라우팅 경로 와 같이 설정됨

- 분리된 하위 폴더의 소스 파일 내
  - Blueprint(블루프린트이름, __name__) 으로 작성
  
```python
from flask import Blueprint
# 블루프린트객체이름은 blog_abtest 가 됨
blog_abtest = Blueprint('blog', __name__)

# http://localhost:8080/blog/blog1
@blog_abtest.route('/blog1')
def blog():
    return "blueprint test login_google"
```


```python
# dave_server.py
from flask import Flask
from test_view import blog_view

app = Flask(__name__)
app.register_blueprint(blog_view.blog_ab, url_prefix='/blog')

if __name__ == '__main__':
    app.run(host='0.0.0.0', port='8080')
```


```python
# blog.py
from flask import Blueprint

blog_ab = Blueprint('blog', __name__)

# http://localhost:8080/blog/blog1
@blog_ab.route('/blog1')
def blog():
    return 'TEST BLUEPRINT'
```

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 9_flask_mysql_mongodb
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 8. flask 와 데이터베이스
- 실제 웹서비스에서는 다양한 데이터베이스를 사용함
- 변경 여지가 적은 경우, mysql 과 같은 관계형 데이터베이스 사용
  - 가장 정보가 많고, 수십년간 사용되었기 때문에 보안, 안정적임
- 변경 여지가 큰 웹서비스 로깅(logging)을 위해서는 NoSQL 을 사용
- 이외에 웹서비스 성능 향상을 위해 redis 와 같은 in-memory 방식의 데이터베이스도 많이 사용됨

> 기존 강좌에서 다뤘던 mysql(SQL) 과 mongodb(NoSQL) 에 대해 간단한 웹서비스 구현을 위한 사전 작업과 함께, 기존 강좌의 핵심 내용 정리

### 블로그 기능과 데이터베이스 활용
- mysql: 구독으로 얻어진 이메일 주소 정보를 저장
- mongodb: 블로그 접근 사용자의 IP 와 접근 시간을 로그 형태로 저장 
  - logging 라이브러리로 파일로 저장하지 않고, 몽고db를 활용
  - 몽고db가 익숙치 않을 경우, logging 라이브러리로도 활용 가능
  - 로깅은 통상적으로 수시로 포맷이 바뀌는 경우가 많으므로, 스키마 설정이 필요없는 NoSQL 이 적합

## 8.1. flask 와 MySQL 사용
- mongodb 는 크롤링 데이터등과 같이 방대하지만, 일부 유실되도 큰 문제없는 데이터 처리시 더 적합
- 규격화되고 각 데이터의 극도의 안정성이 필요한 데이터는 MySQL 이 더 적합

### SQLAlchemy VS Pymysql
- Django 등에서 다양한 데이터베이스를 객체로 만들어서, 사용법을 통일하는 기법으로 SQLAlchemy 라는 기능을 사용함
- SQL 이외에 추가적인 SQLAlchemy 기반 CRUD 기법을 익혀야 함 
- 현 단계(입문에서 백엔드개발로 넘어오는 단계) 에서는 SQL, mongodb CRUD 에 익숙해지는 것이 보다 중요함
- 이후 FastAPI 백엔드 강의에서 SQLAlchemy 상세 문법과 실습도 진행함

<center><img src="https://www.fun-coding.org/00_Images/fullstackroadmap_2024_v4.png"></center>

### pymysql 라이브러리 소개 및 설치
* mysql을 python에서 사용할 수 있는 라이브러리 (pymysql 라이브러리 이외에도 MySQLdb(Mysql-pytion), MySQL connector 등 다양한 라이브러리 존재)
* 설치: `pip install PyMySQL`
* 일반적인 mysql 핸들링 코드 작성 순서
  1. PyMySql 모듈 import
  2. pymysql.connect() 메소드를 사용하여 MySQL에 연결
     - 호스트명, 포트, 로그인, 암호, 접속할 DB 등을 파라미터로 지정
  3. MySQL 접속이 성공하면, Connection 객체로부터 cursor() 메서드를 호출하여 Cursor 객체를 가져옴
  4. Cursor 객체의 execute() 메서드를 사용하여 SQL 문장을 DB 서버에 전송
  5. SQL 쿼리의 경우 Cursor 객체의 fetchall(), fetchone() 등의 메서드를 사용하여 서버로부터 가져온 데이타를 코드에서 활용
  6. 삽입, 갱신, 삭제 등의 SQL 구문을 실행하는 경우는 INSERT/UPDATE/DELETE 후 Connection 객체의 commit() 메서드를 사용하여 데이타를 확정
  7. Connection 객체의 close() 메서드를 사용하여 DB 연결을 닫음

### Pymysql 로 mysql 접속
* pymysql.connect() 메소드를 사용하여 MySQL에 연결
     - 호스트명, 포트, 로그인, 암호, 접속할 DB 등을 파라미터로 지정
     - 주요 파라미터
       - host : 접속할 mysql server 주소
       - port : 접속할 mysql server 의 포트 번호
       - user : mysql ID
       - passwd : mysql ID의 암호
       - db : 접속할 데이터베이스
       - charset='utf8' : mysql에서 select하여 데이타를 가져올 때 한글이 깨질 수 있으므로 연결 설정에 넣어줌

### 사전 작업
```
CREATE DATABASE blog_db;
```

### 참고: mysql 에 별도 ID 생성
```
mysql -u root -p
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost';
CREATE USER 'dave'@'localhost' IDENTIFIED BY 'funcoding';
GRANT ALL PRIVILEGES ON *.* TO 'dave'@'localhost';
flush privileges;
```


```python
import pymysql

db_conn = pymysql.connect(
        host='localhost', 
        port=3306, 
        user='dave', 
        passwd='funcoding', 
        db='blog_db', 
        charset='utf8')
```

### 사용자 테이블
- USER_ID 로 사용자 정보를 접근
- USER_EMAIL 도 unique 해야 하지만 동일한 USER_EMAIL 은 입력 코드에서 체크하기로 함

```sql
CREATE TABLE user_info (
    USER_ID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    USER_EMAIL VARCHAR(100) NOT NULL,
    BLOG_ID CHAR(4),
    PRIMARY KEY(USER_ID)
);
```

### mysql 테스트

> 실제 flask 코드에 넣어서 테스트할 경우, 테스트에 굉장한 시간 소요
> 필요한 테스트는 주피터 노트북상에서 가능한 많이 한 후에, 최종 결과가 될 수 있는 코드만 flask 코드로 변환


```python
import pymysql

db_conn = pymysql.connect(
        host='localhost', 
        port=3306, 
        user='dave', 
        passwd='funcoding', 
        db='blog_db', 
        charset='utf8')

dave_db = db_conn.cursor()
dave_db
```




    <pymysql.cursors.Cursor at 0x7f9e2709b390>



### 기존 테이블 수 확인하기


```python
sql = 'SHOW TABLES;'
dave_db.execute(sql)
```




    1




```python
sql = """
CREATE TABLE user_info (
    USER_ID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    USER_EMAIL VARCHAR(100) NOT NULL,
    BLOG_ID CHAR(4),
    PRIMARY KEY(USER_ID)
);
"""
dave_db.execute(sql)
db_conn.commit() # 데이터베이스를 변경하는 명령은 commit() 해주기
```

### 테이블 수 확인하기
- 테이블 생성되었으므로 테이블 수가 1이어야 맞음


```python
sql = 'SHOW TABLES;'
dave_db.execute(sql)
```




    1



### 테이블 삭제하기


```python
sql = 'DROP TABLE user_info;'
dave_db.execute(sql)
db_conn.commit() # 데이터베이스를 변경하는 명령은 commit() 해주기
```

### 테이블 수 확인하기
- 테이블 생성되었으므로 테이블 수가 1이어야 맞음


```python
sql = 'SHOW TABLES;'
dave_db.execute(sql)
```




    0



### 테이블 재생성하기


```python
sql = """
CREATE TABLE user_info (
    USER_ID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    USER_EMAIL VARCHAR(100) NOT NULL,
    BLOG_ID CHAR(4),
    PRIMARY KEY(USER_ID)
);
"""
dave_db.execute(sql)
db_conn.commit() # 데이터베이스를 변경하는 명령은 commit() 해주기
```

### 테이블에 데이터 넣기


```python
user_email = 'test@test.com'
blog_id = 'A'
```


```python
sql = "INSERT INTO user_info (USER_EMAIL, BLOG_ID) VALUES ('%s', '%s')" % (str(user_email), str(blog_id))
dave_db.execute(sql)
db_conn.commit() # 데이터베이스를 변경하는 명령은 commit() 해주기
```

### 테이블 데이터 조회(SELECT)
  - Cursor Object 가져오기: cursor = db.cursor()  
  - SQL 실행하기: cursor.execute(SQL)
  - mysql 서버로부터 데이터 가져오기: fetch 메서드 사용
    - fetchall(): Fetch all the rows
    - fetchmany(size=None): Fetch several rows
    - fetchone(): Fetch the next row


```python
sql = "SELECT * FROM user_info"
dave_db.execute(sql)
results = dave_db.fetchall()
for result in results:
    print (result, type(result))
```

    (2, 'jhleeroot@gmail.com', 'A') <class 'tuple'>
    (3, 'dave@gmail.com', 'A') <class 'tuple'>
    (4, 'dream@fun-coding.org', 'A') <class 'tuple'>
    

### USER_EMAIL 로 테이블 데이터 조회


```python
user_id = 1
```


```python
sql = "DELETE FROM user_info WHERE USER_ID = %d" % (user_id)
print(dave_db.execute(sql))
db_conn.commit() # 데이터베이스를 변경하는 명령은 commit() 해주기
```

    0
    

### 데이터베이스 연결 해제


```python
db_conn.close()
```

### 참고: 데이터베이스 데이터 삭제하기
- 강좌 후반부 실제 구현시 관련 내용을 영상으로 보여드림


```python
import pymysql

db_conn = pymysql.connect(
        host='localhost', 
        port=3306, 
        user='dave', 
        passwd='funcoding', 
        db='blog_db', 
        charset='utf8')

dave_db = db_conn.cursor()
dave_db
```




    <pymysql.cursors.Cursor at 0x7f9e270a07d0>




```python
sql = "SELECT * FROM user_info"
dave_db.execute(sql)
results = dave_db.fetchall()
for result in results:
    print (result, type(result))
```

    (2, 'jhleeroot@gmail.com', 'A') <class 'tuple'>
    (3, 'dave@gmail.com', 'A') <class 'tuple'>
    


```python
user_id = 4
```


```python
sql = "DELETE FROM user_info WHERE USER_ID = %d" % (user_id)
print(dave_db.execute(sql))
db_conn.commit() # 데이터베이스를 변경하는 명령은 commit() 해주기
```

    0
    

## 8.2. Mongodb 설치 필요

> mongodb 강의에서 해당 강좌는 무료로 오픈해놓았으니 수강하셔서 확인도 가능합니다

### Mongodb 연결


```python
import pymongo

username = ''
password = ''
ip_address = 'localhost'
connection = pymongo.MongoClient()
connection = pymongo.MongoClient('mongodb://%s' % (ip_address))
# connection = pymongo.MongoClient('mongodb://%s:%s@%s' % (username, password, ip_address))
blog_session_db = connection.blog_session_db
blog_ab = blog_session_db.blog_ab
```

### Mongodb 연결 확인
- mongodb 연결을 한번 해놓으면, 이론적으로는 해당 객체를 사용, 몽고db CRUD 를 실행하면 됨
- 하지만, 실제로는 mongodb 가 다양한 원인으로 다운되거나, 연결이 해제되는 경우가 있음
  - 이 경우, 연결이 되어있음을 가정하고, CRUD를 실행할 경우 에러가 남
- 따라서 연결된 객체가 아직 mongodb 에 연결이 되어있는지 체크하는 방법이 필요함
  - 물론, 이 방법도 mongodb 가 아예 다운된 경우등을 체크하도록 코드를 더 정교하게 작성할 수도 있지만,
  - 문제를 mongodb 는 다운되더라도 재기동된다고 가정하고, (docker 등 다른 시스템을 통해 해당 기능 활성화)
  - 연결이 해제된 경우만 체크하는 기법을 사용 
    - 특별한 방법이 없으므로, 가장 간단한 명령을 내려보는 방법으로 진행


```python
connection.admin.command('ismaster')
```




    {'ismaster': True,
     'maxBsonObjectSize': 16777216,
     'maxMessageSizeBytes': 48000000,
     'maxWriteBatchSize': 100000,
     'localTime': datetime.datetime(2020, 8, 15, 7, 25, 55, 594000),
     'logicalSessionTimeoutMinutes': 30,
     'connectionId': 61,
     'minWireVersion': 0,
     'maxWireVersion': 8,
     'readOnly': False,
     'ok': 1.0}




```python
connection.server_info()
```




    {'version': '4.2.8',
     'gitVersion': '43d25964249164d76d5e04dd6cf38f6111e21f5f',
     'modules': [],
     'allocator': 'system',
     'javascriptEngine': 'mozjs',
     'sysInfo': 'deprecated',
     'versionArray': [4, 2, 8, 0],
     'openssl': {'running': 'Apple Secure Transport'},
     'buildEnvironment': {'distmod': '',
      'distarch': 'x86_64',
      'cc': '/Applications/Xcode10.2.0.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/clang: Apple LLVM version 10.0.1 (clang-1001.0.46.3)',
      'ccflags': '-isysroot /Applications/Xcode10.2.0.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk -mmacosx-version-min=10.12 -target darwin16.0.0 -arch x86_64 -fno-omit-frame-pointer -fno-strict-aliasing -ggdb -pthread -Wall -Wsign-compare -Wno-unknown-pragmas -Winvalid-pch -Werror -O2 -Wno-unused-local-typedefs -Wno-unused-function -Wno-unused-private-field -Wno-deprecated-declarations -Wno-tautological-constant-out-of-range-compare -Wno-tautological-constant-compare -Wno-tautological-unsigned-zero-compare -Wno-tautological-unsigned-enum-zero-compare -Wno-unused-const-variable -Wno-missing-braces -Wno-inconsistent-missing-override -Wno-potentially-evaluated-expression -Wno-unused-lambda-capture -Wno-exceptions -Wunguarded-availability -fstack-protector-strong -fno-builtin-memcmp',
      'cxx': '/Applications/Xcode10.2.0.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/clang++: Apple LLVM version 10.0.1 (clang-1001.0.46.3)',
      'cxxflags': '-Woverloaded-virtual -Werror=unused-result -Wpessimizing-move -Wredundant-move -Wno-undefined-var-template -Wno-instantiation-after-specialization -fsized-deallocation -stdlib=libc++ -std=c++17',
      'linkflags': '-Wl,-syslibroot,/Applications/Xcode10.2.0.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk -mmacosx-version-min=10.12 -target darwin16.0.0 -arch x86_64 -Wl,-bind_at_load -Wl,-fatal_warnings -fstack-protector-strong -stdlib=libc++',
      'target_arch': 'x86_64',
      'target_os': 'macOS'},
     'bits': 64,
     'debug': False,
     'maxBsonObjectSize': 16777216,
     'storageEngines': ['biggie', 'devnull', 'ephemeralForTest', 'wiredTiger'],
     'ok': 1.0}



### INSERT


```python
blog_ab.insert_one({'emailid':'jhleeroot@gmail.com'})
```




    <pymongo.results.InsertOneResult at 0x7f9a8e32d960>



### SELECT


```python
blog_ab.find_one( {'emailid':'jhleeroot@gmail.com'} )
```




    {'_id': ObjectId('5f34e53a2171fe53b403d027'), 'emailid': 'jhleeroot@gmail.com'}



### DELETE


```python
blog_ab.delete_one( {'emailid':'jhleeroot@gmail.com'} )
```




    <pymongo.results.DeleteResult at 0x7f9a8e365b40>



### SELECT *


```python
blog_logs = blog_ab.find()
for log in blog_logs:
    print(log)
```

    {'_id': ObjectId('5f36362bd30e2ec7d748d6e9'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'access_time': '14/08/2020 15:58:51'}
    {'_id': ObjectId('5f36362bd30e2ec7d748d6eb'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'access_time': '14/08/2020 15:58:51'}
    {'_id': ObjectId('5f363660d30e2ec7d748d6ed'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'access_time': '14/08/2020 15:59:44'}
    {'_id': ObjectId('5f36366dd30e2ec7d748d6ef'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'access_time': '14/08/2020 15:59:57'}
    {'_id': ObjectId('5f36372b043800e068a3edb9'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '14/08/2020 16:03:07'}
    {'_id': ObjectId('5f36372f043800e068a3edbb'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '14/08/2020 16:03:11'}
    {'_id': ObjectId('5f363734043800e068a3edbd'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '14/08/2020 16:03:16'}
    {'_id': ObjectId('5f363cddcffa954628adc169'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '14/08/2020 16:27:25'}
    {'_id': ObjectId('5f37632d4c602baac5341f2c'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:23:09'}
    {'_id': ObjectId('5f37632f4c602baac5341f2e'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:23:11'}
    {'_id': ObjectId('5f3763334c602baac5341f30'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:23:15'}
    {'_id': ObjectId('5f3763344c602baac5341f32'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:23:16'}
    {'_id': ObjectId('5f3763354c602baac5341f34'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:23:17'}
    {'_id': ObjectId('5f3763374c602baac5341f36'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:23:19'}
    {'_id': ObjectId('5f3763384c602baac5341f38'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:23:20'}
    {'_id': ObjectId('5f3763394c602baac5341f3a'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:23:21'}
    {'_id': ObjectId('5f3763394c602baac5341f3c'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:23:21'}
    {'_id': ObjectId('5f37633b4c602baac5341f3e'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:23:23'}
    {'_id': ObjectId('5f376365e920969e033c591e'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:05'}
    {'_id': ObjectId('5f376365e920969e033c5920'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:24:05'}
    {'_id': ObjectId('5f376366e920969e033c5922'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:06'}
    {'_id': ObjectId('5f376369e920969e033c5924'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:09'}
    {'_id': ObjectId('5f37636ae920969e033c5926'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:10'}
    {'_id': ObjectId('5f37636be920969e033c5928'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:11'}
    {'_id': ObjectId('5f376375e920969e033c592a'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:21'}
    {'_id': ObjectId('5f376376e920969e033c592c'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:24:22'}
    {'_id': ObjectId('5f3765f8d2ad6b71e5970b2f'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:35:04'}
    {'_id': ObjectId('5f3765fbd2ad6b71e5970b31'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:35:07'}
    {'_id': ObjectId('5f376619d2ad6b71e5970b33'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:35:37'}
    {'_id': ObjectId('5f376641d2ad6b71e5970b35'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 13:36:17'}
    {'_id': ObjectId('5f376649d2ad6b71e5970b37'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:36:25'}
    {'_id': ObjectId('5f376668d2ad6b71e5970b39'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:36:56'}
    {'_id': ObjectId('5f376673d2ad6b71e5970b3b'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:37:07'}
    {'_id': ObjectId('5f376692d2ad6b71e5970b3d'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 13:37:38'}
    {'_id': ObjectId('5f378e22b0f391a391291cc5'), 'emailid': 'jhleeroot@gmail.com'}
    {'_id': ObjectId('5f3790b127142a0c16f9e0c9'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 16:37:21'}
    {'_id': ObjectId('5f3790b327142a0c16f9e0cb'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 16:37:23'}
    {'_id': ObjectId('5f3790c927142a0c16f9e0cd'), 'session_ip': '127.0.0.1', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 16:37:45'}
    {'_id': ObjectId('5f3795122eca64cf5477d2a4'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 16:56:02'}
    {'_id': ObjectId('5f3795162eca64cf5477d2a6'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 16:56:06'}
    {'_id': ObjectId('5f37963d2eca64cf5477d2a8'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:01:01'}
    {'_id': ObjectId('5f37969d2eca64cf5477d2aa'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:02:37'}
    {'_id': ObjectId('5f379ceddcebda5dc50bc5ff'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:29:33'}
    {'_id': ObjectId('5f379cf1dcebda5dc50bc601'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:29:37'}
    {'_id': ObjectId('5f379cfe42d06e6eea66e3f2'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:29:50'}
    {'_id': ObjectId('5f379cff42d06e6eea66e3f4'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:29:51'}
    {'_id': ObjectId('5f379d21968b9888985d3f74'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:30:25'}
    {'_id': ObjectId('5f379d25968b9888985d3f76'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:30:29'}
    {'_id': ObjectId('5f379d339c299e2cd3279ecb'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:30:43'}
    {'_id': ObjectId('5f379d5dc96379d42af666ee'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:31:25'}
    {'_id': ObjectId('5f379d60c96379d42af666f0'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:31:28'}
    {'_id': ObjectId('5f379d693294dbc555bbe741'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:31:37'}
    {'_id': ObjectId('5f379f09f7377e47140f4486'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:38:33'}
    {'_id': ObjectId('5f379f3554325706bcb76545'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:39:17'}
    {'_id': ObjectId('5f379f3654325706bcb76547'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '15/08/2020 17:39:18'}
    {'_id': ObjectId('5f37a07ee470163669d97fd0'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:44:46'}
    {'_id': ObjectId('5f37a082e470163669d97fd2'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '15/08/2020 17:44:50'}
    {'_id': ObjectId('5f38d3011f03a27627a61de8'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:32:33'}
    {'_id': ObjectId('5f38d3051f03a27627a61dea'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '16/08/2020 15:32:37'}
    {'_id': ObjectId('5f38d30d1f03a27627a61dec'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:32:45'}
    {'_id': ObjectId('5f38d404fa835e2a15457254'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:36:52'}
    {'_id': ObjectId('5f38d407fa835e2a15457256'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '16/08/2020 15:36:55'}
    {'_id': ObjectId('5f38d40dfa835e2a15457258'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:37:01'}
    {'_id': ObjectId('5f38d40efa835e2a1545725a'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:37:02'}
    {'_id': ObjectId('5f38d40ffa835e2a1545725c'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:37:03'}
    {'_id': ObjectId('5f38d40ffa835e2a1545725e'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:37:03'}
    {'_id': ObjectId('5f38d410fa835e2a15457260'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 15:37:04'}
    {'_id': ObjectId('5f38defa34213b984bbcbc6f'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 16:23:38'}
    {'_id': ObjectId('5f38e434704a2b25147ce925'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 16:45:56'}
    {'_id': ObjectId('5f38e434704a2b25147ce927'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '16/08/2020 16:45:56'}
    {'_id': ObjectId('5f38e9c8d2ec0435489632c7'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '16/08/2020 17:09:44'}
    {'_id': ObjectId('5f39e30a4353de02944bc5e6'), 'session_ip': '192.168.35.190', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 10:53:14'}
    {'_id': ObjectId('5f39e3144353de02944bc5e8'), 'session_ip': '192.168.35.84', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 10:53:24'}
    {'_id': ObjectId('5f39e3184353de02944bc5ea'), 'session_ip': '192.168.35.84', 'user_email': 'dream@fun-coding.org', 'page': 'blog_A.html', 'access_time': '17/08/2020 10:53:28'}
    {'_id': ObjectId('5f39e31e4353de02944bc5ec'), 'session_ip': '192.168.35.190', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 10:53:34'}
    {'_id': ObjectId('5f39e3214353de02944bc5ee'), 'session_ip': '192.168.35.190', 'user_email': 'jhleeroot@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 10:53:37'}
    {'_id': ObjectId('5f39e3224353de02944bc5f0'), 'session_ip': '192.168.35.84', 'user_email': 'dream@fun-coding.org', 'page': 'blog_A.html', 'access_time': '17/08/2020 10:53:38'}
    {'_id': ObjectId('5f3a3218de04be4c3f1ea802'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:30:32'}
    {'_id': ObjectId('5f3a3219de04be4c3f1ea804'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 16:30:33'}
    {'_id': ObjectId('5f3a321dde04be4c3f1ea806'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:30:37'}
    {'_id': ObjectId('5f3a322ade04be4c3f1ea808'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:30:50'}
    {'_id': ObjectId('5f3a3245de04be4c3f1ea80a'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:31:17'}
    {'_id': ObjectId('5f3a324ede04be4c3f1ea80c'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:31:26'}
    {'_id': ObjectId('5f3a3258de04be4c3f1ea80e'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:31:36'}
    {'_id': ObjectId('5f3a3266de04be4c3f1ea810'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 16:31:50'}
    {'_id': ObjectId('5f3a3267de04be4c3f1ea812'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:31:51'}
    {'_id': ObjectId('5f3a326ade04be4c3f1ea814'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:31:54'}
    {'_id': ObjectId('5f3a32a260f3aa42ffa76598'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:32:50'}
    {'_id': ObjectId('5f3a32a360f3aa42ffa7659a'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 16:32:51'}
    {'_id': ObjectId('5f3a32a660f3aa42ffa7659c'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:32:54'}
    {'_id': ObjectId('5f3a32b660f3aa42ffa7659e'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:33:10'}
    {'_id': ObjectId('5f3a32c8f6fe4fb8a93d1573'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:33:28'}
    {'_id': ObjectId('5f3a32d3f6fe4fb8a93d1575'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:33:39'}
    {'_id': ObjectId('5f3a32d5f6fe4fb8a93d1577'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 16:33:41'}
    {'_id': ObjectId('5f3a3388b824ad43bd0a5ae6'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:36:40'}
    {'_id': ObjectId('5f3a338cb824ad43bd0a5ae8'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:36:44'}
    {'_id': ObjectId('5f3a3391b824ad43bd0a5aea'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:36:49'}
    {'_id': ObjectId('5f3a3391b824ad43bd0a5aec'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:36:49'}
    {'_id': ObjectId('5f3a339ab824ad43bd0a5aee'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 16:36:58'}
    {'_id': ObjectId('5f3a3f197945cba084d7078d'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:26:01'}
    {'_id': ObjectId('5f3a3f197945cba084d7078f'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 17:26:01'}
    {'_id': ObjectId('5f3a3f1e7945cba084d70791'), 'session_ip': '127.0.0.1', 'user_email': 'kkk@kkk.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:26:06'}
    {'_id': ObjectId('5f3a3f47554010887967b925'), 'session_ip': '127.0.0.1', 'user_email': 'kkk@kkk.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:26:47'}
    {'_id': ObjectId('5f3a3f65b730ad4daa643ece'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:27:17'}
    {'_id': ObjectId('5f3a3f66b730ad4daa643ed0'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 17:27:18'}
    {'_id': ObjectId('5f3a3f6fb730ad4daa643ed2'), 'session_ip': '127.0.0.1', 'user_email': 'korea@korea.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:27:27'}
    {'_id': ObjectId('5f3a3f8a77b01dbfa041099a'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:27:54'}
    {'_id': ObjectId('5f3a3f8c77b01dbfa041099c'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 17:27:56'}
    {'_id': ObjectId('5f3a3f9277b01dbfa041099e'), 'session_ip': '127.0.0.1', 'user_email': 'eee@eee.com', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:28:02'}
    {'_id': ObjectId('5f3a3f9477b01dbfa04109a0'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 17:28:04'}
    {'_id': ObjectId('5f3a48d1f06f511c40484472'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 18:07:29'}
    {'_id': ObjectId('5f3a48d3f06f511c40484474'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '17/08/2020 18:07:31'}
    {'_id': ObjectId('5f3a48d5f06f511c40484476'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '17/08/2020 18:07:33'}
    {'_id': ObjectId('5f3b3ed84b108b3db28fb55e'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:37:12'}
    {'_id': ObjectId('5f3b3f273445b86ba754e8a5'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:38:31'}
    {'_id': ObjectId('5f3b3f2b3445b86ba754e8a7'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '18/08/2020 11:38:35'}
    {'_id': ObjectId('5f3b3f2c3445b86ba754e8a9'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:38:36'}
    {'_id': ObjectId('5f3b3f2e3445b86ba754e8ab'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '18/08/2020 11:38:38'}
    {'_id': ObjectId('5f3b3f363445b86ba754e8ad'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:38:46'}
    {'_id': ObjectId('5f3b3fd75ce16e9db0abbfb2'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:41:27'}
    {'_id': ObjectId('5f3b3fd95ce16e9db0abbfb4'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '18/08/2020 11:41:29'}
    {'_id': ObjectId('5f3b414e1288cd63c98cf1f8'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:47:42'}
    {'_id': ObjectId('5f3b4214693bdf55ebdc4f5c'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_B.html', 'access_time': '18/08/2020 11:51:00'}
    {'_id': ObjectId('5f3b4318a987a7fc03d150d3'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:55:20'}
    {'_id': ObjectId('5f3b431fa987a7fc03d150d5'), 'session_ip': '127.0.0.1', 'user_email': 'ggg@kkk.com', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:55:27'}
    {'_id': ObjectId('5f3b4323a987a7fc03d150d7'), 'session_ip': '127.0.0.1', 'user_email': 'ggg@kkk.com', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:55:31'}
    {'_id': ObjectId('5f3b4328a987a7fc03d150d9'), 'session_ip': '127.0.0.1', 'user_email': 'ggg@kkk.com', 'page': 'blog_A.html', 'access_time': '18/08/2020 11:55:36'}
    {'_id': ObjectId('5f3b4740775f63b2838feb0c'), 'session_ip': '127.0.0.1', 'user_email': 'anonymous', 'page': 'blog_A.html', 'access_time': '18/08/2020 12:13:04'}
    {'_id': ObjectId('5f3b4748775f63b2838feb0e'), 'session_ip': '127.0.0.1', 'user_email': 'dave@gmail.com', 'page': 'blog_A.html', 'access_time': '18/08/2020 12:13:12'}
    

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 10_flask_login
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## flask_login 라이브러리

## 1. flask_login 란?

- 사용자를 체크하는 기능을 담당하는 라이브러리
- 예:
  - 사용자가 로그인시, flask_login 라이브러리를 사용하면, 사용자 관련 session 정보를 HTTP response 에 넣어서 보내주고,
  - 이를 기반으로 flask 서버에서 사용자를 구별할 수 있는 기능을 제공

### flask_login 주요 동작 방식

1. 사용자가 로그인하면, 로그인 정보를 User class 에서 객체로 가져오고, LoginManager() 에 추가하여 세션 생성
   - flask 서버가 리턴시에 해당 세션 정보를 웹페이지에 송부
2. current_user 객체에 해당 객체가 저장됨
   - 주요 attribute
     - current_user.id : 사용자 ID (unicode 로 된 값, python string 이라고 봐도 됨)
       - python3 는 기본적으로 unicode 를 사용
     - current_user.is_authenticated : 사용자가 로그인되었는지를 나타내는 값 (True or False)
     - 이외의 attribute 는 User class 를 정의하면서, 필요에 따라 추가하면 됨
3. 로그인 후 웹페이지로 flask 서버 접근시, 전달받은 세션 정보를 기반으로 접근
   - 세션 정보에서 id를 추출해서, LoginManager() 에서 다루는 id 일 경우, @login_required 로 데코레이터가 추가된 API 접근 허용
4. 사용자가 로그아웃시 LoginManager() 에서 해당 id 제거

### 문제는 User class 구현 예가 많지 않음
- 즉, 각자의 아키텍쳐 기반 하에 생성 필요
- User class 에는 flask_login 라이브러리의 UserMixin 클래스를 상속받아서 구현하는 것만 가이드

### flask_login User class 가 지원해야할 변수/함수들
- is_authenticated: This property should return True if the user is authenticated
- is_active: This property should return True if this is an active user (계정 중지된 사용자 확인)
- is_anonymous: This property should return True if this is an anonymous user
- get_id(): This method must return a unicode that uniquely identifies this user, and can be used to load the user from the user_loader callback

> UserMixin 클래스 상속시 관련 기본 변수/함수가 상속되고, 필요시에만 override 하면 됨

## 2. flask_login 코드 구현

### flask_login 초기 설정 코드
- 세션 generation 을 위해, flask 에서 secret key 를 정의해줘야 함
```python
app.secret_key = os.urandom(24)
```

- flask_login 라이브러리에서 세션 관리
  - 다음 코드에서 "strong" 옵션을 사용할 시 Session 보안 적용
```python
login_manager = LoginManager()
login_manager.init_app(app)
login_manager.session_protection = "strong"
```

### 사용자 session 생성
- User 클래스를 기반으로 사용자 객체를 생성한 후, flask_login.login_user() 함수에 해당 객체를 넣어주면,
- 해당 사용자 기반 session 이 생성됨
- 해당 session 은 HTTP response 에 넣어져서 사용자 웹브라우저에 송부됨
  - HTTP Response 에 Set-Cookie 옵션에 해당 session 정보를 넣어서 송부하면,
  - 사용자 웹브라우저에서는 추후 해당 서버 주소로 HTTP request 송부시 해당 session 정보를 자동으로 넣어서 요청함
  - flask_login 은 HTTP request 에서 자동으로 session 정보를 가져와서, 사용자를 구분함
- session 생성시, 사용자 HTTP request 에 들어 있는 사용자 IP address 와 user agent 등을 함께 참조해서 session 을 생성하므로,
  - 다른 사용자가 session 탈취하더라도, 사용자 IP address 와 user agent 까지 동일하게 HTTP request 에 넣어서 요청해야 하고,
  - 이 경우 이에 대한 응답은 다른 컴퓨터의 사용자가 아닌, 해당 사용자 IP 로 전송되므로, session 보안에 유용함
  
```python
from flask_login import login_user

user = User.create(user_email, blog_id)
login_user(user)
```

### login_manager 관련 사전 선언 필요 함수

> 다음 두 함수는 사전 선언 필요

#### 로그인 후 최초 current_user 호출시 다음 코드 호출

- 사용자 정보를 flask_login 과 함께 사용되는 User class 를 통해 가져옴

```python
@login_manager.user_loader
def load_user(user_id):
    return User.get(user_id)
```

#### @login_required 데코레이터로 로그인 후 접근 가능한 페이지 protection 가능
> 로그인이 안된 채로 해당 페이지 접근시 @login_manager.unauthorized_handler 에 정의된 함수를 호출하므로, 필요시 구현 원하는 형태로 구현 가능 <br>
  
```python
@login_manager.unauthorized_handler
def unauthorized():
    return make_response(jsonify(success=False), 401)
```

### User class 구현
- User class 는 UserMixin class 를 상속해야 함
- 속성으로 사용자를 구분할 수 있는 id 를 반드시 가지고 있어야 함
- 이외 코드에 대해서는 구현을 통해 설명

```python
class User(UserMixin):

    def __init__(self, user_id, user_email, blog_id):
        self.id = user_id
        self.user_email = user_email
        self.blog_id = blog_id

    def get_id(self):
        return str(self.id)

    @staticmethod
    def get(user_id):
        mysql_db = conn_mysqldb()
        db_cursor = mysql_db.cursor()
        sql = "SELECT * FROM user_info WHERE USER_ID = '" + \
            str(user_id) + "'"
        db_cursor.execute(sql)
        user = db_cursor.fetchone()
        if not user:
            db_cursor.close()
            return None

        print(user)
        user = User(user_id=user[0], user_email=user[1], blog_id=user[2])
        db_cursor.close()
        return user

    @staticmethod
    def find(user_email):
        mysql_db = conn_mysqldb()
        db_cursor = mysql_db.cursor()
        sql = "SELECT * FROM user_info WHERE USER_EMAIL = '" + \
            str(user_email) + "'"
        db_cursor.execute(sql)
        user = db_cursor.fetchone()
        if not user:
            db_cursor.close()
            return None

        print(user)
        user = User(user_id=user[0], user_email=user[1], blog_id=user[2])
        db_cursor.close()
        return user

    @staticmethod
    def create(user_email, blog_id):
        user = User.find(user_email)
        if user == None:
            mysql_db = conn_mysqldb()
            db_cursor = mysql_db.cursor()
            sql = "INSERT INTO user_info (USER_EMAIL, BLOG_ID) VALUES ('%s', '%s')" % (
                str(user_email), str(blog_id))
            db_cursor.execute(sql)
            mysql_db.commit()
            return User.find(user_email)
        else:
            return user
```

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 11_class_basic
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 1. 예제로 이해하는 객체지향 문법 (class와 object)

### 사각형 만들기

  <img src="https://www.fun-coding.org/00_Images/quadrangle.png" />

### 3.1. class 선언하기
### 객체 생성 전에 미리 class를 선언해야 함


```python
class Quadrangle:
    pass
```


```python
class SingleWord:
    pass
```


```python
dir (SingleWord)
```




    ['__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__']



* class 도 변수/함수와 마찬가지로 유일한 이름을 지어줘야 함
* class 에 attribute/method를 아직 안넣은 상태이므로, 클래스에 내용이 없기에 임의로 pass 를 넣어 클래스 선언이 끝났음을 알려줌
  - pass는 아무것도 수행하지 않는 문법, 임시 코드 작성시 주로 사용
* 클래스명은 PEP Coding Convention에 가이드된 대로 각 단어의 첫 문자를 대문자로 하는 CapWords 방식을 사용

### 만들어진 클래스로 객체를 만들 수 있음
* 객체도 변수/함수/클래스와 마찬가지로 유일한 이름을 지어줘야 함
* 함수와 마찬가지로 인수를 넣을 수 있음


```python
square = Quadrangle()
```


```python
dave = Quadrangle()
```


```python
dave1 = Quadrangle()
```


```python
dir(dave)
```




    ['__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__']




```python
# 객체 square는 Quadrangle의 인스턴스
type(square)
```




    __main__.Quadrangle




```python
type(dave)
```




    __main__.Quadrangle



### 3.2. attribute 넣어보기
* 만들고자 하는 속성 생각해보기
  - width, height, color


```python
class Quadrangle:
    def __init__(self, width, height, color):
        self.width = width
        self.height = height
        self.color = color
```


```python
dir(Quadrangle)
```




    ['__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__']




```python
square1 = Quadrangle(12, 12, 'red')
square2 = Quadrangle(10, 10, 'blue')
```


```python
dir(square1)
```




    ['__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__',
     'color',
     'height',
     'width']



### 객체의 attribute 접근하기
* 객체명.attribute명


```python
square1.color
```




    'red'




```python
square2.color = 'red'
```


```python
square1.color
```




    'red'




```python
square2.color
```




    'red'




```python
square1.height = 5
```


```python
print (square1.height, square2.height)
```

    5 10
    

<div class="alert alert-block alert-success">
<strong><font color="blue" size="4em">초간단 연습</font></strong><br>
* width, height, color 속성을 가진 사각형 클래스를 만들고 다음 2개의 객체 만들기 (객체 속성을 바꿔주시고, 출력도 해보세요)<br>
  - 직사각형 1개 객체 속성: width=10, height=5, color='red'<br>
  - 정사각형 1개 객체 속성: width=7, height=7, color='blue'<br>
</div>


```python
class Dave:
    def __init__(self, width, height, color):    
        self.width = width
        self.height = height
        self.color = color
        
square1 = Dave(10, 5, 'red')
square2 = Dave(7, 7, 'blue')

print (square1.width, square1.height, square1.color)
print (square2.width, square2.height, square2.color)
```

    10 5 red
    7 7 blue
    

### 3.3 method 넣어보기
#### 만들고자 하는 method 생각해보기1
  - 사각형 넓이 구하기    


```python
class Quadrangle:
    def __init__(self, width, height, color):    
        self.width = width
        self.height = height
        self.color = color

    def get_area(self):
        return self.width * self.height
```

#### 이 부분을 이해해야 함
* 파이썬 method는 항상 첫 번째 파라미터로 self 사용
  * 인자가 필요없을 때에도 self는 사용
* 클래스의 attribute는 내부에서 접근시, **self.attribute명 으로 접근**

#### 만들고자 하는 method 생각해보기2
  - 사각형 width, height 설정하기   


```python
class Quadrangle:
    def __init__(self, width, height, color):    
        self.width = width
        self.height = height
        self.color = color

    def get_area(self):
        return self.width * self.height
    
    def set_area(self, data1, data2):
        self.width = data1 
        self.height = data2
```

### 객체의 method 접근하기
* 객체명.method명


```python
square = Quadrangle(2, 3, 'blue')
square.set_area(5, 5)
```


```python
square.width
```




    5



#### method 호출시, 첫 번째 인자로 객체 자신이 넣어지기 때문에, self 를 method 첫 번째 인자로 항상 넣어야 함

  <img src="https://www.fun-coding.org/00_Images/self.png" />


```python
square.get_area()
```




    25



<div class="alert alert-block alert-success">
<strong><font color="blue" size="4em">초간단 연습</font></strong><br>
* 위에서 작성한 Quadrangle 클래스를 기반으로 직사각형 1개 객체와 정사각형 1개 객체를 만들고, 각 사각형 너비 출력하기<br>
  - 직사각형2개 속성: width=10, height=5, color='red'<br>
  - 정사각형2개 속성: width=7, height=7, color='blue'<br>
</div>


```python
class Quadrangle:
    def __init__(self, width, height, color):    
        self.width = width
        self.height = height
        self.color = color

    def get_area(self):
        return self.width * self.height
    
    def set_area(self, data1, data2):
        self.width = data1 
        self.height = data2

square1 = Quadrangle(1, 2, 'blue')
square2 = Quadrangle(3, 4, 'red')

square1.set_area(10, 5)
square2.set_area(7, 7)
square1.color = 'red'
square1.color = 'blue'

print(square1.get_area())
print(square2.get_area())

```

    50
    49
    

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 12_inheritance
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 2. 예제로 이해하는 객체지향 문법 (상속)

### 1. Class Inheritance (상속)
  - **추상화(abstraction)**: 여러 클래스에 중복되는 속성, 메서드를 하나의 기본 클래스로 작성하는 작업
  - **상속(inheritance)**: 기본 클래스의 공통 기능을 물려받고, 다른 부분만 추가 또는 변경하는 것
    + 이 때 기본 클래스는 부모 클래스(또는 상위 클래스), Parent, Super, Base class 라고 부름
    + 기본 클래스 기능을 물려받는 클래스는 자식 클래스(또는 하위 클래스), Child, Sub, Derived class 라고 부름
  <br><br>
  - 코드 재사용이 가능, 공통 기능의 경우 기본 클래스 코드만 수정하면 된다는 장점
  - 부모 클래스가 둘 이상인 경우는 다중 상속 이라고 부름
 <img src="https://www.fun-coding.org/00_Images/oop3.png" />

### 예: 사각형, 삼각형, 원 클래스
* 공통점과 차이점 찾아보기
  + 사각형: **사각형 이름, 사각형 색**, 사각형 너비/높이, 사각형 넓이
  + 삼각형: **삼각형 이름, 삼각형 색**, 삼각형 한 변 길이, 삼각형 넓이
  + 원: **원 이름, 원 색**, 원 반지름, 원 넓이

* 부모 클래스를 자식 클래스에 인자로 넣으면 상속이 됨
<pre>
  - 다음 코드는 __init__(self, name, color) 메서드가 상속되고,
  - self.name과 self.color 도 __init__ 실행시 생성됨
</pre>


```python
class Figure:
    def __init__(self, name, color):
        self.name = name
        self.color = color
```


```python
class Quadrangle(Figure):
    def set_area(self, width, height):
        self.width = width 
        self.height = height

    def get_info(self):
        print (self.name, self.color, self.width * self.height)
```


```python
square = Quadrangle('dave', 'blue')
square.set_area(5, 5)
square.get_info()
```

    dave blue 25
    


```python
class Quadrangle:
    def __init__(self, name, color):
        self.name = name
        self.color = color
        
    def set_area(self, width, height):
        self.width = width 
        self.height = height

    def get_info(self):
        print (self.name, self.color, self.width * self.height)
```


```python
square = Quadrangle('dave', 'red')
square.set_area(5, 5)
square.get_info()
```

    dave red 25
    

### 보며 다시 한번 이해해보기
* https://goo.gl/AXau2u

* 상속 관계인 클래스 확인하기 
  - 내장함수 issubclass(자식 클래스, 부모 클래스) 사용하기


```python
class Figure:
    def __init__(self, name, color):
        self.name = name
        self.color = color

class Quadrangle(Figure):
    def set_area(self, width, height):
        self.width = width 
        self.height = height

    def get_info(self):
        print (self.name, self.color, self.width * self.height)
```


```python
# Quadrangle 클래스가 Figure 클래스의 자식 클래스인지 확인
issubclass(Quadrangle, Figure)
```




    True



* 클래스와 객체간의 관계 확인하기 
  - 내장함수 isinstance(객체, 클래스) 사용하기


```python
figure1 = Figure('figure1', 'black')
square = Quadrangle('square', 'red')
```


```python
print(isinstance(figure1, Figure))
print(isinstance(square, Figure))
print(isinstance(figure1, Quadrangle))
print(isinstance(square, Quadrangle))
```

    True
    True
    False
    True
    

### 또 다른 예: 사람과 학생


```python
# 클래스 선언
class Person:
    def __init__(self, name):
        self.name = name
        
class Student(Person):
    def study(self):
        print (self.name + " studies hard")

class Employee(Person):
    def work(self):
        print (self.name + " works hard")
```


```python
# 객체 생성
student1 = Student("Dave")
employee1 = Employee("David")
```


```python
# 객체 실행
student1.study()
employee1.work()
```

    Dave studies hard
    David works hard
    

### 2. Method Override (메서드 재정의)

* 부모 클래스의 method를 자식 클래스에서 재정의(override)
* 자식 클래스에서 **부모 클래스 method를 재정의**함
* 자식 클래스 객체에서는 재정의된 메소드가 호출됨
* 자식 클래스에서 **부모 클래스의 메서드와 이름만 동일하면 메서드 재정의가 가능함**
  - C++/Java언어 등에서는 메서드와 인자도 동일해야 함 


```python
# 클래스 선언
class Person:
    def __init__(self, name):
        self.name = name

    def work(self):
        print (self.name + " works hard")        

class Student(Person):
    def work(self):
        print (self.name + " studies hard")
```


```python
# 객체 생성
student1 = Student("Dave")
# 자식 클래스(Student)의 재정의된 work(self) 호출
student1.work()
```

    Dave studies hard
    

### Sub 클래스에 메서드를 더 추가할 수도 있죠!


```python
class Person:
    def work(self):
        print('work hard')

class Student(Person):
    def work(self):
        print('Study hard')
        
    def go_to_school(self):
        print('Go to school')
```


```python
p1 = Person()
s1 = Student()

p1.work()
#p1.go_to_school()

s1.work()
s1.go_to_school()
```

    work hard
    Study hard
    Go to school
    

<div class="alert alert-block alert-success">
<strong><font color="blue" size="4em">초간단 연습</font></strong><br>
* Car class 만들기<br>
- Car class<br>
  - attribute: 생성자에서 self.name 설정<br>
  - method: get_info(self) - 이름 출력<br>
<br>
- Eletronic Car class<br>
  - attribute: 생성자에서 self.name 설정<br>
  - method overide: get_info(self) - 이름과 사용 연료(Eletronic) 출력<br>
<br>
- Gasoline Car class<br>
  - attribute: 생성자에서 self.name 설정<br>
  - method overide: get_info(self) - 이름과 사용 연료(Gasoline) 출력
</div>


```python
class Car:
    def __init__(self, name):
        self.name = name
    
    def get_info(self):
        print (self.name)

class ElecCar(Car):
    def get_info(self):
        print (self.name, 'Fuel: Eletronic')

        
class GasoCar(Car):
    def get_info(self):
        print (self.name, 'Fuel: Gasoline')

elec = ElecCar('dave')
gaso = GasoCar('david')
elec.get_info()
gaso.get_info()
```

    dave Fuel: Eletronic
    david Fuel: Gasoline
    

### 3. 자식 클래스에서 부모 클래스 메서드 호출 (super 와 self)
### super()
 - 자식 클래스에서 부모 클래스의 method를 호출할 때 사용
   - super().부모 클래스의 method명


```python
# 클래스 선언
class Person:
    def work(self):
        print('work hard')

class Student(Person):
    def work(self):
        print('Study hard')
        
    def parttime(self):
        super().work()
```


```python
student1 = Student()
student1.work()
student1.parttime()
```

    Study hard
    work hard
    

### self
 - self는 현재의 객체를 나타냄
   - self.method명 또는 attribute명 으로 호출함
 - C++/C#, Java언어에서는 this 라는 키워드를 사용함


```python
# 클래스 선언
class Person:
    def work(self):
        print('work hard')

class Student(Person):
    def work(self):
        print('Study hard')
        
    def parttime(self):
        super().work()

    def general(self):
        self.work() 
```


```python
student1 = Student()
student1.work()
student1.parttime()
student1.general()
```

    Study hard
    work hard
    Study hard
    

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 13_class_method
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 3. 클래스 속성과 메서드

### 1. 클래스 변수와 인스턴스 변수 (attribute를 한 단계 더 구분해보자)
* 클래스 변수: 클래스 정의에서 메서드 밖에 존재하는 변수
  - 해당 클래스를 사용하는 모두에게 공용으로 사용되는 변수
  - 클래스 변수는 클래스 **내외부**에서 "클래스명.변수명" 으로 엑세스 가능
* 인스턴스 변수: 클래스 정의에서 메서드 안에서 사용되면서 "self.변수명"처럼 사용되는 변수
  - 각 객체별로 서로 다른 값을 가짐
  - 클래스 내부에서는 self.인스턴스변수명 을 사용하여 엑세스, 클래스 밖에서는 객체명.인스턴스변수명 으로 엑세스


```python
class Figure:
    count = 0  # 클래스 변수
 
    # 생성자(initializer)
    def __init__(self, width, height):
        # self.* : 인스턴스변수
        self.width = width
        self.height = height
        # 클래스 변수 접근 예
        Figure.count += 1
    
    def __del__(self):
        Figure.count -= 1
    
    # 메서드
    def calc_area(self):
        return self.width * self.height
```


```python
figure1 = Figure(2, 3)
Figure.count
figure2 = Figure(2, 3)
Figure.count
```




    2



<div class="alert alert-block alert-success">
<strong><font color="blue" size="4em">초간단 연습</font></strong><br>
* 다음 코드를 실행시키면서, 출력 값이 왜 이렇게 나왔는지 이해하기(클래스 변수와 인스턴스 변수 이해)
</div>


```python
print(Figure.count)
figure1 = Figure(2, 3)
print(Figure.count)
figure2 = Figure(4, 5)
print(Figure.count)
print(figure1.width)
print(figure2.width)
del figure1
print(Figure.count)
del figure2
print(Figure.count)
```

    0
    1
    2
    2
    4
    1
    0
    

### 2. instance method, static method, class method
### **instance method**: 해당 객체 안에서 호출 (지금까지 다룬 self.메서드명을 의미함)
 - 해당 메서드를 호출한 객체에만 영향을 미침
 - **객체 속성에 접근 가능**

### **static method**: 객체와 독립적이지만, 로직상 클래스내에 포함되는 메서드
 - self 파라미터를 갖고 있지 않음
 - **객체 속성에 접근 불가**
 - <strong><font color='#BF360C'>정적 메서드는 메서드 앞에 @staticmethod 라는 Decorator를 넣어야 함</font></strong>
 - 클래스명.정적메서드명 또는 객체명.정적메서드명 둘 다 호출 가능


```python
class Figure:
    # 생성자(initializer)
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    # 메서드
    def calc_area(self):
        Figure.is_square(2, 3)
        return self.width * self.height

    # 정적 메서드 (Figure 에 너비와 높이가 같은 도형은 정사각형임을 알려주는 기능)
    @staticmethod
    def is_square(rect_width, rect_height):
        if rect_width == rect_height:
            print("정사각형이 될 수 있는 너비/높이입니다.")
        else:
            print("정사각형이 될 수 없는 너비/높이입니다.")
```


```python
figure1 = Figure(2, 3)
figure1.is_square(5, 5)         # 객체명.정적메서드명으로 호출 가능
Figure.is_square(4, 5)          # 클래스명.정적메서드명으로 호출 가능
```

    정사각형이 될 수 있는 너비/높이입니다.
    정사각형이 될 수 없는 너비/높이입니다.
    

<div class="alert alert-block alert-info">
<strong><font color="blue" size="4em">한발짝 더 나가보기!(심화 문제)</font></strong><br>
아래 코드를 실행시키면서 특이 값과 에러를 확인하고, 출력 값이 왜 이렇게 나왔는지 이해하기(정적/인스턴스 메서드 이해)
</div>


```python
class Figure:
    count = 0  # 클래스 변수

    # 생성자(initializer)
    def __init__(self, width, height):
        # self.* : 인스턴스변수
        self.width = width
        self.height = height
        # 클래스 변수 접근 예
        Figure.count += 1
        
    # 정적 메서드 (정적 메서드에서는 클래스 attribute 는 접근 가능)
    @staticmethod
    def print_count():
        print(Figure.count)

    # 정적 메서드 (에러: 정적 메서드에서는 객체 attribute 는 접근 불가)
    @staticmethod
    def print_width():
        print(self.width)
```


```python
figure1 = Figure(1, 2)
print(Figure.count)
print(figure1.print_count())
print(figure1.print_width())
```

    1
    1
    None
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-49-21f7c2ae98bb> in <module>
          2 print(Figure.count)
          3 print(figure1.print_count())
    ----> 4 print(figure1.print_width())
    

    <ipython-input-48-455732a5813d> in print_width()
         18     @staticmethod
         19     def print_width():
    ---> 20         print(self.width)
    

    NameError: name 'self' is not defined


### **class method**: 해당 class 안에서 호출 (해당 클래스로 만들어진 객체에서 호출되지 않고, 직접 클래스 자체에서 호출)
 - self 파라미터 대신, cls 파라미터를 가짐
 - **클래스 변수 접근 가능하며 cls.클래스변수명 으로 엑세스 가능** 단, 객체 속성/메서드는 접근 불가
 - <strong><font color='#BF360C'>클래스 메서드는 메서드 앞에 @classmethod 라는 Decorator를 넣어야 함</font></strong>
 - 클래스명.클래스메서드명 또는 객체명.클래스메서드명 둘 다 호출 가능


```python
class Figure1:
    count = 0  # 클래스 변수
 
    # 생성자(initializer)
    def __init__(self, width, height):
        # self.* : 인스턴스변수
        self.width = width
        self.height = height
        # 클래스 변수 접근 예
        Figure1.count += 1
    
    # 메서드
    def calc_area(self):
        return self.width * self.height

    # 클래스 메서드
    @classmethod
    def print_count(cls):
        return cls.count

figure1 = Figure1(2, 3)
figure2 = Figure1(4, 5)
print(Figure1.count)
print(Figure1.print_count()) # 2
print(figure1.print_count()) # 2
```

    2
    2
    2
    

### static method 와 class method 차이


```python
class Figure:
    @classmethod
    def set_name(cls, name):
        cls.name = name

class Circle(Figure):
   pass
 
Figure.set_name("figure")
print (Figure.name, Circle.name)

Circle.set_name("circle")
print (Figure.name, Circle.name)
```

    figure figure
    figure circle
    


```python
class Figure:
    @staticmethod
    def set_name(name):
        Figure.name = name

class Circle(Figure):
   pass
 
Figure.set_name("figure")
print (Figure.name, Circle.name)

Circle.set_name("circle")
print (Figure.name, Circle.name)
```

    figure figure
    circle circle
    

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 14_control_class
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

### MVC 패턴중 Control 기능 구현을 위해 클래스를 사용
- 클래스명.함수 형태로 코드 작성이 가능하여, 코드만 보더라도 어떤 코드인지 알 수 있고, 함수별 구분이 가능함
- 클래스내에 유사한 기능을 넣어서 기능별로 구현 및 유지보수가 유리함

### 사용자(email) 클래스

### mysql schema
```sql
CREATE TABLE user_info (
    USER_ID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    USER_EMAIL VARCHAR(100) NOT NULL,
    BLOG_ID CHAR(4),
    PRIMARY KEY(USER_ID)
);
```

```python
class User(UserMixin):

    def __init__(self, user_id, user_email, blog_id):
        self.id = user_id
        self.user_email = user_email
        self.blog_id = blog_id

    def get_id(self):
        return str(self.id)

    @staticmethod
    def get(user_id):
        mysql_db = conn_mysqldb()
        db_cursor = mysql_db.cursor()
        sql = "SELECT * FROM user_info WHERE USER_ID = '" + \
            str(user_id) + "'"
        db_cursor.execute(sql)
        user = db_cursor.fetchone()
        if not user:
            db_cursor.close()
            return None

        print(user)
        user = User(user_id=user[0], user_email=user[1], blog_id=user[2])
        db_cursor.close()
        return user

    @staticmethod
    def find(user_email):
        mysql_db = conn_mysqldb()
        db_cursor = mysql_db.cursor()
        sql = "SELECT * FROM user_info WHERE USER_EMAIL = '" + \
            str(user_email) + "'"
        db_cursor.execute(sql)
        user = db_cursor.fetchone()
        if not user:
            db_cursor.close()
            return None

        print(user)
        user = User(user_id=user[0], user_email=user[1], blog_id=user[2])
        db_cursor.close()
        return user

    @staticmethod
    def create(user_email, blog_id):
        user = User.find(user_email)
        if user == None:
            mysql_db = conn_mysqldb()
            db_cursor = mysql_db.cursor()
            sql = "INSERT INTO user_info (USER_EMAIL, BLOG_ID) VALUES ('%s', '%s')" % (
                str(user_email), str(blog_id))
            db_cursor.execute(sql)
            mysql_db.commit()
            return User.find(user_email)
        else:
            return user

```

### blog 세션 관리 클래스

```python
class BlogSession():
    blog_page = {'A': 'blog_A.html', 'B': 'blog_B.html'}
    session_count = 0

    @staticmethod
    def save_session_info(session_ip, user_email, webpage_name):
        now = datetime.now()
        now_time = now.strftime("%d/%m/%Y %H:%M:%S")

        mongo_db = conn_mongodb()
        mongo_db.insert_one({'session_ip': session_ip,
                             'user_email': user_email,
                             'page': webpage_name,
                             'access_time': now_time})

    @staticmethod
    def get_blog_page(force=None):
        print(force)
        if force == None:
            if BlogSession.session_count == 0:
                BlogSession.session_count = 1
                return 'blog_A.html'
            else:
                BlogSession.session_count = 0
                return 'blog_B.html'
        else:
            return BlogSession.blog_page[force]
```

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



# 15_deployment
<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>

## 배포 (deployment)
- 클라우드 서비스(AWS)를 사용하여, 리눅스 기반 서버에 docker 기반 배포가 가장 일반적인 형태임
- 이를 위해서는 클라우드 서비스(AWS) 사용법, 리눅스 사용법, docker 사용법을 익혀야 함
  - 이외에 클라우드 서비스(AWS) 기능과 파이썬을 사용하여, 자동 배포 기능을 구현

### 초간단 웹서비스 배포
- ngrok 를 통해, 자신의 PC 에서 동작하는 웹서버를 외부에서도 접속할 수 있도록 할 수 있음

- 맥 환경
  - Homebrew 설치 필요
    - https://brew.sh/index_ko
```bash
brew cask install ngrok
ngrok http 8080
```
  - ngrok --help 를 통해, 다양한 명령을 알 수 있음
  
- 윈도우 환경
  - https://ngrok.com/ 접속 후, 회원가입
  - 윈도우용 ngrok 다운로드 및 적절한 위치에 압축 풀기
  - cmd 명령으로 터미널을 오픈하고, 해당 위치로 이동 후

```
ngrok.exe http 8080
```
  > 윈도우의 경우 다양한 방화벽 프로그램이 설치되어 있을 가능성이 높으므로
  > 8080 포트 (인바운드, 즉 외부에서 8080 포트에 접속하는 케이스)를 막아놓았는지를 확인해야 함

<div class="alert alert-block" style="border: 1px solid #FFB300;background-color:#F9FBE7;">
<font size="3em" style="font-weight:bold;color:#3f8dbf;">AWS에서 실제 배포 기술로 배포하기</font><br>
AWS에서 실제 배포하는 기술은 리눅스, AWS 등에 매우 익숙해야 하며, <b>각 환경에 따라 문제 발생시에도 각 문제 사항을 스스로 해결할 수 있는 기술력을 갖춘 상태에서만 배포가 가능</b>합니다. 바로 진행하기에는 별도 강의로 만들 정도로 많은 내용이 필요한 사항이며, 따라서, 관련 기술에 아직 익숙하지 않다면, 참고로만 봐주시는 것이 좋습니다.
</div>

### 참고: AWS 무료 서비스(Free Tier) 가입과 서버(EC2) 만들기
  - 실습: http://blog.saltfactory.net/create-instance-on-aws/
  - https://aws.amazon.com/ -> My Account -> AWS Management Console -> Region (Seoul)
  - EC2 -> Launch Instance -> Ubuntu Server 16.04 ->t2.micro -> pem파일 다운로드 (로컬PC에 ~/.ssh/에 저장)
    - https://medium.com/flearning-edu/aws-ec2-%EC%9D%B8%EC%8A%A4%ED%84%B4%EC%8A%A4-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0-ed5d28cd875a
    
  - Elastic IP
    - Go Elastic IP -> Allocate New Address
    - Action -> Associate Address -> Select Instance
      Private IP: Private IP Address는 설정된 그대로! 172.x.x.x 로 설정된 클라우드 내부 IP를 52.x.x.x 공개 IP로 연결하겠다는 것
      
  - 요금불안: http://gun0912.tistory.com/45 , https://aws.amazon.com/ko/free/

### EC2에 접속하는 방법

* 서버 접속 방법
    + **osx**
      - chmod 400 [pem_file]
      - ssh -i path/[pemfile] ubuntu@[aws_server_public_ip]
      
    + **windows** 
      - 윈도우즈에서 접속하기 링크(http://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/putty.html)
      - putty(ssh client), puttygen download (https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
<br><br>
* 서버 터미널 접속 방법
    + **osx**
      - chmod 400 [pem_file]
      - ssh -i path/[pemfile] ubuntu@[aws_server_public_ip]
      
    + **windows** 
      - 윈도우즈에서 접속하기 링크(https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html)
      - putty(ssh client), puttygen download (http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
<br><br>
* 서버 FTP 접속 방법
    + FileZilla FTP 프로그램 사용
      - 윈도우: http://hyeonstorage.tistory.com/272
      - 맥: http://devgyugyu.tistory.com/8

### EC2 서버에 apache 웹서버 설치

- sudo apt-get update -y
- sudo apt-get install apache2
- sudo a2enmod rewrite
- sudo service apache2 restart
  - 현재 아파치 실행 상태 확인 명령: sudo service apache2 status

### FTP 접속 및 웹페이지 업로드
- Fizilla 접속 설정 참고: https://babamba-playground.tistory.com/27
- FTP 접속 - web 디렉토리 만들기 - upload
- SSH 접속 후
  - cd web
  - sudo cp -rf * /var/www/html/

### EC2 서버에 anaconda 설치
- anaconda 다운로드: https://www.anaconda.com/products/individual
- FTP 연결 및 해당 파일 업로드
- 다음 명령으로 설치 (파일명은 다운로드 시점마다 다를 수 있음)
  - 라이센스 동의 (yes), 설치 위치 (Enter) 
```
sudo bash Anaconda3-2020.07-Linux-x86_64.sh
```

- anaconda 는 다음 디렉토리에 설치
  - /home/ubuntu/anaconda3

- 참고: https://docs.anaconda.com/anaconda/install/linux/

### 참고: Ubuntu + flask

```bash
sudo apt-get install apache2-dev
```

1. mod_wsgi 소스 다운로드
   - 글로벌 python으로 동작시키기 위해, 현 환경에 맞게 mod_wsgi 모듈을 생성해야 함
   - https://github.com/GrahamDumpleton/mod_wsgi/releases

2. 소스 풀기
```
    tar -xvzf mod_wsgi-4.7.1.tar.gz -C .
```

3. mod_wsgi 빌드
```
    cd mod_wsgi-4.7.1
    ./configure
    make
    sudo make install
```

4. mod_wsgi.so 위치 확인 (make install 시 마지막 라인에서 확인 가능)
```
    sudo chmod 755 /usr/lib/apache2/modules/mod_wsgi.so
```

5. mod_wsgi 설치
 - 우선 sudo 명령에서도 /home/ubuntu/anaconda3/bin 디렉토리의 명령을 실행할 수 있도록, sudo 명령에서만 쓰는 secure path 에 해당 디렉토리를 추가해줘야 함 (매우 매우 복잡)
   - nano 에디터로 다음 명령이 실행되므로, nano 에디터 사용법은 다음 부분 참고
     - secure_path 마지막에 :/home/ubuntu/anaconda3/bin 추가
```
sudo visudo
```


6. 다음 실행 결과 복사 후, 000-default.conf 에 붙임
   - 다음 명령으로 우선 mod_wsgi-express 설치
```
sudo pip install mod_wsgi
```

   - 다음 실행 결과 복사 후, 000-default.conf 에 붙임
```
mod_wsgi-express module-config
```

7. apache2 설정 

```
sudo vi /etc/apache2/sites-available/000-default.conf
```

   - 다음과 같이 mod_wsgi-express 실행 결과를 최상단에 붙여넣기

```
LoadModule wsgi_module "/home/ubuntu/anaconda3/lib/python3.8/site-packages/mod_wsgi/server/mod_wsgi-py38.cpython-38-x86_64-linux-gnu.so"
WSGIPythonHome "/home/ubuntu/anaconda3"

<VirtualHost *:80>
```

#### flask 파일 생성

```
mkdir /home/ubuntu/web/backend
```

- create runserver.py in backend directory

```
rom flask import Flask

@app.route("/")
def hello():
    return "Hello, I love Flask!"
if __name__ == "__main__":
    app.run(host= '0.0.0.0', port="8081")
```

- create runserver.wsgi in backend directory

```
import sys, os
sys.path.insert(0, "/home/ubuntu/web/backend")

from runserver import app as application
```

### apache2 설정

1. 8081 포트 추가 
   - <b>AWS EC2 설정에서도 해당 포트 추가</b>
   - 아파치 설정에서도 다음과 같이 8081 포트 추가
   
```bash
    sudo vi /etc/apache2/ports.conf

    Listen 80
    Listen 8081 # 추가
```

2. 가상호스트 추가
   - fun-coding.org 를 자신의 서버 IP로 변경하면 됨
   
```bash
    sudo vi /etc/apache2/sites-available/000-default.conf

```

```bash
<VirtualHost *:8081>
        # The ServerName directive sets the request scheme, hostname and port that
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.
        #ServerName www.example.com

        ServerAdmin dream@fun-coding.org
        ServerName fun-coding.org
        ServerAlias www.fun-coding.org

        # Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        # error, crit, alert, emerg.
        # It is also possible to configure the loglevel for particular
        # modules, e.g.
        #LogLevel info ssl:warn

        ErrorLog /home/ubuntu/web/backend/error.log
        CustomLog /home/ubuntu/web/backend/access.log combined

        WSGIDaemonProcess runserver python-path=/home/ubuntu/anaconda3 user=ubuntu group=ubuntu threads=5
        WSGIProcessGroup runserver
        WSGIScriptAlias / "home/ubuntu/web/backend/runserver.wsgi"
        <Directory "/home/ubuntu/web/backend">
                Require all granted
        </Directory>
</VirtualHost>
```

- apache2 재실행
```
    sudo service apache2 restart
```

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>



