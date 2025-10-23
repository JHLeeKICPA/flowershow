---
collection:
  - 📼Lecture
---
## 0. 배경 지식과 큰 그림 이해하기

### 0.1 웹서비스 개발의 역사와 동향

- 웹서비스 개발은 시대의 변화와 기술 발전에 따라 진화했습니다.
- **1세대: 정적 웹 페이지** - HTML/CSS로 만들어진 파일을 서버에서 제공
- **2세대: 동적 웹 페이지** - CGI와 데이터베이스를 사용하여 사용자 요청에 따라 페이지 동적 생성.
- **3세대: MVC 프레임워크** - 모델(Model), 뷰(View), 컨트롤러(Controller)로 코드 구조화.
- **4세대: API 중심 서버** - 마이크로 서비스 아키텍처(MSA)를 통해 다양한 플랫폼 지원.

### 0.2 프레임워크의 정의

- 프레임워크: 미리 만들어진 코드/구조 집합으로, 개발 생산성 향상을 위해 반복적 기능 제공.
- 웹 개발 프레임워크 예: Python의 Django, Flask, JAVA의 Spring, Javascript의 Node.js.

### 0.3 마이크로 프레임워크의 특징

- 풀스택 프레임워크와 대비되는 개념으로, 필수 기능만 제공하여 서비스 경량화와 학습 곡선 감소.
- 장점: 빠른 개발, 선택적 기능 사용, 높은 확장성, 쉬운 문제 해결.
- Flask/FastAPI는 파이썬 라이브러리와 결합하여 파이썬 생태계의 강력한 기능 활용 가능.

## 1. FastAPI란?

### 개요

FastAPI는 Python을 위한 현대적인, 빠르고(높은 성능), 웹 프레임워크로, 주로 API 개발에 사용합니다. 이는 비동기 처리를 강조하며, Starlette(비동기 프레임워크)와 Pydantic(데이터 검증 및 설정 라이브러리)에 기반을 두고 있습니다.

### 주요 특징

1. **성능 중심**: 비동기 프로그래밍을 통한 높은 처리 속도. 데이터베이스 쿼리, 서버 간 통신 등 I/O 작업이 많은 애플리케이션에서 유리.
2. **RESTful API 개발 용이**: 보일러플레이트 코드 감소. 웹 서비스와 클라이언트 간 데이터 교환 최적화.
3. **Flask와의 비교**: Flask는 동기 처리 기반인 반면, FastAPI는 비동기 처리에 최적화되어 I/O 바운드 작업에서 더 효과적.

### FastAPI와 Flask의 비교

- **성능**: FastAPI가 Flask보다 빠르며, 비동기 처리에 최적화.
- **자동 문서화**: API 작성 시 자동으로 문서 생성, Flask는 별도 확장 기능 필요.
- **유효성 검사**: Pydantic을 통한 간편한 데이터 유효성 검사, Flask는 별도 라이브러리 필요.
- **비동기 프로그래밍**: FastAPI에서 간편하게 처리 가능, Flask는 동기 작업에 최적화.

### 설치 방법

Python 3.6 이상 필요.
```
!pip install fastapi
```

### Uvicorn 설치

FastAPI 애플리케이션을 실행하기 위해서는 Uvicorn이라는 ASGI 서버가 필요합니다. Uvicorn은 비동기 웹 서버로, FastAPI와 함께 사용하여 효율적인 성능을 발휘합니다. 설치는 다음 명령어로 간단히 할 수 있습니다.

```
pip install uvicorn
```

```
# pip install uvicorn 으로 uvicorn 가 정상 동작하지 않는다면, conda install uvicorn 으로 설치 재시도
```

#### 윈도우에서의 Uvicorn 설치 주의사항

윈도우에서 Uvicorn을 설치할 때 PATH에 대한 경고 메시지가 나타날 수 있습니다. 이는 uvicorn.exe 실행 파일이 PATH에 등록되지 않았음을 의미합니다. 경고가 나타날 경우, 해당 경로를 PATH에 등록해야 합니다. PATH 설정은 윈도우 환경에서 시스템 변수를 조정하는 방식으로 진행할 수 있으며, 이 과정은 별도의 챕터에서 자세히 설명되어 있습니다. 다만, PATH 설정에 익숙하지 않으시다면, 다음 명령으로 설치하는 것도 추천드림 (다음 명령으로 설치되는 폴더가 이미 아나콘다 설정 시 PATH로 설정되어 있기 때문임)

```
conda install uvicorn
```

- 직접 PATH를 설정하고자 하신다면: 윈도우에서 uvicorn 실행 파일 위치 확인 방법
   ``` bash
# 윈도우 터미널(프로그램 검색에서 cmd등으로 검색)에서 다음과 같이 실행
where uvicorn
    
# 출력
C:\Users\jhlee\AppData\Roaming\Python\Python311\Scripts\uvicorn.exe
    
#C:\Users\jhlee\AppData\Roaming\Python\Python311\Scripts\ 를 Path 환경 변수에 등록
    ```

### FastAPI 서버 실행 방법

VSCode를 설치하고 파이썬 실행 환경을 만든 후, FastAPI 개발용 폴더 구성 후, 해당 폴더에서 예제 코드를 main.py로 만드세요!

#### 간단한 예제: "Hello, World!" API

##### FastAPI 코드

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, World!"}
```

##### FastAPI 기본 문법 설명:

- `from fastapi import FastAPI` : FastAPI 클래스를 가져옴.
- `app = FastAPI()` : FastAPI 인스턴스 생성.
- `@app.get("/")` : HTTP GET 요청의 경로 지정.
- `def read_root():` : GET 요청 처리 함수.
- `return {"message": "Hello, World!"}` : JSON 형태의 응답 반환. FastAPI가 자동 변환.

#### FastAPI 애플리케이션 실행

FastAPI 코드를 `main.py`에 저장한 후, 아래 명령어를 사용해 애플리케이션을 실행합니다.

```bash
uvicorn main:app --reload
```

- `main`: FastAPI 애플리케이션 코드가 있는 파이썬 파일명 (`main.py`).
- `app`: FastAPI 인스턴스 객체명 (`app = FastAPI()`).
- `--reload`: 개발 중 코드 변경 시 자동으로 서버 재시작.

#### 서버 접속

명령어 실행 후, `http://127.0.0.1:8000` 주소를 통해 FastAPI 애플리케이션에 접속 가능.

#### FastAPI와 Uvicorn의 조합

FastAPI는 Uvicorn을 포함한 다양한 ASGI 프레임워크와 호환됩니다. 하지만 Uvicorn의 비동기 처리 기능을 최대한 활용할 때 FastAPI는 최적의 성능을 발휘합니다. 따라서 FastAPI와 Uvicorn의 조합이 가장 권장됩니다.

### 자동 문서화의 중요성 및 FastAPI의 자동 문서화 기능

#### 1. 자동 문서화의 중요성

- **문서화의 부재 문제**: 개발 과정에서 API 문서화는 시간이 많이 소요되고 지속적인 업데이트가 필요한 문제가 있음.
- **자동 문서화의 해결책**: FastAPI는 이러한 문제를 자동 문서화 기능을 통해 해결함.

#### 2. FastAPI의 자동 문서화 방식

- **타입 힌트와 데코레이터 활용**: 코드 내의 타입 힌트(Type Hint)와 데코레이터(decorator)를 사용하여 API 문서를 자동 생성.
- **라우터를 통한 문서 생성**: 예를 들어, `@app.get("/")` 라우터를 통해 해당 API 엔드포인트에 대한 문서 자동 생성.

#### 3. 자동 문서화 사용법

- **Swagger UI 접근**: `http://127.0.0.1:8000/docs` 주소를 통해 Swagger UI 접근 가능. API 엔드포인트의 상세 정보 확인 및 테스트 수행 가능.
- **ReDoc 접근**: `http://127.0.0.1:8000/redoc` 주소를 통해 ReDoc을 통한 다른 형태의 문서 확인 가능.

### FastAPI 자동 문서화의 실제 사용 예시 및 이해

#### 1. Swagger UI (Docs)의 기능 및 사용 방법

- **엔드포인트 목록**: 화면 좌측에 사용 가능한 모든 API 엔드포인트 나열.
- **테스트 버튼**: 'Try it out' 버튼을 클릭하여 API 직접 테스트.
- **매개변수 입력**: 필요한 매개변수 입력 구분.
- **실행 버튼**: 'Execute' 버튼으로 API 호출.
- **응답 표시**: API 호출 결과과 표시 부분.

#### 2. ReDoc의 기능 및 특징

- **사이드 메뉴**: API의 전체 구조 확인 가능.
- **엔드포인트 설명**: 상세한 설명과 요청/응답 예시 제공.
- **데이터 모델 설명**: 사용되는 데이터 모델의 구조와 설명 제공.
- **마크다운 문법 지원**.
- **단일 페이지 구조로 문서 전체 구조 쉽게 파악**.
- **대화형 API 테스트 미지원**.

#### 3. Swagger UI (Docs)와 ReDoc의 차이점

- **Swagger UI (Docs):**
    1. 대화형 API 테스트 가능.
    2. 매개변수 형태 및 예시 표시.
    3. OAuth2 인증 테스트 지원.
    4. UI 커스터마이징 가능.
- **ReDoc:**
    1. 깔끔하고 직관적인 UI 제공.

#### 4. 주요 자동 문서화 용어 이해

- **curl**: 터미널에서 사용하는 명령줄 도구, API 호출 방법 표시.
- **GET / Read Root**: 서버로부터 정보 조회를 위한 GET 요청의 문서화.
- **200**: HTTP 응답 코드, 요청이 성공적으로 완료됨을 의미.
- **application/json**: 데이터가 JSON 형식으로 반환됨을 나타내는 MIME 타입.
- **Response body**: 서버가 반환하는 실제 데이터 부분.
- **Response headers**: 서버 응답의 메타데이터를 포함하는 부분.

#### 5. 자동 문서화의 장점

- **시간 절약**: 수동 문서 업데이트 필요 없음.
- **최신 정보 유지**: 코드 업데이트 시 문서 자동 업데이트.
- **API 테스트 용이성**: 직접 API 호출하여 테스트 가능.
- **타입 검사와 유효성 검증**: 코드의 타입 힌트와 유효성 검사 규칙을 문서에 반영.

## 5.2 라우팅

FastAPI에서 라우팅은 클라이언트로부터의 HTTP 요청을 적절한 함수나 메소드로 연결하는 과정을 의미합니다.

### 1. 기본 라우팅: @app.get("/")

- 기본적으로 HTTP GET 메소드를 사용한 라우팅
- 예시: 루트 URL (`http://127.0.0.1:8000/`)에 GET 요청 시 "Hello, FastAPI" 응답 반환

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, FastAPI"}
```

### 2. 경로 매개변수(Path Parameters)와 쿼리 매개변수(Query Parameters)

- **경로 매개변수**: URL의 일부로 통합된 변수, 동적 값 처리에 사용
    - 예시: `/items/{item_id}` 에서 `{item_id}`는 경로 매개변수
```python
@app.get("/items/{item_id}")
def read_item(item_id):
	return {"item_id": item_id}
```

- **복수의 경로 매개변수 사용**
	- 예시: `/users/{user_id}/items/{item_name}` 에서 `user_id` 와 `item_name` 은 경로 매개변수    
```python
@app.get("/users/{user_id}/items/{item_name}")
def read_user_item(user_id, item_name):
	return {"user_id": user_id, "item_name": item_name}
```

- **쿼리 매개변수**: URL의 `?` 이후에 정의되는 키-값 쌍. 필터링이나 정렬 등에 사용
    - 예시: `/items/?skip=5&limit=5` 에서 `skip` 과 `limit` 은 쿼리 매개변수

### 테스트

아래 코드를 `main.py`에 작성하고 서버를 실행합니다.
```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, FastAPI"}

@app.get("/items/{item_id}")
def read_item(item_id: int):
    return {"item_id": item_id}

@app.get("/items/")
def read_items(skip: int = 0, limit: int = 10):
    return {"skip": skip, "limit": limit}

# uvicorn main:app --reload 로 실행
```

#### curl 명령어와 테스트

- **curl 사용**: 클라이언트 URL 도구로 서버와 상호작용에 사용
- 브라우저에서도 유사한 결과 확인 가능

#### 테스트: 루트 URL

루트 URL에 GET 요청을 보내서 테스트합니다.
```bash
curl http://127.0.0.1:8000/
```

**테스트 결과:
```json
{"message":"Hello, FastAPI"}
```

#### 경로 매개변수 테스트

`item_id`를 5로 지정하여 테스트해보겠습니다.
```bash
curl http://127.0.0.1:8000/items/5
```

**테스트 결과:**
```json
{"item_id":5}
```

#### 쿼리 매개변수 테스트

`skip`을 20, `limit`을 2로 설정하여 테스트합니다.
```bash
curl http://127.0.0.1:8000/items/?skip=20&limit=2
```

**테스트 결과:**
```json
{"skip":20,"limit":2}
```

다음과 같이 `skip`과 `limit`을 설정하지 않으면 기본값이 출력됩니다.
```bash
curl http://127.0.0.1:8000/items/
```

**테스트 결과:**
```json
{"skip":0,"limit":10}
```

네, 이어서 변환해 드리겠습니다.

## 5.3 타입 힌트

타입 힌트(Type Hint)는 변수나 함수의 예상되는 데이터 타입을 명시적으로 표시하는 프로그래밍 기술입니다. FastAPI는 이를 활용하여 요청의 유효성을 검증하고, 적절한 데이터 처리를 도와줍니다.

### 기본 타입 힌트 사용

- **목적**: 경로 나 쿼리 매개변수에 타입 지정하여 자동 검증
- **예시**:
    - 경로 매개변수 예시: `@app.get("/items/{item_id}")` 에서 `item_id: int`
    - 쿼리 매개변수 예시: `@app.get("/getdata/")` 에서 `data: str = "funcoding"`

```python
# main.py 파일
from fastapi import FastAPI

app = FastAPI()

@app.get("/items/{item_id}")
def read_item(item_id: int):
    return {"item_id": item_id}

@app.get("/getdata/")
def read_item(data: str = "funcoding"):
    return {"data": data}

# 실행: uvicorn main:app --reload
```

- **웹 브라우저 테스트:**
    1. `http://127.0.0.1:8000/items/123` → 출력: `{"item_id": 123}`
    2. `http://127.0.0.1:8000/items/fun` → 오류: `item_id`가 `int`가 아님
    3. `http://127.0.0.1:8000/getdata/?data=somequery` → 출력: `{"data": "somequery"}`
    4. `http://127.0.0.1:8000/getdata/` → 출력: `{"data": "funcoding"}`
    5. `http://127.0.0.1:8000/getdata/?data=1.1` → 출력: `{"data": "1.1"}` (문자열로 처리)

### 타입 힌트 사용 가능한 데이터 타입

FastAPI에서 사용할 수 있는 파이썬 타입 힌트에 대해 알아보겠습니다. 타입 힌트는 FastAPI가 데이터의 유효성을 검증하고, 적절한 형식으로 데이터를 변환하는 데 사용됩니다.

#### 기본 데이터 타입
- `int`: 정수
- `float`: 부동 소수점 수
- `str`: 문자열
- `bool`: 불리언 (True 또는 False)

#### 컬렉션 타입
- `List`: 예: `List[int]` (정수 리스트)
- `Tuple`: 예: `Tuple[str, int]` (문자열과 정수 튜플)
- `Dict`: 예: `Dict[str, float]` (문자열 키와 부동 소수점 값의 딕셔너리)
- `Set`: 예: `Set[bool]` (불리언 값의 세트)

#### 특수 타입
- `None`: 값 없음
- `Any`: 모든 타입 허용, 타입 검사 무시

#### typing 모듈의 고급 타입
- `Optional`: 예: `Optional[str]` (문자열 또는 None)
- `Union`: 예: `Union[int, str]` (정수 또는 문자열)

#### 예시: 복잡한 타입 힌트 조합
- `List[Dict[str, Union[int, str]]]` : 문자열 키와 정수 또는 문자열 값을 갖는 딕셔너리의 리스트

FastAPI는 이러한 다양한 타입 힌트를 활용하여 요청 데이터의 형식을 검증하고, 응답 데이터를 적절한 형식으로 변환합니다. 또한, 이를 통해 API 문서를 자동으로 생성할 수 있습니다.

### 고급 타입 힌트 사용

- **목적**: `typing` 모듈의 `List`, `Dict` 등을 사용하여 복잡한 데이터 구조 표현
- **예시**:
    - 리스트 자료형 처리 쿼리 매개변수: `List[int] = Query([])`
    - 딕셔너리 자료형 요청 본문: `Dict[str, int]`

```python
# main.py 파일
from fastapi import FastAPI, Query
from typing import List, Dict

app = FastAPI()

@app.get("/items/")
async def read_items(q: List[int] = Query([])):
    return {"q": q}

@app.post("/create-item/")
async def create_item(item: Dict[str, int]):
    return item

# 실행: uvicorn main:app --reload
```

### 웹 브라우저 및 HTTP 클라이언트 테스트

- **목적**: FastAPI에서 타입 힌트를 사용하여 데이터 유효성을 검증하는 방법 시연
- **예시 및 결과**:
    1. **List 타입 쿼리 매개변수 테스트**
        - `curl "http://127.0.0.1:8000/items/?q=1&q=2&q=3"` 실행
        - 웹 브라우저: `http://127.0.0.1:8000/items/?q=1&q=2&q=3` -> 결과: `{"q": [1, 2, 3]}`
    2. **타입 불일치 시 에러 테스트**
        - 웹 브라우저: `http://127.0.0.1:8000/items/?q=하나&q=둘&q=셋` -> 결과: 타입 에러 (정수가 아닌 문자열 입력)
    3. **HTTP POST 요청 테스트**
        - `curl -X POST "http://127.0.0.1:8000/create-item/" -H "accept: application/json" -H "Content-Type: application/json" -d "{\"name\":1}"`
        - 결과: 서버에서 `{"name": 1}` 형태로 요청 본문 받고 반환

이러한 테스트 방법은 FastAPI가 타입 힌트를 기반으로 유효성 검증을 어떻게 수행하는지 확인하는데 유용합니다. 타입 힌트의 정확한 사용은 API의 안정성을 크게 향상시킵니다.

## 5.4 HTTP 메소드

HTTP 메소드는 클라이언트가 서버에 특정 동작을 요청하는 방법을 정의합니다. FastAPI에서는 이를 통해 요청의 의도를 명확히 하고 적절한 엔드포인트로 라우팅합니다.

### HTTP 메소드 상세 설명

1. **GET**
    - **사용처**: 서버로부터 정보 요청
    - **특징**: 데이터 읽기 전용, 서버 상태 변경 없음
    - **예시**: 사용자 프로필, 게시글 목록 조회
2. **POST**
    - **사용처**: 서버에 데이터 전송, 새 리소스 생성
    - **특징**: 데이터 서버에 제출, 주로 요청 본문에 데이터 포함
    - **예시**: 새 사용자 등록, 게시글 작성
3. **PUT**
    - **사용처**: 지정된 리소스의 전체 업데이트
    - **특징**: 기존 리소스의 완전한 교체
    - **예시**: 사용자 프로필 전체 업데이트
4. **DELETE**
    - **사용처**: 지정된 리소스 삭제
    - **특징**: 리소스 제거 지시, 성공 시 접근 불가
    - **예시**: 계정 삭제, 게시글 제거

FastAPI는 다양한 HTTP 요청 처리를 위해 메소드별 라우팅 데코레이터(`@app.get()`, `@app.post()`, `@app.put()`, `@app.delete()` 등)를 제공합니다.

### FastAPI 코드 예시 (CRUD)

이 코드는 FastAPI로 간단한 CRUD(Create, Read, Update, Delete) 작업을 수행하는 예시입니다. `main.py` 파일에 저장 후 `uvicorn main:app --reload` 명령어로 실행할 수 있습니다.

```python
from fastapi import FastAPI

app = FastAPI()

# Create
@app.post("/items/")
def create_item(item: dict):
    return {"item": item}

# Read (List)
@app.get("/items/")
def read_items(skip: int = 0, limit: int = 10):
    return {"skip": skip, "limit": limit}

# Read (Single)
@app.get("/items/{item_id}")
def read_item(item_id: int):
    return {"item_id": item_id}

# Update
@app.put("/items/{item_id}")
def update_item(item_id: int, item: dict):
    return {"item_id": item_id, "updated_item": item}

# Delete
@app.delete("/items/{item_id}")
def delete_item(item_id: int):
    return {"message": f"Item {item_id} has been deleted"}
```

### 주요 HTTP 응답 코드1

#### 2xx (성공)

- **200 OK**: 요청이 성공적으로 처리되었음을 의미합니다. 가장 일반적인 성공 응답 코드입니다.3
- **201 Created**: 요청이 성공적으로 이루어져 새로운 리소스가 생성되었습니다. 예를 들어, POST 요청을 통해 새로운 엔트리가 데이터베이스에 추가되었을 때 사용됩니다.4
- **204 No Content**: 요청은 성공적이지만, 클라이언트에게 보내줄 콘텐츠는 없습니다. 예를 들어, DELETE 요청이 성공적으로 처리되었을 때 사용될 수 있습니다.5

#### 3xx (리다이렉션)

- **301 Moved Permanently**: 요청한 리소스가 영구적으로 새 위치로 이동했습니다. 이 코드는 리소스의 URL이 변경되었을 때 사용됩니다.7
- **302 Found**: 요청한 리소스가 일시적으로 다른 위치에 있음을 나타냅니다. 리다이렉션을 위해 자주 사용됩니다.8

#### 4xx (클라이언트 오류)

- **400 Bad Request**: 서버가 요청을 이해할 수 없음. 잘못된 요청 구조나 파라미터 때문에 발생할 수 있습니다.10
- **401 Unauthorized**: 요청이 인증을 필요로 함. 보통 로그인하지 않은 사용자가 보호된 리소스에 접근하려 할 때 반환됩니다.11
- **403 12Forbidden**: 서버가 요청을 이해했으나, 권한이 없어 요청을 거부합니다.
- **404 Not Found**: 서버가 요청한 리소스를 찾을 수 없습니다. URL 오류나 존재하지 않는 페이지에 대한 요청에서 흔히 발생합니다.
- **405 Method Not Allowed**: 요청한 리소스에서는 지원하지 않는 HTTP 메소드를 사용했습니다.
- **422 Unprocessable Entity**: 요청은 이해했으나, 요청된 작업을 수행할 수 없음. 주로 요청 형식이 올바르지만, 내용이 유효하지 않을 때 사용됩니다(예: 데이터 유효성 검증 실패).

#### 5xx (서버 오류)

- **500 Internal Server Error**: 서버 내부 오류로 인해 요청을 처리할 수 없습니다. 가장 일반적인 서버 오류 응답입니다.
- **503 Service Unavailable**: 서버가 일시적으로 요청을 처리할 수 없습니다. 일반적으로 서버 과부하나 유지 관리로 인해 발생합니다.

### curl을 사용한 FastAPI 테스트

FastAPI에서 HTTP 메소드를 테스트하는 방법 중 하나는 `curl` 명령어를 사용하는 것입니다. 이를 통해 POST, PUT, DELETE 메소드를 시험해볼 수 있습니다.

#### 1. POST 메소드 테스트

- **목적**: 새로운 아이템 생성
- **특징**: 요청 본문에 JSON 데이터 전송
- **Pydantic 모델**: 사용 권장, 하지만 여기서는 직접 `dict` 타입 사용
- **curl 명령어**:
```bash
curl -X POST "http://127.0.0.1:8000/items/" -H "Content-Type: application/json" -d "{\"name\":\"item1\", \"value\":42}"
```
- **결과**:
```json
{"item":{"name":"item1","value":42}}
```


#### 2. PUT 메소드 테스트

- **목적**: 특정 아이템 정보 업데이트
- **사용**: 아이템 ID 지정 후 정보 업데이트
- **curl 명령어**:
```bash
curl -X PUT "http://127.0.0.1:8000/items/1" -H "accept: application/json" -d "{\"name\": \"updated_item\", \"value\": 43}"
```
- **결과**:
```json
{"item_id":1,"updated_item":{"name":"updated_item","value":43}}
```

#### 3. DELETE 메소드 테스트

- **목적**: 특정 아이템 삭제
- **사용**: 아이템 ID 지정 후 삭제 요청
- **curl 명령어**:
```bash
curl -X DELETE "http://127.0.0.1:8000/items/1" -H "accept: application/json"
```
- **결과**:
```json
{"message":"Item 1 has been deleted"}
```

이러한 테스트 방법은 FastAPI로 구현한 API의 기능을 검증하는 데 유용하며, 특히 개발 단계에서 자주 사용됩니다. 요청 본문의 데이터 형식이 JSON인 경우에는 `Content-Type: application/json` 헤더를 추가해야 합니다.
