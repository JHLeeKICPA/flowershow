---
collection:
  - 📼Lecture
---
## 0. 빅데이터
* 기존: 관계형 데이터베이스(RDBMS)
	- SQL 언어로 사용 가능
	- SQL 데이터베이스
* 빅데이터: NoSQL 데이터베이스

## 1. NoSQL 이해
- Not only SQL(NoSQL)
- RDBMS의 한계를 극복하기 위해 만들어진 새로운 형태의 데이터저장소
- RDBMS처럼 고정된 **스키마가 존재하지 않음**

### 1.1. Why NoSQL?
- RDBMS를 기본으로 사용하지만,
- 초당 데이터가 수십만개씩 쌓이는 서비스가 많아지면서(쇼셜, 온라인 서비스등), NoSQL을 사용하는 경우가 많아지고 있음
- 경험적 수치
	- 95% read, 5% write 경우는 RDBMS 가 성능이 나쁘지 않음
	- 50% write > 인 경우 RDBMS는 성능 저하 또는 불안정
	- NoSQL (분산 환경) + redis (In memory cache) 등을 고려하게 됨
- 관계형 데이터베이스 종류
	- MySQL, Oracle, PostgreSQL, SQLlite
- NoSQL 데이터베이스는 각 데이터베이스마다 기반으로 하는 데이터 모델이 다르므로, 데이터 모델별로 대표적인 데이터베이스를 알아둘 필요가 있음
	  - 각기 데이터베이스 다루는 인터페이스가 다름
	    - Key/Value Store
	    - Wide Column Store
	    - Document Store
	    - Graph Store

<center>
    <img src="https://davelee-fun.github.io/fixeddata/nosqltypes.png">
    출처: https://supaerodatascience.github.io/OBD/0_3_project.html
</center>    

### 1.2. MongoDB 란?
* MongoDB는 document 기반 NoSQL 데이터베이스
	- MongoDB는 BSON(Binary JSON) 기반의 Document 로 데이터 관리
	- JSON 보다 대용량 데이터를 처리할 때 유용하며,
	- BSON의 이진 형식은 데이터를 빠르게 스캔하고 처리할 수 있음 

> JSON 데이터를 0 과 1 형식으로 변환하여 내부에서 저장하면, 성능상 이점이 있음

#### JSON 예제
```json
document  = {
    "id":"01",
    "languange":"java",
    "edition":{
        "first":"1st",
        "second":"2nd",
        "third":"third"
    }
}
```

#### MongoDB Document 예제
```json
{
    "_id": ObjectId("5099803df3f42312312391"),
    "username": "davelee",
    "name": { "first": "Dave", "last": "Lee" }
}
```

### 1.3. MongoDB 데이터 구조
 * MongoDB: Database - Collection(table 대체) - Document(Row 대체)
 * RDBMS: Database - Table - data
	- RDBMS의 table이 아니라, Collection 에 JSON 형태의 Document를 넣습니다.
	- Document 하나가 하나의 Row(레코드)임
<img src="https://davelee-fun.github.io/fixeddata/rdbms_nosql.png" /> 

#### MongoDB Database
* Database는 Collection의 집합

#### MongoDB Collection
* Collection은 MongoDB Document의 집합
* RDBMS Table과 유사한 개념, 단 정규화된 데이터 구조, 즉 Schema가 정의되어 있지 않음

<img src="https://davelee-fun.github.io/fixeddata/rdbms_mongodb.png" /> 

## 2. MongoDB 설치 및 환경 구축 

### 2.1. MongoDB  설치 방법 (맥/윈도우/리눅스 환경)

<div class="alert alert-block" style="border: 2px solid #E65100;background-color:#FFF3E0;padding:10px">
<font size="4em" style="color:#BF360C;">MongoDB 설치 방법이 수시로 변경되고, 설치가 단순하지 않아지고 있습니다.</font><br>
    <font size="4em" style="color:#BF360C;">그래서, 구글에서 mongdb linux install 또는 mongdb windows install 또는 mongodb mac install 로 검색하여, mongodb 공식 페이지의 가이드를 따르시는 것을 추천드립니다</font><br>
    - 예: https://www.mongodb.com/docs/manual/administration/install-on-linux/
</div>

### 2.2. EC2(AWS 서버)에 MongoDB  설정시 참고 사항 (ubuntu 리눅스)

* AWS Management Console -> EC2 -> Security Groups -> EC2's Security Group -> Add Custom TCP Rule, 27017, AnyWhere

* 외부 접속 허용
  - sudo vi /etc/mongod.conf
    - bindIp: 0.0.0.0   으로 변경
  - sudo systemctl restart mongod

* 계정 추가
  - EC2 에서 다음 명령 실행
  > 서버 상에서 MongoDB 계정을 추가하지 않으면, 외부에서 해당 포트/주소로 아무나 접속 가능 (해킹 위험)
  - 계정 추가 참고 명령
```bash
> mongosh
> use admin
> db.createUser(
  {
    user: "davelee",
    pwd: "funcoding",
    roles: [
      { role: "userAdminAnyDatabase", db: "admin" },
      { role: "readWriteAnyDatabase", db: "admin" }
    ]
  }
)
> exit
> sudo vi /etc/mongod.conf
security:
    authorization: enabled   # mongodb.conf 에서 해당 설정 변경
```
```bash
> sudo systemctl restart mongod
```

## 3. MongoDB 바로 다뤄보기

### 3.1. Studio 3T Free 설치 (MongoDB 관리 GUI 툴)

#### 기본 접속 설정
- Server
  - 사용할 mongodb PC(또는 서버) 주소
- Authentication (ID 설정시)
  - Authentication Mode: Basic(SCRAM-SHA-256) 
  - User Name: 사용자 ID
  - Password: 사용자 암호
  - Authentication DB: admin

### 3.2 기본 명령 이해하기

#### UI 로 데이터베이스/collection 생성 테스트
- Add Database 메뉴로 funcoding 데이터베이스 생성
- Add Collection 메뉴로 test collection 생성

#### 기본 명령 테스트해보며 이해하기
 - IntelliShell 으로 명령창 오픈

##### 1. 전체 데이터베이스 확인

```bash
show dbs 
```

##### 2. 데이터베이스 선택과 생성
 
- 해당 데이터베이스가 없으면 **데이터베이스 자동 생성**
```bash
use [DB 이름]
```

##### 3. 선택된 데이터베이스의 collection 확인

```bash
show collections
```

##### 4. collection 다루기
* 예) db.test.find() - test 컬렉션에서 전체 Document 검색
    ```bash
 db.[Collection 이름].함수()
```

##### 5. 데이터베이스 상세 정보 확인

```bash
db.stats()
```

##### 6. 데이터베이스/collection 삭제

```bash
db.dropDatabase()
db.[collection이름].drop()
```

##### 7. collection 생성

```bash
db.createCollection(name, options)
```
- name: 생성할 컬렉션의 이름을 나타냄
- options: 선택적 매개변수로 컬렉션의 동작을 설정하는데 사용
- options 매개변수에는 다음과 같은 필드가 사용될 수 있음
	- capped: 이 값이 true로 설정되면, capped 컬렉션을 생성, Capped 컬렉션은 고정된 크기를 가지며, 그 크기가 꽉 차면 가장 오래된 데이터부터 자동으로 삭제 기본값은 false
	- autoIndexId: 이 값이 true로 설정되면, `_id` 필드에 대한 인덱스를 자동으로 생성, 기본값은 false
	- size: capped 컬렉션의 최대 바이트 크기를 지정합니다. capped 옵션이 true일 때만 사용
	- max: capped 컬렉션에 저장할 수 있는 문서의 최대 개수를 지정
- collection 의 capped 설정 확인 명령
```bash
db.[collection이름].isCapped()
```

* collection 생성 예1
```bash
db.createCollection("users")
```

* collection 생성 예2
```bash
db.createCollection("log", { capped : true, size : 5242880, max : 5000 } )
```

##### 8. collection 이름 변경

```bash
db.[collection이름].renameCollection([변경할collection이름])
```

### 3.2 MongoDB 의 주요 데이터 타입

#### String
- 문자열 데이터 타입은 유니코드 문자열을 저장
- 예: name: "John Doe"와 같이 사용

#### Integer
- 정수 데이터 타입은 숫자를 저장. 32비트와 64비트 두 가지 형태가 있음
- 예: age: 25와 같이 사용

#### Boolean
- 불리언 데이터 타입은 참(true) 또는 거짓(false) 값을 저장
- 예: isStudent: true와 같이 사용

#### Double
- 부동 소수점 값(즉, 소수)을 저장하는 데이터 타입
- 예: rating: 4.5와 같이 사용

#### Arrays
- 배열 데이터 타입은 값의 리스트를 저장
- 예: hobbies: ["reading", "music", "travelling"]와 같이 사용

#### Object
- 객체 데이터 타입은 임베디드 문서를 저장하는데 사용
- 예: address: { city: "Seoul", country: "South Korea" }와 같이 사용

#### Null
- null 데이터 타입은 null 값을 저장하는데 사용
- 예: middleName: null과 같이 사용

#### ObjectId
- 문서 ID를 저장하는데 사용되는 데이터 타입
- 예: _id: ObjectId("507f1f77bcf86cd799439011")와 같이 사용

#### Date
- 날짜 데이터 타입은 시간 정보를 저장
- 예: createdAt: new Date()와 같이 사용

## 4. MongoDB 데이터 입력/수정/검색/삭제 (CRUD)

### 4.1. Document 입력 - insertOne, insertMany
- insertOne : 한개의 document 생성
- insertMany : list of document 생성

#### Document 입력 문법
<img src="https://davelee-fun.github.io/fixeddata/mongodb_insert_structure.png" /> 
#### SQL INSERT 문법과 비교
<img src="https://davelee-fun.github.io/fixeddata/mongodb_insert.png" /> 
#### insertOne 예제

```bash
db.users.insertOne(
     { subject: "coding", author: "funcoding", views: 50 }
)
```

#### insertMany 예제
```bash
db.users.insertMany(
   [
     { subject: "coffee", author: "xyz", views: 50 },
     { subject: "Coffee Shopping", author: "efg", views: 5 },
     { subject: "Baking a cake", author: "abc", views: 90  },
     { subject: "baking", author: "xyz", views: 100 },
     { subject: "Café Con Leche", author: "abc", views: 200 },
     { subject: "Сырники", author: "jkl", views: 80 },
     { subject: "coffee and cream", author: "efg", views: 10 },
     { subject: "Cafe con Leche", author: "xyz", views: 10 },
     { subject: "coffees", author: "xyz", views: 10 },
     { subject: "coffee1", author: "xyz", views: 10 }
   ]
)
```

##### 연습문제
1. users Collection 생성 (Capped Collection, size는 100000 으로 생성)
2. 다음 Document 데이터 넣기
```json
{ name:"David", age:45, address:"서울" }
{ name:"DaveLee", age:25, address:"경기도" }
{ name:"Andy", age:50, hobby:"골프", address:"경기도" }
{ name:"Kate", age:35, address:"수원시" }
{ name:"Brown", age:8 }
```

### 4.2. Document 읽기(검색) - findOne, find
  - findOne : 매칭되는 한개의 document 검색
  - find : 매칭되는 list of document 검색
  
  > db.[collection이름].find() 명령으로 전체 데이터 출력 가능

#### Document 읽기(검색) 문법
- query criteria: 조건
- projection: 결과값에서 보여질 field 선택
<img src="https://davelee-fun.github.io/fixeddata/mongodb_find_structure.png" /> 

##### find() 명령과 - SQL 문 비교

```sql
- db.users.find() 
- SELECT * FROM users

- db.users.find({ }, { name: 1, address: 1 }) 
- SELECT _id, name, address FROM users

- db.users.find({ },{ name: 1, address: 1, _id: 0 })
- SELECT name, address FROM users

- db.users.find({ address: "서울" })
- SELECT * FROM users WHERE address = "서울"
```

##### 연습문제
1. users Collection 에서 name 이 DaveLee 인 Document의 name, age, address, `_id 출력
2. users Collection 에서 name 가 Kate 인 Document의 name, age, address 출력

#### 비교 문법
- $eq     =    Matches values that are equal to a specified value.
- $gt     >    Matches values that are greater than a specified value.
- $gte    >=   Matches values that are greater than or equal to a specified value.
- $in          Matches any of the values specified in an array.
- $lt     <    Matches values that are less than a specified value.
- $lte    <=   Matches values that are less than or equal to a specified value.
- $ne     !=   Matches all values that are not equal to a specified value.
- $nin         Matches none of the values specified in an array.

##### 비교 문법 코드 예제
```bash
db.users.find({ age: { $gt: 25 } })
SELECT * FROM users WHERE age > 25

db.users.find({ age: { $lt: 25 } })
SELECT * FROM users WHERE age < 25

db.users.find({ age: { $gt: 25, $lte: 50 } })
SELECT * FROM users WHERE age > 25 AND age <= 50
```

##### 연습문제
1. 다음 Document 데이터 넣기
   - age 가 20 보다 큰 Document 의 name 만 출력하기
   - age 가 50 이고 address 가 경기도 인 Document 의 name 만 출력하기
   - age 가 30 보다 작은 Document 의 name 과 age 출력하기

#### 논리 연산 문법
$or           OR 조건
$and          AND 조건
$not          NOT 조건

##### 논리 연산 문법 코드 예제
```bash
db.users.find({ address: "서울", age: 45 })
db.users.find({ $and: [ {address: "서울"}, {age: 45} ] })
SELECT * FROM users WHERE address = "서울" AND age = 45

db.users.find({ $or: [ { address: "경기도" } , { age: 45 } ] })
SELECT * FROM users WHERE address = "경기도" OR age = 45

db.users.find({ age: { $not: { $eq: 45 } } })
SELECT * FROM users WHERE age != 45
```

##### 연습문제
1. users Collection 에서 name 가 Brown 이거나, age가 35인 Document 의 모든 필드 출력

##### 예제로 좀더 이해하는 논리 연산 문법

- users Collection 에서 name 가 Brown 이 아니고, age 가 45 가 아닌 모든 필드 출력

```bash
db.users.find({
  name: {
    $not: {
      $eq: "Brown"
    }
  },
  age: {
    $not: {
      $eq: 45
    }
  }
})

```

> 단 mongodb 는 명시적으로 \$and 를 넣지 않아도, 모든 조건을 AND 조건으로 처리함

```bash
db.users.find({
  $and: [
    {
      name: {
        $not: {
          $eq: "Brown"
        }
      }
    },
    {
      age: {
        $not: {
          $eq: 45
        }
      }
    }
  ]
})
```

- users Collection 에서 name 가 Brown 이 아니거나, age 가 45 가 아닌 모든 필드 출력

```bash
db.users.find({
  $or: [
    {
      name: {
        $not: {
          $eq: "Brown"
        }
      }
    },
    {
      age: {
        $not: {
          $eq: 45
        }
      }
    }
  ]
})
```

#### 유용한 추가 문법

##### 정규 표현식을 이용한 검색($regex)

- "Lee"라는 문자열을 이름 필드에서 찾는 명령: 
    - MongoDB: `db.users.find( { name: /Lee/ } )`
    - MongoDB: `db.users.find( { name: { $regex: /Lee/ } } )`
    - SQL에서는 `SELECT * FROM users WHERE name like "%Lee%"`와 동일    
- 이름 필드가 "Da"로 시작하는 모든 문서를 찾는 명령: 
    - MongoDB: `db.users.find( { name: /^Da/ } )`
    - MongoDB: `db.users.find( { name: { $regex: /^Da/ } } )`
    - SQL에서는 `SELECT * FROM users WHERE name like "Da%"`와 동일

##### 정렬(sort)

- 주소가 "경기도"인 모든 문서를 찾아서, 나이 순으로 오름차순 정렬하는 명령: 
    - MongoDB: `db.users.find( { address: "경기도" } ).sort( { age: 1 } )`
    - SQL에서는 `SELECT * FROM users WHERE address = "경기도" ORDER BY age ASC`와 동일
    
- 주소가 "경기도"인 모든 문서를 찾아서, 나이 순으로 내림차순 정렬하는 명령: 
    - MongoDB: `db.users.find( { address: "경기도" } ).sort( { age: -1 } )`
    - SQL에서는 `SELECT * FROM users WHERE address = "경기도" ORDER BY age DESC`와 동일

##### 문서 개수 세기(count)

- 사용자 컬렉션의 문서 수를 세는 명령:
    - MongoDB: `db.users.count()`, `db.users.find().count()`
    - SQL에서는 `SELECT COUNT(*) FROM users`와 동일

##### 필드 존재 여부로 개수 세기($exists)

- 주소 필드가 존재하는 문서 수를 세는 명령:
    - MongoDB: `db.users.count( { address: { $exists: true } } )`, `db.users.find( { address: { $exists: true } } ).count()`
    - SQL에서는 `SELECT COUNT(address) FROM users`와 비슷, MongoDB는 주소 필드가 존재하지 않는 문서는 제외
    
##### 중복 제거(distinct)

- 모든 사용자의 주소를 중복 없이 가져오는 명령: 
    - MongoDB: `db.users.distinct( "address" )`
    - SQL에서는 `SELECT DISTINCT(address) FROM people`과 동일

##### 한 개만 가져오기(findOne, limit)

- 사용자 컬렉션에서 한 개의 문서만 가져오는 명령: 
    - MongoDB: `db.users.findOne()`, `db.users.find().limit(1)`
    - SQL에서는 `SELECT * FROM users LIMIT 1`과 동일

#### 배열과 $all
- 배열(array)을 사용하여 여러 값을 하나의 필드에 저장 가능
- 배열은 대괄호([])로 묶인 값들의 리스트로 표현
- 예
```bash
db.users.insertMany([
   { name: "유진", age: 25, hobbies: ["독서", "영화", "요리"] },
   { name: "동현", age: 30, hobbies: ["축구", "음악", "영화"] },
   { name: "혜진", age: 35, hobbies: ["요리", "여행", "독서"] }
])
```

##### 배열 필드가 주어진 모든 값을 포함하는 문서 찾기($all)

- 취미 필드가 "축구"와 "요리"를 모두 포함하는 모든 문서를 찾는 명령:
    - MongoDB: `db.users.find( { hobbies: { $all: [ "축구", "음악" ] } } )`
    - SQL에서는 이와 동일한 기능을 직접적으로 지원하지 않으나, `SELECT * FROM users WHERE hobbies LIKE "%축구%" AND hobbies LIKE "%음악%"`와 유사하나, SQL의 경우 "hobbies" 필드가 문자열 타입이어야 함
    
##### 여러 값 중 하나와 일치하는 문서 찾기($in)

- 나이가 20세, 30세, 40세 중 하나인 모든 문서를 찾는 명령: 
    - MongoDB: `db.users.find( { hobbies: { $in: [ "축구", "요리" ] } } )`
    - SQL에서는 `SELECT * FROM users WHERE hobbies LIKE '%축구%' OR hobbies LIKE '%요리%'`과 동일

##### 여러 값 중 어떤 것과도 일치하지 않는 문서 찾기($nin)

- 나이가 20세, 30세, 40세 중 어떤 것도 아닌 모든 문서를 찾는 명령: 
    - MongoDB: `db.users.find( { hobbies: { $nin: [ "축구", "요리" ] } } )`
    - SQL에서는 `SELECT * FROM users WHERE hobbies NOT LIKE '%축구%' AND hobbies NOT LIKE '%요리%`과 동일

#### Document 수정 - updateOne, updateMany
  - updateOne - 매칭되는 한개의 document 업데이트
  - updateMany - 매칭되는 list of document 업데이트
  
> 업데이트해야 하는 데이터(Key:Value) 가 없으면, 해당 데이터가 해당 Document 에 추가됨

### 4.3. Document 수정 문법
<img src="https://davelee-fun.github.io/fixeddata/mongodb_update_structure.png" /> 
#### Document 수정 코드 예제

> 조건에 매칭이 되는 최초 데이터만 변경시에는 updateOne, 전체 데이터 변경시는 updateMany (통상적으로 updateMany 사용)

```bash
db.users.updateMany( { age: { $gt: 25 } }, { $set: { address: "서울" } } )
UPDATE users SET address = "서울" WHERE age > 25

db.users.updateMany( { address: "서울" } , { $inc: { age: 3 } } )
UPDATE users SET age = age + 3 WHERE status = "서울"
```

##### 연습문제
1. 다음 Document 데이터 수정하기
	- age 가 40 보다 큰 Document 의 address 를 수원시 로 변환하기

#### Document 수정 관련 유용한 문법

**특정 필드 업데이트하기**
- 이름이 '유진'인 문서에서 'age' 필드를 26으로 업데이트하는 명령:
    - MongoDB: `db.users.updateOne( { name: "유진" }, { $set: { age: 26 } } )`
    - SQL에서는 `UPDATE users SET age = 26 WHERE name = '유진'`과 동일

**문서를 replace 하기**
- 이름이 '동현'인 문서를 새로운 문서로 대체하는 명령:
    - MongoDB: `db.users.updateOne({ name: "동현" }, { $set: {"name": "동현2세", age: 31, hobbies: ["축구", "음악", "영화"]}})`
    - SQL에서는 이런 직접적인 대체는 지원하지 않으므로, 동등한 SQL 구문이 없음

**특정 필드를 제거하기**
- 이름이 '유진'인 문서에서 'age' 필드를 제거하는 명령:
    - MongoDB: `db.users.updateOne( { name: "유진" }, { $unset: { age: 1 } } )`
    - SQL에서는 `UPDATE users SET age = NULL WHERE name = '유진'`과 유사

**특정 조건을 만족하는 문서가 없을 경우 새로 추가하기**
- 이름이 '민준'인 문서가 없을 경우 새로운 문서를 추가하는 명령:
    - MongoDB: `db.users.updateOne({ name: "민준" }, { $set: { name: "민준", age: 22, hobbies: ["음악", "여행"] }}, { upsert: true })`
    - SQL에서는 이런 직접적인 기능은 지원하지 않음

**여러 문서의 특정 필드를 수정하기**
- 나이가 20 이하인 모든 문서에서 'hobbies' 필드를 '독서'로 업데이트하는 명령:
    - MongoDB: `db.users.updateMany( { age: { $lte: 20 } }, { $set: { hobbies: ["독서"] } } )`
    - SQL에서는 `UPDATE users SET hobbies = '독서' WHERE age <= 20`과 동일

**배열에 값 추가하기**
- 이름이 '유진'인 문서의 'hobbies' 배열에 '운동'을 추가하는 명령:
    - MongoDB: `db.users.updateOne( { name: "유진" }, { $push: { hobbies: "운동" } } )`
    - SQL에서는 이런 배열 추가 기능을 지원하지 않음

**배열에서 값 제거하기**
- 이름이 '유진'인 문서의 'hobbies' 배열에서 '운동'을 제거하는 명령:
    - MongoDB: `db.users.updateOne( { name: "유진" }, { $pull: { hobbies: "운동" } } )`
    - SQL에서는 이런 배열 제거 기능을 지원하지 않음

**참고**
MongoDB의 update() 함수는 기본적으로 첫 번째로 일치하는 문서만 업데이트합니다. 모든 일치하는 문서를 업데이트하려면 updateMany() 함수를 사용해야 합니다.

### 4.4. Document 삭제 - removeOne, removeMany
- removeOne - 매칭되는 한개의 document 삭제
- removeMany - 매칭되는 list of document 삭제

#### Document 삭제 문법
<img src="https://davelee-fun.github.io/fixeddata/mongodb_delete_structure.png" /> 

#### Document 삭제 코드 예제
```bash
db.users.deleteMany( { address: "서울" } )
DELETE FROM users WHERE status = "서울"

db.people.deleteMany({})
DELETE FROM people
```

##### 연습문제
1. 다음 Document 데이터 삭제하기
	- age 가 30 보다 작은 Document 삭제하기

## 5. Aggregation Framework

### 1. MongoDB Aggregation Framework
* 기존의 find로는 원하는 데이터로 가공하는데 어려움
* 빅데이터를 다루려면 새로운 데이터 가공 방식이 필요
* 이를 위해 MongoDB 에서는 Aggregation Framework (집계 프레임워크) 를 제공
	- MongoDB Aggregation Framework 는 파이프라인(pipeline) 개념을 모델로 함
- 파이프라인(pipeline) 이란, 이전 단계의 연산결과를 다음 단계연산에 이용하는 것을 의미
	- Unix의 pipe와 같은 방식으로 데이터를 처리하는 방식
	- document를 여러 단계의 파이프라인으로 처리해서, 데이터를 처리/집계한다고 이해하면 됨
* MongoDB Aggregation Framework 를 사용하면 documents를 grouping, filtering 등 다양한 연산을 적용할 수 있음

> 단순하게, find() 보다 복잡한 검색과 연산을 지원하는 또다른 MongoDB 문법이라고 생각하시면 쉽습니다.

#### Shard 와 MongoDB Aggregation Framework: 
  - Shard 란 전체 데이터의 서브셋을 가진 서버를 의미함
     - Sharding 은 여러 장비에 데이터를 분할하는 과정을 의미하고, Partitioning 이라고도 함
  - MongoDB 에서도 Shading 을 통해 여러 장비에 collection 을 쪼개 넣을 수 있고,
  - MongoDB Aggregation Framework 를 통해, 여러 장비에 동일한 요청을 동시에 처리하도록 하고, 
  - 이를 집계하여 계산하면, 빅데이터 상에서 성능을 급격히 높일 수 있음

#### MongoDB Aggregation Framework 문법과 Pipeline 동작
- Aggregation Pipeline: Aggregation은 주로 Aggregation Pipeline을 사용하여 데이터를 처리
	- Pipeline은 여러 단계로 구성되며, 각 단계는 데이터를 변형하거나 필터링하는데 사용 
	- 각 단계는 이전 단계의 결과를 입력으로 받아 처리하고, 최종 결과를 반환
- 매칭, 그룹화, 정렬, 프로젝션: Aggregation Pipeline은 다양한 단계로 구성될 수 있음
- 주요 단계에는 `$match`, `$group`, `$sort`, `$project` 등이 있음 
	- `$match`는 조건에 맞는 문서를 필터링
	- `$group`은 문서를 그룹화하고 집계 작업을 수행
	- `$sort`는 결과를 정렬
	- `$project`는 필요한 필드를 선택하거나 계산하여 결과에 포함시킴
- 이외에 다양한 집계 작업을 위한 기능 제공
	- `$sum, $avg, $min, $max, $count` 등으로 필드를 합산하거나 평균을 계산하고, 최소/최대 값을 찾을 수 있음

![MongoDB Aggregate Pipeline|675](https://davelee-fun.github.io/fixeddata/mongodb_aggregate_pipeline.png)

### 2. 주요 Mongodb Aggregation 문법

#### 사전준비
- 제공해드린 데이터를 툴을 사용하여 mongodb 에 import 

##### sample_mflix 데이터베이스

- `sample_mflix` 데이터베이스는 여러 영화와 관련 정보가 포함되어 있음 
- 영화 정보, 배우, 감독, 영화 리뷰 등에 대한 데이터가 포함되어 있음

##### movies collection
- 이 컬렉션은 각각의 영화에 대한 정보를 포함하고 있음 
    - `_id`: 각 영화의 고유 식별자
    - `title`: 영화의 제목
    - `plot`: 영화의 줄거리
    - `genres`: 영화의 장르 (예: 액션, 코미디 등)
    - `runtime`: 영화의 상영 시간 (분 단위)
    - `cast`: 영화 출연 배우
    - `directors`: 영화 감독
    - `year`: 영화가 개봉한 년도

##### comments collection
- 이 컬렉션은 사용자들이 남긴 영화에 대한 댓글을 포함하고 있음
    - `_id`: 각 댓글의 고유 식별자
    - `name`: 댓글을 남긴 사용자의 이름
    - `email`: 댓글을 남긴 사용자의 이메일
    - `movie_id`: 댓글이 남겨진 영화의 식별자
    - `text`: 댓글의 내용
    - `date`: 댓글이 작성된 날짜

#### aggregate()
- `aggregate()` 메서드는 Mongodb Aggregation 작업을 수행할 수 있게 해주는 메서드
- 이 메서드는 배열 형태로 표현하며, 맨 처음 연산부터, 순차적으로 파이프라인 연산을 수행함

```bash
db.collection.aggregate([ { <stage1> }, { <stage2> }, ... ])
```


##### $match

- `$match` 단계는 지정된 조건을 만족하는 문서만을 필터링하여 다음 파이프라인 단계로 전달하는 데 사용합니다

```bash
{ $match: { <query> } }
```

- 예를 들어, 1995년에 개봉한 모든 영화를 선택하려고 한다면 아래와 같이 질의할 수 있습니다

```bash
db.movies.aggregate([
  { $match: { year: 1995 } }
]);
```

##### $group

- `$group` 단계는 Document에 대한 그룹화를 수행하여 복잡한 집계 연산을 가능하게 합니다.
- `$group` 연산자는 그룹의 키를 정의하는 `_id` 필드를 필요로 합니다.
	- `_id`는 표현식이 될 수 있으며, 이는 그룹화의 기준이 됩니다.
- 각 그룹에 대해 집계를 수행할 수 있습니다.
	- 이는 필드와 해당 필드에 적용할 누산식(accumulator)의 쌍으로 제공됩니다.
	- 이 누산식은 `$sum`, `$avg`, `$min`, `$max` 등과 같은 여러 가지 연산자를 포함할 수 있습니다.

```bash
db.collection.aggregate([
  { 
    $group: {
      _id: <expression>, // 그룹화할 필드를 지정
      <field1>: { <accumulator1> : <expression1> }, // 그룹에 적용할 누산식
      ...
    }
  }
]);
```

- 예를 들어, 모든 영화에 대한 댓글 수를 집계하려면 다음과 같이 쿼리를 작성할 수 있습니다.
	- 여기서는 각 영화를 그룹화(`_id: "$movie_id"`)하고, 각 그룹에 대해 댓글 수를 누적(`$sum: 1`)하여 `commentCount` 필드에 저장합니다.

```bash
db.comments.aggregate([
  { 
    $group: {
      _id: "$movie_id",
      commentCount: { $sum: 1 }
    }
  }
]);
```

- `$sum: 1`은 그룹화된 문서의 개수를 세는 것을 의미합니다. 즉, 그룹 내의 각 문서를 카운트하여 개수를 계산합니다.
- `$sum: "$runtime" ` 과 같이 작성하면, runtime 컬럼의 값의 총합을 의미합니다.

##### 주요 accumulator

**1. `$sum`: 숫자 값을 누적하여 합계를 계산**
   ```bash
   db.movies.aggregate([
     {
       $group: {
         _id: "$year", 
         totalMovies: { $sum: 1 }
       }
     }
   ]);
   ```

   위 예제에서는 각 연도별로 출시된 영화의 총 수(`totalMovies`)를 계산합니다.

**2. `$avg`: 숫자 값의 평균을 계산**

   ```bash
   db.movies.aggregate([
     {
       $group: {
         _id: "$year",
         averageRating: { $avg: "$imdb.rating" }
       }
     }
   ]);
   ```

   위 예제에서는 각 연도별 영화의 IMDB 평점의 평균(`averageRating`)을 계산합니다.

**3. `$min` & `$max`: 최소값과 최대값을 찾음**

   ```bash
   db.movies.aggregate([
     {
       $group: {
         _id: "$year",
         minRating: { $min: "$imdb.rating" },
         maxRating: { $max: "$imdb.rating" }
       }
     }
   ]);
   ```

   위 예제에서는 각 연도별 영화의 IMDB 평점 중 최소(`minRating`)와 최대(`maxRating`) 평점을 찾습니다.

**4. `$push`: 그룹에 있는 모든 값들을 배열로 반환**

```bash
db.movies.aggregate([
 {
   $group: {
     _id: "$year",
     titles: { $push: "$title" }
   }
 }
]);
```

   위 예제에서는 각 연도별로 출시된 영화의 제목들(`titles`)을 배열로 묶습니다.

**5. `$addToSet`: 중복되지 않는 값들만 배열로 반환**

   ```bash
   db.movies.aggregate([
     {
       $group: {
         _id: "$year",
         genres: { $addToSet: "$genres" }
       }
     }
   ]);
   ```

   위 예제에서는 각 연도별 영화 장르(`genres`)를 중복 없이 배열로 묶습니다.

**6. `$first` & `$last`: 그룹에서 가장 첫번째 또는 마지막 문서를 반환**
- 202502 업데이트
	- year 필드가 문자열일 경우 정렬이 제대로 되지 않는 경우가 있을 수 있음을 확인하였습니다 
	- 이를 보완하기 위해 year 필드값을 문자열에서 정수형으로 변환합니다.
	- ```$toInt: "$year"``` 는 문자열을 정수로 변환하는 연산자

```bash
db.movies.aggregate([
    {
      $project: {
        year: { $toInt: "$year" },
        title: 1
      }
    },
    {
        $sort: { "year": 1, "title": 1 }
    },
    {
        $group: {
            _id: "$year",
            firstMovie: { $first: "$title" },
            lastMovie: { $last: "$title" }
        }
    }
]);
```

위 예제에서는 각 연도별로 가장 먼저와 마지막으로 등록된 영화의 제목(`firstMovie`, `lastMovie`)을 찾습니다. `$first`와 `$last`는 입력 문서의 순서에 의존하므로, 일반적으로 `$sort` 연산자와 함께 사용됩니다.

**7. `$strLenCP`: 문자열의 길이를 반환**

```bash
db.movies.aggregate([
    {
        $group: {
            _id: "$year",
            avgTitleLength: { $avg: { $strLenCP: { $toString: "$title" } } }
        }
    }
]);
```

위 예제에서는 각 연도별 영화 제목의 평균 길이(`avgTitleLength`)를 계산합니다.

##### $count

`$count` 스테이지는 파이프라인에서 들어오는 문서 수를 계산합니다. 이 스테이지는 출력 필드의 이름을 파라미터로 받아 출력 문서에 추가합니다.

예시:
2000년 이후에 출시된 영화의 수를 계산하는 쿼리입니다:

```bash
db.movies.aggregate([
    { $match: { year: { $gte: 2000 } } },
    { $count: "movies_since_2000" }
]);
```

위의 쿼리는 2000년 이후에 출시된 영화의 개수를 `movies_since_2000` 필드에 저장하게 됩니다.

##### $sort

`$sort` 스테이지는 입력 문서를 지정된 필드를 기준으로 정렬합니다. 정렬 필드와 순서(오름차순 : 1, 내림차순 : -1)를 지정할 수 있습니다.

예시:
영화를 출시 연도와 제목을 기준으로 오름차순으로 정렬하는 쿼리입니다:

```bash
db.movies.aggregate([
    { $sort: { "year": 1, "title": 1 } }
]);
```

위의 쿼리는 먼저 영화를 출시 연도에 따라 정렬한 후, 같은 연도의 영화들은 제목으로 다시 정렬하게 됩니다.

##### $unwind

`$unwind` 스테이지는 배열 필드를 "풀어"서 각각의 배열 요소가 개별 문서로 처리될 수 있게 합니다. 배열에 포함된 각 요소에 대해 입력 문서의 복사본을 생성하며, 이렇게 생성된 문서는 배열에서의 요소와 함께 출력됩니다.

예시:
각 영화의 장르별로 문서를 생성하는 쿼리입니다:

```bash
db.movies.aggregate([
    { $unwind: "$genres" }
]);
```

위의 쿼리는 각 영화의 각 장르에 대해 별도의 문서를 생성하게 됩니다. 그 결과, 장르가 'Drama', 'Comedy', 'Romance'인 영화는 세 개의 문서로 처리됩니다. 각 문서는 원래의 문서에서 복사되며, "genres" 필드는 해당 장르로 대체됩니다.


##### $limit

`$limit` 스테이지는 파이프라인이 출력하는 문서의 수를 제한합니다. `$limit`는 숫자를 인자로 받으며, 이 숫자는 출력할 문서의 최대 개수를 지정합니다.

`$limit`는 주로 정렬된 데이터셋에서 상위 혹은 하위 n개의 결과를 가져올 때 사용됩니다. 이 때는 `$sort` 스테이지와 함께 사용됩니다.

예시:

가장 높은 평점을 가진 상위 5개의 영화를 선택하는 쿼리입니다:

```bash
db.movies.aggregate([
    { $sort: { "imdb.rating": -1 } },
    { $limit: 5 }
]);
```

위의 쿼리는 영화를 IMDB 평점에 따라 내림차순으로 정렬한 후, 상위 5개의 영화만 선택하게 됩니다.

`$limit`은 성능 최적화를 위해 자주 사용됩니다. 큰 데이터셋에서 작은 부분집합만 필요할 때 `$limit`를 사용하면 불필요한 데이터 처리를 피할 수 있어 처리 속도를 향상시킬 수 있습니다.

#### 연습문제
**1. 2000년 이후로 출시된 영화의 수는 얼마인가요?**

```bash
db.movies.aggregate([
    { $match: { year: { $gte: 2000 } } },
    { $count: "total_movies" }
]);
```

**2. 각 연도별로 출시된 영화의 수는 어떻게 되나요?**

```bash
db.movies.aggregate([
    { $group: { _id: "$year", count: { $sum: 1 } } },
    { $sort: { _id: 1 } }
]);
```

**3. 가장 많은 영화가 출시된 연도는 언제인가요?**

```bash
db.movies.aggregate([
    { $group: { _id: "$year", count: { $sum: 1 } } },
    { $sort: { count: -1 } },
    { $limit: 1 }
]);
```

**4. 각 연도별 평균 영화 러닝타임은 어떻게 되나요?**

```bash
db.movies.aggregate([
    { $group: { _id: "$year", avgRuntime:{ $avg: "$runtime" } } },
    { $sort: { avgRuntime: -1} },
]);
```

**5. 가장 러닝타임이 긴 영화는 어떤 영화인가요?**

```bash
db.movies.aggregate([
    { $sort: { runtime: -1 } },
    { $limit: 1}
])
```

**6. 각 영화 장르별 평균 IMDB 평점은 어떻게 되나요?**

```bash
db.movies.aggregate([
    { $unwind: "$genres" },
    { $group: { _id: "$genres", avgRating: { $avg: "$imdb.rating"}}},
    { $sort: { avgRating: -1} }
])
```

**7. 각 연도별 영화 제목의 평균 길이는 어떻게 되나요?**

```bash
db.movies.aggregate([
    { $group: { _id: "$year", avgTitleLength: { $avg: { $strLenCP: { $toString: "$title"}}}}},
    { $sort: { _id: 1} }
])
```

**8. 각 연도별로 가장 먼저 출시된 영화의 제목은 무엇인가요?**

```bash
db.movies.aggregate([
    { $sort: { "year": 1, "released": 1} },
    { $group: { _id: "$year", firstMovie: { $first: "$title" } } },
    { $sort: { _id: 1} }
])
```

**9. 각 연도별로 가장 마지막에 출시된 영화의 제목은 무엇인가요?**

```bash
db.movies.aggregate([
    { $sort: { "year": 1, "released": 1} },
    { $group: { _id: "$year", lastMovie: { $last: "$title" } } },
    { $sort: { _id: 1} }
])
```

**10. 각 연도별로 고유한 영화 장르는 어떻게 되나요?**

```bash
db.movies.aggregate([
    { $unwind: "$genres" },
    { $group: { _id: "$year", uniqueGenres: { $addToSet: "$genres" } } },
    { $sort: { _id: 1 } }
]);
```

참고로, 위의 예상 답안은 실제 `sample_mflix` 데이터셋의 내용에 따라 다르게 나올 수 있습니다. 이 연습 문제들은 MongoDB의 `$match`, `$group` 연산자 및 주요 누산식들에 대한 이해를 돕는 데 도움이 될 것입니다.

>sort와 count 제외하고는 모두 인자로 $을 포함해야함

### Aggregation 고급 명령 이해

#### $project

`$project` 스테이지는 출력 문서에 특정 필드를 선택하거나 필드의 형식을 변환하는 데 사용됩니다. 필드 이름에 대한 명시적인 표현식, 새로운 필드 생성, 필드 제외 등 다양한 기능을 제공합니다.

예시:
각 영화의 제목과 출시 연도만 출력하는 쿼리입니다:

```bash
db.movies.aggregate([
    { $project: { _id: 0, title: 1, year: 1 } }
]);
```

위의 쿼리는 출력 문서에서 `_id` 필드를 제외하고, `title`과 `year` 필드만을 선택하여 출력합니다.

새로운 필드를 생성하는 예시로는 다음과 같습니다:

```bash
db.movies.aggregate([
    { 
        $project: { 
            title: 1,
            year: 1,
            releasedIn: { $concat: ["$title", " (", { $toString: "$year" }, ")"] }
        }
    }
]);
```

위의 쿼리는 `title`과 `year` 필드를 선택하고, `releasedIn`이라는 새로운 필드를 생성합니다. `releasedIn` 필드는 `title`과 `year`을 연결하고 괄호로 둘러싸여 출력됩니다.

`$project` 스테이지는 출력에 특정 필드를 포함하거나 제외함으로써 데이터를 가공하는 데 유용합니다. 필요한 필드만 선택하여 데이터의 용량을 줄이거나 필드 형식을 변환하여 데이터를 처리할 수 있습니다


#### $concat`

`$concat` 연산자는 문자열 필드를 연결하여 새로운 문자열을 생성하는 데 사용됩니다. 여러 문자열 필드를 조합하거나 문자열과 상수를 문자열로 만들어 조합하여 새로운 문자열 값을 만들 수 있습니다.

```bash
{ $concat: [ <expression1>, <expression2>, ... ] }
```
-  \<expression1\>, \<expression2\> 등은 문자열 필드 또는 상수 값입니다.
- 인자로 전달된 필드 또는 상수 값을 순서대로 연결하여 새로운 문자열을 생성합니다.
- `$concat`은 문자열 필드 또는 상수를 조합하여 동적인 문자열 값을 생성하는 데 유용합니다. 필요한 경우 다른 Aggregation 연산자와 함께 사용하여 문자열을 가공하고 다양한 형식으로 표현할 수 있습니다.


예시:
영화 제목과 출시 연도를 조합하여 새로운 필드인 `titleWithYear`를 생성하는 쿼리입니다:

```bash
db.movies.aggregate([
    {
        $project: {
            _id: 0,
            title: 1,
            year: 1,
            titleWithYear: { $concat: ["$title", " (", { $toString: "$year" }, ")"] }
        }
    }
]);
```

위의 쿼리는 `$concat`을 사용하여 `$title` 필드와 " (" 문자열, `$year` 필드를 문자열로 변환한 값, ")" 문자열을 조합하여 `titleWithYear` 필드를 생성합니다. 이를 통해 영화 제목과 출시 연도가 포함된 새로운 문자열 값을 만들 수 있습니다.

#### $lookup`
- `$lookup` 연산자는 Aggregation Framework에서 다른 컬렉션과의 조인(join) 작업을 수행하여 관련 데이터를 결합하는 데 사용됩니다. 주어진 필드에서 값이 일치하는 문서를 다른 컬렉션에서 찾아서 연결합니다.
- `$lookup` 연산자는 다른 컬렉션과의 조인 작업을 통해 데이터를 결합할 수 있어 복잡한 데이터 질의와 관련된 정보를 가져올 때 유용합니다. 

```bash
{
    $lookup: {
        from: <collection>,
        localField: <field>,
        foreignField: <field>,
        as: <newField>
    }
}
```
- from: 조인할 컬렉션의 이름입니다.
- localField: 현재 컬렉션에서 조인에 사용할 필드입니다.
- foreignField: 조인할 컬렉션에서 조인에 사용할 필드입니다.
- as: 조인된 결과를 저장할 필드의 이름입니다.

예시1:

comments 컬렉션의 각 도큐먼트에 대해 movies 컬렉션의 도큐먼트와 일치하는 것을 찾으려면 다음과 같이 쿼리를 작성할 수 있습니다.

```bash
db.comments.aggregate([
   {
      $lookup:
        {
          from: "movies",
          localField: "movie_id",
          foreignField: "_id",
          as: "movie"
        }
   }
])

```

위의 쿼리는 comments 컬렉션의 movie_id 필드와 movies 컬렉션의 `_id` 필드가 일치하는 도큐먼트를 찾습니다. 일치하는 각 movies 도큐먼트는 새로운 movie 필드로 comments 도큐먼트에 추가됩니다.

예시2:

users 컬렉션의 각 도큐먼트에 대해 comments 컬렉션의 도큐먼트와 일치하는 것을 찾으려면 다음과 같이 쿼리를 작성할 수 있습니다.

```bash
db.users.aggregate([
   {
      $lookup:
        {
          from: "comments",
          localField: "email",
          foreignField: "email",
          as: "user_comments"
        }
   }
])
```

위의 쿼리를 실행하면 'users' 컬렉션의 각 도큐먼트에 'user_comments'라는 이름의 배열 필드가 추가되며, 해당 배열에는 사용자가 작성한 모든 댓글의 정보가 들어갑니다. 즉, 각 사용자와 그들이 남긴 댓글을 한번의 쿼리로 쉽게 확인할 수 있습니다.

#### $skip`

`$skip` 스테이지는 파이프라인에서 일정 개수의 문서를 건너뛰고 그 다음 문서들을 출력합니다.

문법:
```bash
{ $skip: <num> }
```

- `<num>`은 건너뛸 문서의 개수를 나타내는 숫자입니다.

예시:

1. 첫 번째 3개의 영화를 건너뛰고 나머지 영화를 출력하는 쿼리입니다:
```bash
db.movies.aggregate([
    { $skip: 3 }
]);
```

2. 러닝타임이 100분 이상인 영화 리스트에서 상위 5개의 영화를 건너띄고, 나머지 영화를 출력하는 쿼리입니다:
```bash
db.movies.aggregate([
    { $match: { runtime: { $gte: 100 } } },
    { $skip: 5 }
]);
```

#### $facet`

`$facet` 스테이지는 단일 Aggregation 파이프라인 내에서 다중 Aggregation 파이프라인을 정의하여 여러 결과 집합을 생성합니다.

문법:
```bash
{
    $facet: {
        <outputField1>: [ <stage1>, <stage2>, ... ],
        <outputField2>: [ <stage3>, <stage4>, ... ],
        ...
    }
}
```

- `<outputField1>`, `<outputField2>` 등은 각각의 결과 집합에 대한 출력 필드 이름입니다.
- `<stage1>`, `<stage2>` 등은 각각의 결과 집합을 생성하기 위한 Aggregation 스테이지입니다.

예시:

1. 출시 연도별로 영화 수와 최고 평점을 구하는 쿼리입니다:
```bash
db.movies.aggregate([
    {
        $facet: {
            movieCountByYear: [
                { $group: { _id: "$year", count: { $sum: 1 } } }
            ],
            maxRatingByYear: [
                { $group: { _id: "$year", maxRating: { $max: "$imdb.rating" } } }
            ]
        }
    }
]);
```

#### $redact`

`$redact` 스테이지는 문서 내에서 보안이나 필터링 규칙에 따라 문서를 제어하는 데 사용됩니다.

문법:
```bash
{
    $redact: {
        $cond: {
            if: <condition>,
            then: <expression1>,
            else: <expression2>
        }
    }
}
```

- `<condition>`은 문서를 허용할지 거부

할지 결정하는 조건을 나타내는 표현식입니다.
- `<expression1>`은 조건이 true일 때 적용되는 표현식입니다.
- `<expression2>`는 조건이 false일 때 적용되는 표현식입니다.

예시:

평균 평점이 7 이상인 영화만을 출력하는 쿼리입니다:
```bash
db.movies.aggregate([
    {
        $redact: {
            $cond: {
                if: { $gte: ["$imdb.rating", 7] },
                then: "$$KEEP",
                else: "$$PRUNE"
            }
        }
    }
])
```

- `$$KEEP`: 이 변수를 사용하면 현재 도큐먼트 또는 임베디드 도큐먼트를 보존하고 다음 하위 도큐먼트를 검토합니다.
- `$$PRUNE`: 이 변수를 사용하면 현재 도큐먼트 또는 임베디드 도큐먼트를 제거하고 추가 검토를 중지합니다.

#### 연습문제

**1. 각 영화의 제목과 해당 영화에 달린 댓글들을 출력하세요.**
```mongodb
db.movies.aggregate([
  { 
    $lookup: {
      from: "comments",
      localField: "_id",
      foreignField: "movie_id",
      as: "movie_comments"
    }
  },
  { 
      $project: { 
          _id: 0, 
          title: 1, 
          movie_comments: {
              $map: {
                  input: "$movie_comments",
                  as: "comment",
                  in: "$$comment.text"
              }
          } 
      } 
  },
  { $limit: 5 }
]);
```

**2. 평점이 가장 높은 영화의 제목과 평점을 출력하세요.**
```mongodb
db.movies.aggregate([
    { $match: { "imdb.rating": { $ne: ""} } },
    { $sort: { "imdb.rating": -1} },
    { $limit: 1},
    { $project: { _id: 0, title: 1, "imdb.rating": 1} }
])
```

**3. 각 장르별로 평균 평점이 가장 높은 장르와 평균 평점을 출력하세요.**
```mongodb
db.movies.aggregate([
    { $unwind: "$genres" },
    { $group: { _id: "$genres", avgRating: { $avg: "$imdb.rating"} } },
    { $sort: { avgRating: -1} },
    { $limit: 1},
    { $project: { _id: 1, avgRating: 1} }
])
```

**4. 평균 러닝타임이 가장 짧은 개봉 연도와 평균 러닝타임을 출력하세요.**
```mongodb
db.movies.aggregate([
    { $group: { _id: "$year", avgRuntime: { $avg: "$runtime"} } },
    { $sort: { avgRuntime: 1} },
    { $limit: 1},
    { $project: { _id: 0, year: "$_id", avgRuntime: 1} }
])
```

**5. 각 국가별로 가장 많은 영화를 제작한 감독과 그 감독의 영화 수를 출력하세요.**
```mongodb
db.movies.aggregate([
    { $unwind: "$directors" },
    { $unwind: "$countries" },
    { $group: 
        { _id: { country: "$countries", director: "$directors"}, 
            count: { $sum: 1} 
         } 
    },
    { $sort: { count: -1 } },
    { $group: 
        { _id: "$_id.country", 
            topDirector: { $first: "$_id.director"}, 
            movieCount: { $first: "$count"} 
         } 
     },
     { $project: { _id: 0, country: "$_id", topDirector: 1, movieCount: 1}}
])
```

**6. 각 연도별로 가장 많은 평점을 받은 영화의 제목과 평점을 출력하세요.**
```mongodb
db.movies.aggregate([
    { $sort: { "year": 1, "imdb.rating": -1 } },
    {
        $group: {
            _id: "$year",
            title: { $first: "$title" },
            maxRating: { $first: "$imdb.rating" }
        }
    },
    { $project: { _id: 0, year: "$_id", title: 1, maxRating: 1 } }
])
```

**7. 각 장르별 영화 갯수를 영화 갯수가 가장 많은 순으로 출력하세요.**
```mongodb
db.movies.aggregate([
    { $unwind: "$genres" },
    { $group: { _id: "$genres", count: { $sum: 1} } },
    { $sort: { count: -1 } },
    { $project: { _id: 0, genre: "$_id", movieCount: "$count" } }
])
```

**8. 영화 감독별로 평균 평점이 가장 높은 감독과 그 감독의 평균 평점을 출력하세요.**
```mongodb
db.movies.aggregate([
  { $unwind: "$directors" },
  { $group: { _id: "$directors", avgRating: { $avg: "$imdb.rating" } } },
  { $sort: { avgRating: -1 } },
  { $limit: 1 },
  { $project: { _id: 0, director: "$_id", avgRating: 1 } }
]);
```

**9. 장르별로 평균 러닝타임이 가장 긴 장르와 그 장르의 평균 러닝타임을 출력하세요.**
```mongodb
db.movies.aggregate([
  { $unwind: "$genres" },
  { $group: { _id: "$genres", avgRuntime: { $avg: "$runtime" } } },
  { $sort: { avgRuntime: -1 } },
  { $limit: 1 },
  { $project: { _id: 0, genre: "$_id", avgRuntime: 1 } }
]);
```

**10. 각 영화의 제목과 해당 영화에 대해 댓글을 남긴 사용자들을 출력하세요.**
```mongodb
db.movies.aggregate([
  { 
    $lookup: {
      from: "comments",
      localField: "_id",
      foreignField: "movie_id",
      as: "movie_comments"
    }
  },
  { 
    $project: { 
      _id: 0, 
      title: 1, 
      users: "$movie_comments.name" 
    } 
  }
])
```

## 6. mongodb_python

### 1. MongoDB 와 파이썬
- 역시 파이썬으로 MongoDB 를 다룰 수 있는 다양한 라이브러리가 있음
- 이중에서 가장 많이 사용되는 라이브러리가 pymongo 임

> pymongo 기반 주요 코드를 가능한 쉽게, 패턴화하여, 파이썬으로 MongoDB 를 다루는 방법을 익히기로 함

#### 1. pymongo 설치
- 먼저, pymongo를 설치해야 합니다. 다음 명령을 사용하여 pymongo를 설치하세요.


```python
!pip install pymongo
```

    Requirement already satisfied: pymongo in /Users/davelee/opt/anaconda3/lib/python3.10/site-packages (4.4.0)
    Requirement already satisfied: dnspython<3.0.0,>=1.16.0 in /Users/davelee/opt/anaconda3/lib/python3.10/site-packages (from pymongo) (2.3.0)
    

#### 2. MongoDB에 연결하기
- MongoDB에 연결하려면 MongoClient 클래스를 사용해야 합니다. 
- MongoClient 객체를 생성하고 host 매개변수에 MongoDB 서버의 주소와 포트를 지정합니다.
- 다음 코드에서 username 및 password는 MongoDB 인스턴스에 대한 실제 사용자 이름과 비밀번호로 대체되어야 합니다. 
- 또한, localhost:27017 부분은 MongoDB 서버의 주소와 포트로 실제 값으로 대체되어야 합니다.

```python
# MongoDB에 연결 (인증 필요시)
client = MongoClient("mongodb://username:password@localhost:27017")
```


```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
```

#### 3. 데이터베이스 생성 및 선택
- 연결된 MongoDB 클라이언트에서 데이터베이스를 생성하고 선택할 수 있습니다. 
- client 객체의 database_name 속성을 사용하여 데이터베이스를 생성하고 선택합니다.

```python
# 데이터베이스 선택 
# 해당 데이터베이스가 없으면 해당 데이터베이스에 새로운 컬렉션에 데이터 처리시, 해당 데이터베이스와 컬렉션이 자동 생성
db = client["mydatabase"]
# 또는 
db = client.mydatabase
```

##### 데이터베이스의 컬렉션 리스트 확인


```python
# list_collection_names() 를 통해 컬렉션 리스트를 가져올 수 있음
db = client['test']
collections = db.list_collection_names()
for collection in collections:
    print(collection)
```

##### 컬렉션 생성 및 선택

```python
# 컬렉션 선택 (해당 컬렉션이 없으면 해당 컬렉션에 데이터 처리시, 해당 컬렉션이 자동 생성)
users = db["users"]
# 또는 
users = db.users
```

#### 4. 데이터 삽입
- 데이터를 MongoDB에 삽입하려면 insert_one() 또는 insert_many() 메서드를 사용합니다.


```python
# 단일 문서 삽입
db = client['test']
collection = db.users
data = {"name": "John", "age": 30}
result = collection.insert_one(data)
print("Inserted ID:", result.inserted_id) # _id 

# 여러 문서 삽입
data = [
    {"name": "Alice", "age": 25},
    {"name": "Bob", "age": 35},
    {"name": "Charlie", "age": 40}
]
result = collection.insert_many(data)
print("Inserted IDs:", result.inserted_ids) # _id 리스트
```

    Inserted ID: 649a9dfc0358237921bcfc96
    Inserted IDs: [ObjectId('649a9dfc0358237921bcfc97'), ObjectId('649a9dfc0358237921bcfc98'), ObjectId('649a9dfc0358237921bcfc99')]
    

#### 5. 데이터 조회
- 데이터를 조회하려면 find_one() 또는 find() 메서드를 사용합니다.

> MongoDB 에서는 findOne() 또는 insertMany 과 같이 naming 이 되어 있지만, pymongo 에서는 find_one() 또는 insert_many() 와 같은 naming 으로 되어 있음


```python
# 단일 문서 조회
db = client['test']
collection = db.users
document = collection.find_one({"name": "John"})
print('find_one')
print(document)

# 모든 문서 조회
print('find')
documents = collection.find()
for document in documents:
    print(document)
```

    find_one
    None
    find
    {'_id': ObjectId('649a9dfc0358237921bcfc98'), 'name': 'Bob', 'age': 35, 'is_available': True}
    {'_id': ObjectId('649a9dfc0358237921bcfc99'), 'name': 'Charlie', 'age': 40, 'is_available': True}
    

#### 6. 데이터 수정
- 데이터를 수정하려면 update_one() 또는 update_many() 메서드를 사용합니다.


```python
# 단일 문서 수정
collection = db.users
filter = {"name": "John"}
update = {"$set": {"age": 31}}
result = collection.update_one(filter, update)
print("Modified Count:", result.modified_count) # 수정된 document count

# 여러 문서 수정
filter = {"age": {"$gt": 30}}
update = {"$set": {"is_available": True}}
result = collection.update_many(filter, update)
print("Modified Count:", result.modified_count) # 수정된 document count
```

    Modified Count: 0
    Modified Count: 3
    

#### 7. 데이터 삭제
- 데이터를 수정하려면 delete_one() 또는 delete_many() 메서드를 사용합니다.


```python
# 단일 문서 삭제
collection = db.users
filter = {"name": "John"}
result = collection.delete_one(filter)
print("Deleted Count:", result.deleted_count) # 삭제된 document count

# 여러 문서 삭제
filter = {"age": {"$lt": 30}}
result = collection.delete_many(filter)
print("Deleted Count:", result.deleted_count) # 삭제된 document count
```

    Deleted Count: 0
    Deleted Count: 1
    

#### 8. 프로그램 종료
- 프로그램 종료시에는 MongoClient() 객체에 close() 를 명시적으로 호출해주는 것이 좋습니다.
- 또는 다음과 같이 파이썬의 with 문법을 활용하면, close() 를 명시적으로 호출해주지 않아도, 자동으로 호출됨

```python
from pymongo import MongoClient

# MongoDB에 연결
with MongoClient("mongodb://localhost:27017") as client:
    # 작업 수행
    pass
```


```python
# 연결 종료
client.close()
```

#### 9. 전체 pymongo 템플릿 코드


```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용

db = client['test']  # 'test' 데이터베이스 선택

collection = db.users  # 'users' 컬렉션 선택

documents = collection.find()  # 'users' 컬렉션의 모든 문서 조회
for document in documents: # find() 의 결과는 iterable 객체이므로 반복문을 통해 각 데이터를 가져와야 함
    print(document)

# 연결 종료
client.close()
```

    {'_id': ObjectId('649a9dfc0358237921bcfc98'), 'name': 'Bob', 'age': 35, 'is_available': True}
    {'_id': ObjectId('649a9dfc0358237921bcfc99'), 'name': 'Charlie', 'age': 40, 'is_available': True}
    

### 2. 기본 pymongo 템플릿 코드
> sample_mflix 데이터셋을 기반으로, 지금까지 익힌 mongodb 문법을 pymongo 에서 어떻게 적용해서 사용할 수 있는지를 알아보기로 함


```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용

db = client.sample_mflix
movies = db.movies
```

#### 다양한 find() 문법 적용

**1. 프로젝션(projection) - 결과 문서에 표시할 필드 지정:**


```python
for movie in movies.find({"year": 1923}, {"_id": 0, "title": 1, "year": 1}):
    print(movie, movie['year'])
```

    <class 'dict'> {'title': 'The Hunchback of Notre Dame', 'year': 1923} 1923
    <class 'dict'> {'title': 'Our Hospitality', 'year': 1923} 1923
    <class 'dict'> {'title': 'Safety Last!', 'year': 1923} 1923
    <class 'dict'> {'title': 'Three Ages', 'year': 1923} 1923
    <class 'dict'> {'title': 'A Woman of Paris: A Drama of Fate', 'year': 1923} 1923
    <class 'dict'> {'title': 'The Chechahcos', 'year': 1923} 1923
    

**2. 비교 쿼리 연산자 - MongoDB 비교 쿼리 연산자 사용:**


```python
# 1910년 이전에 출시된 영화 찾기
for movie in movies.find({"year": {"$lt": 1910}}, {"_id": 0, "title": 1, "year": 1}):
    print(movie)
```

    {'title': 'Blacksmith Scene', 'year': 1893}
    {'title': 'The Great Train Robbery', 'year': 1903}
    {'title': 'A Corner in Wheat', 'year': 1909}
    {'title': 'The Kiss', 'year': 1896}
    {'title': 'Dickson Experimental Sound Film', 'year': 1894}
    {'title': 'The Kiss', 'year': 1896}
    {'title': 'Newark Athlete', 'year': 1891}
    

**3. 논리 쿼리 연산자 - MongoDB 논리 쿼리 연산자 사용:**


```python
# 1900년 이전 또는 2015년 이후에 출시된 영화 찾기
for movie in movies.find(
        {"$or": [{"year": {"$lt": 1900}}, {"year": {"$gt": 2015}}]},
        {"_id": 0, "title": 1, "year": 1}
):
    print(movie)
```

    {'title': 'Blacksmith Scene', 'year': 1893}
    {'title': 'The Kiss', 'year': 1896}
    {'title': 'Dickson Experimental Sound Film', 'year': 1894}
    {'title': 'The Kiss', 'year': 1896}
    {'title': 'Newark Athlete', 'year': 1891}
    {'title': 'The Masked Saint', 'year': 2016}
    

**4. 배열 쿼리 연산자 - MongoDB 배열 쿼리 연산자 사용:**


```python
# 'Action'과 'Sci-Fi' 장르의 영화 찾기
for movie in movies.find(
        {"genres": {"$all": ["Action", "Sci-Fi", "Drama"]}},
        {"_id": 0, "title": 1, "year": 1, "genres": 1}
):
    print(movie)
```

    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Das Millionenspiel', 'year': 1970}
    {'year': 1978, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Superman'}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'The Chain Reaction', 'year': 1980}
    {'genres': ['Sci-Fi', 'Action', 'Drama'], 'title': 'City Limits', 'year': 1984}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Solarbabies', 'year': 1986}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Until the End of the World', 'year': 1991}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Timebomb', 'year': 1991}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'No Escape', 'year': 1994}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Chain Reaction', 'year': 1996}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': "Smilla's Feeling for Snow", 'year': 1997}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Soldier', 'year': 1998}
    {'year': 1997, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Volcano'}
    {'year': 1998, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Deep Impact'}
    {'year': 2002, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Equilibrium'}
    {'year': 2000, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Battle Royale'}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': '2009 Loseuteu maemorijeu', 'year': 2002}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Battle Royale II', 'year': 2003}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Moon Child', 'year': 2003}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Naechureol siti', 'year': 2003}
    {'year': 2011, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Real Steel'}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Category 7: The End of the World', 'year': 2005}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Battlestar Galactica: Razor', 'year': 2007}
    {'year': 2011, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Rise of the Planet of the Apes'}
    {'year': 2013, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Elysium'}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Lockout', 'year': 2012}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Lockout', 'year': 2012}
    {'year': 2013, 'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Snowpiercer'}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Dawn of the Planet of the Apes', 'year': 2014}
    {'genres': ['Action', 'Drama', 'Sci-Fi'], 'title': 'Young Ones', 'year': 2014}
    

**5. 정렬하기(sort), 앞쪽 일부 건너뛰기(skip), 갯수 제한하기(limit):**
- find() 에 붙여서, 별도 메서드로 사용


```python
for movie in movies.find().sort("imdb.rating", -1).skip(3).limit(3):  # -1은 내림차순을 의미합니다.
    print(movie)
```

    {'_id': ObjectId('573a13cff29313caabd88f5b'), 'plot': 'Three scouts, on the eve of their last camp-out, discover the true meaning of friendship when they attempt to save their town from a zombie outbreak.', 'genres': ['Comedy', 'Horror'], 'runtime': 93, 'rated': 'R', 'cast': ['Halston Sage', 'Tye Sheridan', 'Patrick Schwarzenegger', 'Cloris Leachman'], 'num_mflix_comments': 1, 'poster': 'https://m.media-amazon.com/images/M/MV5BMTY4NjczNjE4OV5BMl5BanBnXkFtZTgwODk0MjQ5NjE@._V1_SY1000_SX677_AL_.jpg', 'title': 'Scouts Guide to the Zombie Apocalypse', 'fullplot': 'Three scouts, on the eve of their last camp-out, discover the true meaning of friendship when they attempt to save their town from a zombie outbreak.', 'languages': ['English'], 'released': datetime.datetime(2015, 10, 30, 0, 0), 'directors': ['Christopher Landon'], 'writers': ['Emi Mochizuki (screenplay)', 'Carrie Lee Wilson (screenplay)', 'Christopher Landon (screenplay)', 'Lona Williams (screenplay)'], 'awards': {'wins': 0, 'nominations': 1, 'text': '1 nomination.'}, 'lastupdated': '2015-08-27 00:00:19.697000000', 'year': 2015, 'imdb': {'rating': '', 'votes': '', 'id': 1727776}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 2.8, 'numReviews': 91}, 'website': 'http://www.scoutsandzombiesmovie.com/', 'production': 'Paramount Pictures', 'lastUpdated': datetime.datetime(2015, 8, 30, 20, 13, 8)}}
    {'_id': ObjectId('573a13cef29313caabd86ddc'), 'plot': 'Through interwoven dramas spanning the U.S. and China, Catching the Sun explores the global economic race to lead the clean energy future.', 'genres': ['Documentary', 'Drama', 'History'], 'runtime': 75, 'title': 'Catching the Sun', 'num_mflix_comments': 3, 'countries': ['USA', 'China', 'Germany', 'India'], 'fullplot': 'Through interwoven dramas spanning the U.S. and China, Catching the Sun explores the global economic race to lead the clean energy future. Over the course of a solar jobs training program, Catching the Sun follows the hope and heartbreak of unemployed American workers seeking jobs in the solar industry. An unlikely ensemble of characters contrast with preconceived notions about who is at the forefront of a transition to clean energy. With countries like China investing in innovative technologies and capitalizing on this trillion-dollar opportunity, Catching the Sun tells the story of the global energy transition from the perspective of workers and entrepreneurs building solutions to income inequality and climate change with their own hands. Their successes and failures speak to one of the biggest questions of our time: will the U.S. actually be able to build a clean energy economy?', 'languages': ['English'], 'released': datetime.datetime(2015, 6, 1, 0, 0), 'directors': ['Shalini Kantayya'], 'writers': ['Shalini Kantayya'], 'awards': {'wins': 0, 'nominations': 1, 'text': '1 nomination.'}, 'lastupdated': '2015-08-26 01:30:44.587000000', 'year': 2015, 'imdb': {'rating': '', 'votes': '', 'id': 1698654}, 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.5, 'numReviews': 11}, 'website': 'http://www.sparrowfilm.com/', 'lastUpdated': datetime.datetime(2015, 6, 1, 18, 19, 5)}}
    {'_id': ObjectId('573a1393f29313caabcddbed'), 'countries': ['Spain'], 'genres': ['Drama'], 'runtime': 87, 'cast': ['Paola Barbara', 'Manuel Luna', 'Josè Nieto', 'Raquel Rodrigo'], 'num_mflix_comments': 3, 'title': 'La nao capitana', 'lastupdated': '2014-01-23 00:00:00', 'languages': ['Spanish'], 'released': datetime.datetime(1947, 9, 29, 0, 0), 'directors': ['Florièn Rey'], 'writers': ['Ricardo Baroja (novel)', 'Manuel Tamayo'], 'awards': {'wins': 2, 'nominations': 0, 'text': '2 wins.'}, 'year': 1947, 'imdb': {'rating': '', 'votes': '', 'id': 39653}, 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.4, 'numReviews': 67, 'meter': 67}, 'dvd': datetime.datetime(2000, 5, 9, 0, 0), 'lastUpdated': datetime.datetime(2015, 7, 1, 19, 30, 40)}}
    

**6. 정규표현식과 pymongo**

-  파이썬의 정규표현식 라이브러리인 `re` 모듈의 `compile` 함수를 사용하여 정규 표현식 객체를 생성하고,
- 이를 pymongo 에 적용할 수 있습니다.
- 예: re.I (IGNORECASE): 이 옵션은 대소문자를 구분하지 않는다는 것을 나타냅니다. 따라서 'Star', 'STAR', 'star', 'sTaR' 등을 모두 찾을 수 있습니다.


```python
import re
regex = re.compile('Star', re.I)  # 'Star'를 대소문자를 구분하지 않고 검색합니다.

for movie in movies.find({"title": regex}).limit(1):
    print(movie)
```

    {'_id': ObjectId('573a1392f29313caabcdbdd3'), 'plot': 'Davey Fenwick leaves his mining village on a university scholarship intent on returning to better support the miners against the owners. But he falls in love with Jenny who gets him to ...', 'genres': ['Drama'], 'runtime': 110, 'cast': ['Michael Redgrave', 'Margaret Lockwood', 'Emlyn Williams', 'Nancy Price'], 'num_mflix_comments': 1, 'poster': 'https://m.media-amazon.com/images/M/MV5BNzI0ODk3NzU4Nl5BMl5BanBnXkFtZTgwMTQ4ODgwMzE@._V1_SY1000_SX677_AL_.jpg', 'title': 'The Stars Look Down', 'fullplot': 'Davey Fenwick leaves his mining village on a university scholarship intent on returning to better support the miners against the owners. But he falls in love with Jenny who gets him to marry her and return home as local schoolteacher before finishing his degree. Davey finds he is ill-at-ease in his role, the more so when he realises Jenny still loves her former boyfriend. When he finds that his father and the other miners are going to have to continue working on a possibly deadly coal seam he decides to act.', 'languages': ['English'], 'released': datetime.datetime(1940, 9, 16, 0, 0), 'directors': ['Carol Reed'], 'writers': ['A.J. Cronin (from the book by)', 'J.B. Williams (screenplay)', 'A.J. Cronin (adaptation)', 'J.B. Williams (scenario)', 'A. Coppel (scenario)'], 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-09-02 00:42:27.583000000', 'year': 1940, 'imdb': {'rating': 7.2, 'votes': 634, 'id': 31976}, 'countries': ['UK'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.5, 'numReviews': 330, 'meter': 56}, 'fresh': 7, 'critic': {'rating': 7.8, 'numReviews': 8, 'meter': 88}, 'rotten': 1, 'lastUpdated': datetime.datetime(2015, 4, 30, 19, 14, 20)}}
    

- re 모듈 없이, 직접 정규표현식을 pymongo 에 사용할 수도 있음
- `$options`
   - `i`: 대소문자를 구분하지 않습니다. (re 라이브러리에서는 re.I)


```python
for movie in movies.find({"title": {"$regex": "star", "$options": 'i'}}).limit(1):
    print(movie)
```

    {'_id': ObjectId('573a1392f29313caabcdb497'), 'plot': 'A young woman comes to Hollywood with dreams of stardom, but achieves them only with the help of an alcoholic leading man whose best days are behind him.', 'genres': ['Drama'], 'runtime': 111, 'rated': 'NOT RATED', 'cast': ['Janet Gaynor', 'Fredric March', 'Adolphe Menjou', 'May Robson'], 'poster': 'https://m.media-amazon.com/images/M/MV5BMmE5ODI0NzMtYjc5Yy00MzMzLTk5OTQtN2Q3MzgwOTllMTY3XkEyXkFqcGdeQXVyNjc0MzMzNjA@._V1_SY1000_SX677_AL_.jpg', 'title': 'A Star Is Born', 'fullplot': 'Esther Blodgett is just another starry-eyed farm kid trying to break into the movies. Waitressing at a Hollywood party, she catches the eye of alcoholic star Norman Maine, is given a test, and is caught up in the Hollywood glamor machine (ruthlessly satirized). She and her idol Norman marry; but his career abruptly dwindles to nothing', 'languages': ['English'], 'released': datetime.datetime(1937, 4, 27, 0, 0), 'directors': ['William A. Wellman', 'Jack Conway'], 'writers': ['Dorothy Parker (screen play)', 'Alan Campbell (screen play)', 'Robert Carson (screen play)', 'William A. Wellman (from a story by)', 'Robert Carson (from a story by)'], 'awards': {'wins': 3, 'nominations': 7, 'text': 'Won 1 Oscar. Another 2 wins & 7 nominations.'}, 'lastupdated': '2015-09-01 00:55:54.333000000', 'year': 1937, 'imdb': {'rating': 7.7, 'votes': 5005, 'id': 29606}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'website': 'http://www.vcientertainment.com/Film-Categories?product_id=73', 'viewer': {'rating': 3.6, 'numReviews': 2526, 'meter': 79}, 'dvd': datetime.datetime(2004, 11, 16, 0, 0), 'critic': {'rating': 7.4, 'numReviews': 11, 'meter': 100}, 'lastUpdated': datetime.datetime(2015, 8, 26, 18, 58, 34), 'rotten': 0, 'production': 'Image Entertainment Inc.', 'fresh': 11}}
    

**7. distinct: 이 메소드는 특정 필드의 모든 고유한 값을 반환합니다.**


```python
distinct_genres = movies.distinct('genres')
print(distinct_genres)
```

    ['Action', 'Adventure', 'Animation', 'Biography', 'Comedy', 'Crime', 'Documentary', 'Drama', 'Family', 'Fantasy', 'Film-Noir', 'History', 'Horror', 'Music', 'Musical', 'Mystery', 'News', 'Romance', 'Sci-Fi', 'Short', 'Sport', 'Talk-Show', 'Thriller', 'War', 'Western']
    

**8. $in: 이 연산자는 필드 값이 특정 배열 내의 값 중 하나와 일치하는 문서를 선택합니다.**


```python
for movie in movies.find({'genres': {'$in': ['Action', 'Adventure']}}).limit(3):
    print(movie['genres'])
```

    ['Action']
    ['Action', 'Adventure', 'Crime']
    ['Comedy', 'Short', 'Action']
    

**9. $exists: 이 연산자는 특정 필드가 문서에 존재하는지 여부에 따라 문서를 선택합니다.**


```python
for movie in movies.find({'writers': {'$exists': False}}).limit(3):
    print(movie)
```

    {'_id': ObjectId('573a1390f29313caabcd4135'), 'plot': 'Three men hammer on an anvil and pass a bottle of beer around.', 'genres': ['Short'], 'runtime': 1, 'cast': ['Charles Kayser', 'John Ott'], 'num_mflix_comments': 1, 'title': 'Blacksmith Scene', 'fullplot': 'A stationary camera looks at a large anvil with a blacksmith behind it and one on either side. The smith in the middle draws a heated metal rod from the fire, places it on the anvil, and all three begin a rhythmic hammering. After several blows, the metal goes back in the fire. One smith pulls out a bottle of beer, and they each take a swig. Then, out comes the glowing metal and the hammering resumes.', 'countries': ['USA'], 'released': datetime.datetime(1893, 5, 9, 0, 0), 'directors': ['William K.L. Dickson'], 'rated': 'UNRATED', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-26 00:03:50.133000000', 'year': 1893, 'imdb': {'rating': 6.2, 'votes': 1189, 'id': 5}, 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.0, 'numReviews': 184, 'meter': 32}, 'lastUpdated': datetime.datetime(2015, 6, 28, 18, 34, 9)}}
    {'_id': ObjectId('573a1390f29313caabcd42e8'), 'plot': 'A group of bandits stage a brazen train hold-up, only to find a determined posse hot on their heels.', 'genres': ['Short', 'Western'], 'runtime': 11, 'cast': ['A.C. Abadie', "Gilbert M. 'Broncho Billy' Anderson", 'George Barnes', 'Justus D. Barnes'], 'poster': 'https://m.media-amazon.com/images/M/MV5BMTU3NjE5NzYtYTYyNS00MDVmLWIwYjgtMmYwYWIxZDYyNzU2XkEyXkFqcGdeQXVyNzQzNzQxNzI@._V1_SY1000_SX677_AL_.jpg', 'title': 'The Great Train Robbery', 'fullplot': "Among the earliest existing films in American cinema - notable as the first film that presented a narrative story to tell - it depicts a group of cowboy outlaws who hold up a train and rob the passengers. They are then pursued by a Sheriff's posse. Several scenes have color included - all hand tinted.", 'languages': ['English'], 'released': datetime.datetime(1903, 12, 1, 0, 0), 'directors': ['Edwin S. Porter'], 'rated': 'TV-G', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-13 00:27:59.177000000', 'year': 1903, 'imdb': {'rating': 7.4, 'votes': 9847, 'id': 439}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.7, 'numReviews': 2559, 'meter': 75}, 'fresh': 6, 'critic': {'rating': 7.6, 'numReviews': 6, 'meter': 100}, 'rotten': 0, 'lastUpdated': datetime.datetime(2015, 8, 8, 19, 16, 10)}}
    {'_id': ObjectId('573a1390f29313caabcd446f'), 'plot': "A greedy tycoon decides, on a whim, to corner the world market in wheat. This doubles the price of bread, forcing the grain's producers into charity lines and further into poverty. The film...", 'genres': ['Short', 'Drama'], 'runtime': 14, 'cast': ['Frank Powell', 'Grace Henderson', 'James Kirkwood', 'Linda Arvidson'], 'num_mflix_comments': 1, 'title': 'A Corner in Wheat', 'fullplot': "A greedy tycoon decides, on a whim, to corner the world market in wheat. This doubles the price of bread, forcing the grain's producers into charity lines and further into poverty. The film continues to contrast the ironic differences between the lives of those who work to grow the wheat and the life of the man who dabbles in its sale for profit.", 'languages': ['English'], 'released': datetime.datetime(1909, 12, 13, 0, 0), 'directors': ['D.W. Griffith'], 'rated': 'G', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-13 00:46:30.660000000', 'year': 1909, 'imdb': {'rating': 6.6, 'votes': 1375, 'id': 832}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.6, 'numReviews': 109, 'meter': 73}, 'lastUpdated': datetime.datetime(2015, 5, 11, 18, 36, 53)}}
    

**10. count_documents: 이 메소드는 쿼리에 일치하는 문서의 수를 반환합니다.**
- find() 대신에 count_documents() 메서드로 count 값을 얻을 수 있음

> find().count() 방식도 문서의 수를 세는 방법으로 사용할 수 있지만, 이 방식은 MongoDB 4.0 이후로 공식적으로 deprecated (사용이 권장되지 않는) 되었습니다.


```python
count = movies.count_documents({'genres': {'$in': ['Action', 'Adventure']}})
print(count)
```

    3805
    

### 3. 기본 pymongo 템플릿 코드(aggregation)
> sample_mflix 데이터셋을 기반으로, 지금까지 익힌 MongoDB aggregation 문법을 pymongo 에서 어떻게 적용해서 사용할 수 있는지를 알아보기로 함


```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용

db = client.sample_mflix
movies = db.movies
```

#### 다양한 aggregate() 문법 적용
- MongoDB aggregation 문법은 find() 가 아닌, aggregate() 메서드를 사용해야 함

**1. $match: 이 스테이지는 쿼리와 유사한 방식으로 문서를 필터링합니다.**

> 결과가 너무 많기 때문에, $limit 문법도 함께 사용하기로 함


```python
pipeline = [
    {"$match": {"genres": "Action"}}, { "$limit": 1 }
]
for movie in movies.aggregate(pipeline):
    print(movie)
```

    {'_id': ObjectId('573a1390f29313caabcd5293'), 'plot': "Young Pauline is left a lot of money when her wealthy uncle dies. However, her uncle's secretary has been named as her guardian until she marries, at which time she will officially take ...", 'genres': ['Action'], 'runtime': 199, 'cast': ['Pearl White', 'Crane Wilbur', 'Paul Panzer', 'Edward Josè'], 'num_mflix_comments': 1, 'poster': 'https://m.media-amazon.com/images/M/MV5BMzgxODk1Mzk2Ml5BMl5BanBnXkFtZTgwMDg0NzkwMjE@._V1_SY1000_SX677_AL_.jpg', 'title': 'The Perils of Pauline', 'fullplot': 'Young Pauline is left a lot of money when her wealthy uncle dies. However, her uncle\'s secretary has been named as her guardian until she marries, at which time she will officially take possession of her inheritance. Meanwhile, her "guardian" and his confederates constantly come up with schemes to get rid of Pauline so that he can get his hands on the money himself.', 'languages': ['English'], 'released': datetime.datetime(1914, 3, 23, 0, 0), 'directors': ['Louis J. Gasnier', 'Donald MacKenzie'], 'writers': ['Charles W. Goddard (screenplay)', 'Basil Dickey (screenplay)', 'Charles W. Goddard (novel)', 'George B. Seitz', 'Bertram Millhauser'], 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-09-12 00:01:18.647000000', 'year': 1914, 'imdb': {'rating': 7.6, 'votes': 744, 'id': 4465}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 2.8, 'numReviews': 9}, 'production': 'Pathè Frères', 'lastUpdated': datetime.datetime(2015, 9, 11, 17, 46, 19)}}
    

**2. $group: 이 스테이지는 특정 필드를 기준으로 문서를 그룹화하고, 각 그룹에 대해 다양한 연산을 수행할 수 있습니다.**


```python
# 영상 후반부에 왜 다음과 같이 수정하였는지도 설명을 드립니다.
pipeline = [
    {"$group": {"_id": "$directors", "count": {"$sum": 1}}}, { "$limit": 5 }
]
for group in movies.aggregate(pipeline):
    print(group)
```

    {'_id': ['Vikram Gandhi'], 'count': 1}
    {'_id': ['Olivier Coussemacq'], 'count': 1}
    {'_id': ['Marcelo Laffitte'], 'count': 1}
    {'_id': ['Wan Laiming'], 'count': 1}
    {'_id': ['Michael Hoffman'], 'count': 9}
    

**3. $sort: 이 스테이지는 특정 필드를 기준으로 문서를 정렬합니다.**


```python
pipeline = [
    {"$sort": {"title": 1}}, { "$limit": 3 }
]
for movie in movies.aggregate(pipeline):
    print(movie)
```

    {'_id': ObjectId('573a13def29313caabdb6863'), 'plot': "Set in the golden era of Grand Prix Racing '1' tells the story of a generation of charismatic drivers who raced on the edge, risking their lives during Formula 1's deadliest period, and the men who stood up and changed the sport forever.", 'genres': ['Documentary'], 'runtime': 112, 'cast': ['Michael Fassbender', 'Niki Lauda', 'Lewis Hamilton', 'Michael Schumacher'], 'num_mflix_comments': 1, 'poster': 'https://m.media-amazon.com/images/M/MV5BMjAxNDI5NTMxMF5BMl5BanBnXkFtZTgwMDMzMjg4MTE@._V1_SY1000_SX677_AL_.jpg', 'title': 1, 'fullplot': "Set in the golden era of Grand Prix Racing '1' tells the story of a generation of charismatic drivers who raced on the edge, risking their lives during Formula 1's deadliest period, and the men who stood up and changed the sport forever.", 'languages': ['English'], 'released': datetime.datetime(2013, 10, 1, 0, 0), 'directors': ['Paul Crowder'], 'writers': ['Mark Monroe'], 'awards': {'wins': 0, 'nominations': 1, 'text': '1 nomination.'}, 'lastupdated': '2015-09-06 00:03:18.180000000', 'year': 2013, 'imdb': {'rating': 8.0, 'votes': 2290, 'id': 2518788}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 4.1, 'numReviews': 260, 'meter': 85}, 'dvd': datetime.datetime(2014, 1, 28, 0, 0), 'website': 'http://www.facebook.com/1thefilm', 'production': 'Millennium Entertainment', 'lastUpdated': datetime.datetime(2015, 8, 24, 19, 11, 45)}}
    {'_id': ObjectId('573a13dcf29313caabdb2734'), 'plot': 'Three college friends hit the biggest party of the year, where a mysterious phenomenon disrupts the night, quickly descending into a chaos that challenges their friendships -- and whether they can stay alive.', 'genres': ['Sci-Fi', 'Thriller'], 'runtime': 95, 'metacritic': 60, 'rated': 'NOT RATED', 'cast': ['Rhys Wakefield', 'Logan Miller', 'Ashley Hinshaw', 'Natalie Hall'], 'poster': 'https://m.media-amazon.com/images/M/MV5BMTQwOTA5Mzc3Ml5BMl5BanBnXkFtZTgwOTkxODAxMDE@._V1_SY1000_SX677_AL_.jpg', 'title': 1, 'fullplot': 'Three college friends hit the biggest party of the year, where a mysterious phenomenon disrupts the night, quickly descending into a chaos that challenges their friendships -- and whether they can stay alive.', 'languages': ['English'], 'released': datetime.datetime(2013, 10, 24, 0, 0), 'directors': ['Dennis Iliadis'], 'writers': ['Dennis Iliadis (story)', 'Bill Gullo (screenplay)'], 'awards': {'wins': 0, 'nominations': 1, 'text': '1 nomination.'}, 'lastupdated': '2015-09-11 00:09:26.053000000', 'year': 2013, 'imdb': {'rating': 5.5, 'votes': 5626, 'id': 2395385}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'website': 'http://www.ifcfilms.com/films/1', 'viewer': {'rating': 3.0, 'numReviews': 1210, 'meter': 38}, 'dvd': datetime.datetime(2014, 1, 14, 0, 0), 'critic': {'rating': 6.7, 'numReviews': 11, 'meter': 73}, 'lastUpdated': datetime.datetime(2015, 9, 13, 17, 1, 24), 'rotten': 3, 'production': 'IFC Films', 'fresh': 8}}
    {'_id': ObjectId('573a13c9f29313caabd79051'), 'fullplot': 'A Berlin-set drama centered on a 40-something couple who, separately, fall in love with the same man.', 'imdb': {'rating': 6.8, 'votes': 3937, 'id': 1517177}, 'year': 2010, 'plot': 'A Berlin-set drama centered on a 40-something couple who, separately, fall in love with the same man.', 'genres': ['Comedy', 'Drama', 'Romance'], 'rated': 'UNRATED', 'metacritic': 55, 'title': 3, 'lastupdated': '2015-08-17 00:12:37.110000000', 'languages': ['German', 'English'], 'writers': ['Tom Tykwer'], 'type': 'movie', 'tomatoes': {'website': 'http://www.strandreleasing.com', 'viewer': {'rating': 3.3, 'numReviews': 1247, 'meter': 55}, 'dvd': datetime.datetime(2012, 2, 7, 0, 0), 'critic': {'rating': 5.8, 'numReviews': 31, 'meter': 45}, 'boxOffice': '$59.8k', 'rotten': 17, 'production': 'Strand Releasing', 'lastUpdated': datetime.datetime(2015, 8, 11, 19, 0, 6), 'fresh': 14}, 'poster': 'https://m.media-amazon.com/images/M/MV5BMTQwMDU5MTQ1MV5BMl5BanBnXkFtZTcwNTEzMzA1Ng@@._V1_SY1000_SX677_AL_.jpg', 'num_mflix_comments': 1, 'released': datetime.datetime(2010, 12, 23, 0, 0), 'awards': {'wins': 8, 'nominations': 11, 'text': '8 wins & 11 nominations.'}, 'countries': ['Germany'], 'cast': ['Sophie Rois', 'Sebastian Schipper', 'Devid Striesow', 'Angela Winkler'], 'directors': ['Tom Tykwer'], 'runtime': 119}
    

**4. $limit: 이 스테이지는 출력되는 문서의 수를 제한합니다.**


```python
pipeline = [
    {"$limit": 1}
]
for movie in movies.aggregate(pipeline):
    print(movie)
```

    {'_id': ObjectId('573a1390f29313caabcd4135'), 'plot': 'Three men hammer on an anvil and pass a bottle of beer around.', 'genres': ['Short'], 'runtime': 1, 'cast': ['Charles Kayser', 'John Ott'], 'num_mflix_comments': 1, 'title': 'Blacksmith Scene', 'fullplot': 'A stationary camera looks at a large anvil with a blacksmith behind it and one on either side. The smith in the middle draws a heated metal rod from the fire, places it on the anvil, and all three begin a rhythmic hammering. After several blows, the metal goes back in the fire. One smith pulls out a bottle of beer, and they each take a swig. Then, out comes the glowing metal and the hammering resumes.', 'countries': ['USA'], 'released': datetime.datetime(1893, 5, 9, 0, 0), 'directors': ['William K.L. Dickson'], 'rated': 'UNRATED', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-26 00:03:50.133000000', 'year': 1893, 'imdb': {'rating': 6.2, 'votes': 1189, 'id': 5}, 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.0, 'numReviews': 184, 'meter': 32}, 'lastUpdated': datetime.datetime(2015, 6, 28, 18, 34, 9)}}
    

**5. $project: 이 스테이지는 출력되는 문서의 필드를 추가, 제거, 또는 새로 생성합니다.**


```python
pipeline = [
    {"$project": {"_id": 0, "title": 1, "genres": 1}}, {"$limit": 1}
]
for movie in movies.aggregate(pipeline):
    print(movie)
```

    {'genres': ['Short'], 'title': 'Blacksmith Scene'}
    

**6. $unwind: 이 스테이지는 배열 필드를 풀어서 각 원소를 별도의 문서로 만듭니다.**


```python
pipeline = [
    {"$unwind": "$genres"}, {"$limit": 3}
]
for movie in movies.aggregate(pipeline):
    print(movie)
```

    {'_id': ObjectId('573a1390f29313caabcd4135'), 'plot': 'Three men hammer on an anvil and pass a bottle of beer around.', 'genres': 'Short', 'runtime': 1, 'cast': ['Charles Kayser', 'John Ott'], 'num_mflix_comments': 1, 'title': 'Blacksmith Scene', 'fullplot': 'A stationary camera looks at a large anvil with a blacksmith behind it and one on either side. The smith in the middle draws a heated metal rod from the fire, places it on the anvil, and all three begin a rhythmic hammering. After several blows, the metal goes back in the fire. One smith pulls out a bottle of beer, and they each take a swig. Then, out comes the glowing metal and the hammering resumes.', 'countries': ['USA'], 'released': datetime.datetime(1893, 5, 9, 0, 0), 'directors': ['William K.L. Dickson'], 'rated': 'UNRATED', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-26 00:03:50.133000000', 'year': 1893, 'imdb': {'rating': 6.2, 'votes': 1189, 'id': 5}, 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.0, 'numReviews': 184, 'meter': 32}, 'lastUpdated': datetime.datetime(2015, 6, 28, 18, 34, 9)}}
    {'_id': ObjectId('573a1390f29313caabcd42e8'), 'plot': 'A group of bandits stage a brazen train hold-up, only to find a determined posse hot on their heels.', 'genres': 'Short', 'runtime': 11, 'cast': ['A.C. Abadie', "Gilbert M. 'Broncho Billy' Anderson", 'George Barnes', 'Justus D. Barnes'], 'poster': 'https://m.media-amazon.com/images/M/MV5BMTU3NjE5NzYtYTYyNS00MDVmLWIwYjgtMmYwYWIxZDYyNzU2XkEyXkFqcGdeQXVyNzQzNzQxNzI@._V1_SY1000_SX677_AL_.jpg', 'title': 'The Great Train Robbery', 'fullplot': "Among the earliest existing films in American cinema - notable as the first film that presented a narrative story to tell - it depicts a group of cowboy outlaws who hold up a train and rob the passengers. They are then pursued by a Sheriff's posse. Several scenes have color included - all hand tinted.", 'languages': ['English'], 'released': datetime.datetime(1903, 12, 1, 0, 0), 'directors': ['Edwin S. Porter'], 'rated': 'TV-G', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-13 00:27:59.177000000', 'year': 1903, 'imdb': {'rating': 7.4, 'votes': 9847, 'id': 439}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.7, 'numReviews': 2559, 'meter': 75}, 'fresh': 6, 'critic': {'rating': 7.6, 'numReviews': 6, 'meter': 100}, 'rotten': 0, 'lastUpdated': datetime.datetime(2015, 8, 8, 19, 16, 10)}}
    {'_id': ObjectId('573a1390f29313caabcd42e8'), 'plot': 'A group of bandits stage a brazen train hold-up, only to find a determined posse hot on their heels.', 'genres': 'Western', 'runtime': 11, 'cast': ['A.C. Abadie', "Gilbert M. 'Broncho Billy' Anderson", 'George Barnes', 'Justus D. Barnes'], 'poster': 'https://m.media-amazon.com/images/M/MV5BMTU3NjE5NzYtYTYyNS00MDVmLWIwYjgtMmYwYWIxZDYyNzU2XkEyXkFqcGdeQXVyNzQzNzQxNzI@._V1_SY1000_SX677_AL_.jpg', 'title': 'The Great Train Robbery', 'fullplot': "Among the earliest existing films in American cinema - notable as the first film that presented a narrative story to tell - it depicts a group of cowboy outlaws who hold up a train and rob the passengers. They are then pursued by a Sheriff's posse. Several scenes have color included - all hand tinted.", 'languages': ['English'], 'released': datetime.datetime(1903, 12, 1, 0, 0), 'directors': ['Edwin S. Porter'], 'rated': 'TV-G', 'awards': {'wins': 1, 'nominations': 0, 'text': '1 win.'}, 'lastupdated': '2015-08-13 00:27:59.177000000', 'year': 1903, 'imdb': {'rating': 7.4, 'votes': 9847, 'id': 439}, 'countries': ['USA'], 'type': 'movie', 'tomatoes': {'viewer': {'rating': 3.7, 'numReviews': 2559, 'meter': 75}, 'fresh': 6, 'critic': {'rating': 7.6, 'numReviews': 6, 'meter': 100}, 'rotten': 0, 'lastUpdated': datetime.datetime(2015, 8, 8, 19, 16, 10)}}
    

**7. `$group`과 `$sum`: 이 예제에서는 감독별로 영화를 그룹화하고, 각 그룹의 영화 수를 계산합니다.**


```python
pipeline = [
    {"$group": {"_id": "$directors", "count": {"$sum": 1}}}, { "$limit": 5 }
]
for group in movies.aggregate(pipeline):
    print(group)
```

    {'_id': ['Gavin Millar'], 'count': 1}
    {'_id': ['Riccardo Milani'], 'count': 2}
    {'_id': ['Anne Bohlen', 'Kevin Rafferty', 'James Ridgeway'], 'count': 1}
    {'_id': ['Charles McDougall'], 'count': 2}
    {'_id': ['John Maybury'], 'count': 3}
    

**8. `$group`과 `$avg`: 이 예제에서는 감독별로 영화를 그룹화하고, 각 그룹의 영화 평점 평균을 계산합니다.**


```python
pipeline = [
    {"$group": {"_id": "$directors", "average_rating": {"$avg": "$imdb.rating"}}}, { "$limit": 5 }
]
for group in movies.aggregate(pipeline):
    print(group)
```

    {'_id': ['John Landis'], 'average_rating': 6.625}
    {'_id': ['Arthur Vincie'], 'average_rating': 5.5}
    {'_id': ['Ian Sharp'], 'average_rating': 6.5}
    {'_id': ['Pyotr Buslov'], 'average_rating': 6.866666666666667}
    {'_id': ['Billy Corben'], 'average_rating': 7.3}
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 컬렉션에 있는 영화의 수를 계산하세요.</font><br>
</div>


```python
movie_count = movies.count_documents({})
print('영화 수:', movie_count)
```

    영화 수: 23540
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 평균 영화 길이를 찾으세요.</font><br>
</div>


```python
average_length = list(movies.aggregate([{"$group": {"_id": None, "평균길이": {"$avg": "$runtime"}}}]))[0]
print('평균 영화 길이:', average_length['평균길이'])
```

    평균 영화 길이: 103.79006625384315
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 각 장르에 대한 영화 수를 계산하세요.</font><br>
</div>


```python
genre_counts = list(movies.aggregate([{"$unwind": "$genres"}, {"$group": {"_id": "$genres", "count": {"$sum": 1}}}]))
for genre in genre_counts:
    print('장르:', genre['_id'], '영화 수:', genre['count'])
```

    장르: Biography 영화 수: 1404
    장르: War 영화 수: 794
    장르: Mystery 영화 수: 1259
    장르: Documentary 영화 수: 2129
    장르: Fantasy 영화 수: 1153
    장르: Sport 영화 수: 390
    장르: Horror 영화 수: 1703
    장르: News 영화 수: 51
    장르: Animation 영화 수: 971
    장르: Adventure 영화 수: 2045
    장르: Western 영화 수: 274
    장르: Comedy 영화 수: 7024
    장르: Short 영화 수: 478
    장르: Crime 영화 수: 2678
    장르: Romance 영화 수: 3665
    장르: Music 영화 수: 840
    장르: Film-Noir 영화 수: 105
    장르: Talk-Show 영화 수: 1
    장르: Family 영화 수: 1311
    장르: Sci-Fi 영화 수: 1034
    장르: History 영화 수: 1000
    장르: Musical 영화 수: 487
    장르: Drama 영화 수: 13790
    장르: Action 영화 수: 2539
    장르: Thriller 영화 수: 2658
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 2015년 이후에 개봉한 영화를 제목으로 정렬하여 나열하세요.</font><br>
</div>


```python
post_2000_movies = movies.find({"year": {"$gt": 2015}}).sort("title")
for movie in post_2000_movies:
    print('영화 제목:', movie['title'])
```

    영화 제목: The Favourite
    영화 제목: The Masked Saint
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 가장 많은 영화를 제작하는 상위 5개 국가를 찾으세요.</font><br>
</div>


```python
top_countries = list(movies.aggregate([{"$unwind": "$countries"}, {"$group": {"_id": "$countries", "count": {"$sum": 1}}}, {"$sort": {"count": -1}}, {"$limit": 5}]))
for country in top_countries:
    print('국가:', country['_id'], '영화 수:', country['count'])
```

    국가: USA 영화 수: 11855
    국가: France 영화 수: 3093
    국가: UK 영화 수: 2904
    국가: Germany 영화 수: 1659
    국가: Italy 영화 수: 1388
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 2000년 이후 영화의 연도별 평균 IMDB 평점을 찾으세요.</font><br>
</div>


```python
average_ratings = movies.aggregate([
    { "$match": { "year": { "$gt": 2000 }}},
    { "$group": { "_id": "$year", "avgRating": { "$avg": "$imdb.rating"}}}
])
for rating in average_ratings:
    print ("년도:", str(rating['_id']) + ", 평균 평점:", rating["avgRating"])
```

    년도: 2015 평균 평점: 6.94197247706422
    년도: 2011 평균 평점: 6.491538461538461
    년도: 2013 평균 평점: 6.48876127973749
    년도: 2014 평균 평점: 6.5637478108581435
    년도: 2001 평균 평점: 6.584031007751937
    년도: 2016 평균 평점: None
    년도: 2018 평균 평점: None
    년도: 2002 평균 평점: 6.561679389312976
    년도: 2012 평균 평점: 6.478068592057761
    년도: 2007 평균 평점: 6.607224770642202
    년도: 2004 평균 평점: 6.648852901484481
    년도: 2009 평균 평점: 6.517979797979798
    년도: 2003 평균 평점: 6.577929984779299
    년도: 2010 평균 평점: 6.5279669762641905
    년도: 2006 평균 평점: 6.618364928909952
    년도: 2005 평균 평점: 6.591292875989446
    년도: 2008 평균 평점: 6.573243801652892
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제:  'Star'라는 단어가 포함된 영화의 제목을 가져오세요.</font><br>
</div>


```python
star_movies = movies.find({"title": {"$regex": ".*Star.*"}}, {"title": 1, "_id": 0})
for movie in star_movies:
    print('영화 제목:', movie['title'])
```

    영화 제목: A Star Is Born
    영화 제목: The Stars Look Down
    영화 제목: A Star Is Born
    영화 제목: The Tin Star
    영화 제목: It Started with a Kiss
    영화 제목: Stars
    영화 제목: It Started in Naples
    영화 제목: It Is Written in the Stars, Inspector Palmu
    영화 제목: Dog Star Man: Part IV
    영화 제목: Star!
    영화 제목: Start the Revolution Without Me
    영화 제목: Dark Star
    영화 제목: Stardust
    영화 제목: The Bingo Long Traveling All-Stars & Motor Kings
    영화 제목: A Star Is Born
    영화 제목: Star Wars: Episode IV - A New Hope
    영화 제목: Starcrash
    영화 제목: Starting Over
    영화 제목: Star Trek: The Motion Picture
    영화 제목: Battle Beyond the Stars
    영화 제목: Star Wars: Episode V - The Empire Strikes Back
    영화 제목: I'm Starting from Three
    영화 제목: Stardust Memories
    영화 제목: The Night of the Shooting Stars
    영화 제목: Star Trek II: The Wrath of Khan
    영화 제목: Starstruck
    영화 제목: Star Wars: Episode VI - Return of the Jedi
    영화 제목: Star 80
    영화 제목: The Last Starfighter
    영화 제목: Star Trek III: The Search for Spock
    영화 제목: Starman
    영화 제목: Hour of the Star
    영화 제목: Perry Mason: The Case of the Shooting Star
    영화 제목: Star Trek IV: The Voyage Home
    영화 제목: Stars and Bars
    영화 제목: Star Trek V: The Final Frontier
    영화 제목: Star Trek VI: The Undiscovered Country
    영화 제목: Star Trek: Generations
    영화 제목: Stargate
    영화 제목: The Star Maker
    영화 제목: The Evening Star
    영화 제목: How the War Started on My Island
    영화 제목: Lone Star
    영화 제목: Star Trek: First Contact
    영화 제목: Unhook the Stars
    영화 제목: Wish Upon a Star
    영화 제목: All Stars
    영화 제목: Starship Troopers
    영화 제목: Star Maps
    영화 제목: Star Trek: Insurrection
    영화 제목: Star Wars: Episode I - The Phantom Menace
    영화 제목: Star Wars: Episode III - Revenge of the Sith
    영화 제목: Star Wars: Episode II - Attack of the Clones
    영화 제목: Only Clouds Move the Stars
    영화 제목: The Book of Stars
    영화 제목: It All Starts Today
    영화 제목: Stardom
    영화 제목: Rock Star
    영화 제목: Starye klyachi
    영화 제목: Only Clouds Move the Stars
    영화 제목: Star Trek: Nemesis
    영화 제목: Startup.com
    영화 제목: Porn Star: The Legend of Ron Jeremy
    영화 제목: Star
    영화 제목: Dickie Roberts: Former Child Star
    영화 제목: The Star
    영화 제목: Starsky & Hutch
    영화 제목: And Starring Pancho Villa as Himself
    영화 제목: Starship Troopers 2: Hero of the Federation
    영화 제목: Star Runner
    영화 제목: Empire of Dreams: The Story of the 'Star Wars' Trilogy
    영화 제목: Laura's Star
    영화 제목: The Missing Star
    영화 제목: Starter for 10
    영화 제목: Under the Stars
    영화 제목: Stardust
    영화 제목: Refugee All Stars, Sierra Leone's
    영화 제목: Starting Out in the Evening
    영화 제목: Star Trek
    영화 제목: Bright Star
    영화 제목: Stargate: Continuum
    영화 제목: Like Stars on Earth
    영화 제목: 9 Star Hotel
    영화 제목: Robot Chicken: Star Wars
    영화 제목: Under the North Star
    영화 제목: Star Wars: The Clone Wars
    영화 제목: Starring Maja
    영화 제목: The Men Who Stare at Goats
    영화 제목: All Stars 2: Old Stars
    영화 제목: Afghan Star
    영화 제목: Grown Up Movie Star
    영화 제목: Star Trek Into Darkness
    영화 제목: Bucky Larson: Born to Be a Star
    영화 제목: Stargate SG-1: Children of the Gods - Final Cut
    영화 제목: Stark Raving Black
    영화 제목: Third Star
    영화 제목: StarStruck
    영화 제목: Man on a Mission: Richard Garriott's Road to the Stars
    영화 제목: All-Star Superman
    영화 제목: Position Among the Stars
    영화 제목: Starbuck
    영화 제목: Fullmetal Alchemist: The Sacred Star of Milos
    영화 제목: RockStar
    영화 제목: Starlet
    영화 제목: Starry Starry Night
    영화 제목: Starship Troopers: Invasion
    영화 제목: Stars Above
    영화 제목: Maps to the Stars
    영화 제목: A Five Star Life
    영화 제목: Five Star
    영화 제목: Twenty Feet from Stardom
    영화 제목: Starship: Rising
    영화 제목: Starred Up
    영화 제목: The Fault in Our Stars
    영화 제목: Starry Eyes
    영화 제목: All Stars
    영화 제목: Catch a Christmas Star
    영화 제목: Set Fire to the Stars
    영화 제목: Dark Star: H.R. Giger's World
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제:  데이터셋에서 사용 가능한 모든 고유 언어를 나열하세요.</font><br>
</div>


```python
distinct_languages = movies.distinct("languages")
print('사용 가능한 언어:', ', '.join(distinct_languages))
```

    사용 가능한 언어:  Ancient (to 1453),  Old, Abkhazian, Aboriginal, Acholi, Afrikaans, Aidoukrou, Albanian, Algonquin, American Sign Language, Amharic, Apache languages, Arabic, Aramaic, Arapaho, Armenian, Assamese, Assyrian Neo-Aramaic, Athapascan languages, Awadhi, Aymara, Azerbaijani, Balinese, Bambara, Basque, Belarusian, Bengali, Berber languages, Bhojpuri, Bosnian, Brazilian Sign Language, Breton, British Sign Language, Bulgarian, Burmese, Cantonese, Catalan, Chechen, Cheyenne, Chinese, Cornish, Corsican, Cree, Creole, Creoles and pidgins, Croatian, Crow, Czech, Danish, Dari, Dinka, Dutch, Dyula, Dzongkha, Eastern Frisian, Egyptian (Ancient), English, Esperanto, Estonian, Ewe, Faroese, Filipino, Finnish, Flemish, French, French Sign Language, Frisian, Fulah, Fur, Gallegan, Georgian, German, German Sign Language, Greek, Greenlandic, Guarani, Gujarati, Gumatj, Haitian, Hakka, Haryanvi, Hassanya, Hawaiian, Hebrew, Hindi, Hmong, Hokkien, Hungarian, Ibo, Icelandic, Indian Sign Language, Indonesian, Inuktitut, Inupiaq, Irish, Italian, Japanese, Japanese Sign Language, Jola-Fonyi, Kabuverdianu, Kabyle, Kannada, Karajè, Kazakh, Khmer, Kikuyu, Kinyarwanda, Kirghiz, Klingon, Konkani, Korean, Korean Sign Language, Kuna, Kurdish, Ladakhi, Ladino, Lao, Latin, Latvian, Lingala, Lithuanian, Low German, Luxembourgish, Macedonian, Malay, Malayalam, Malinka, Maltese, Mandarin, Manipuri, Maori, Mapudungun, Marathi, Mari, Masai, Maya, Mende, Middle English, Min Nan, Mohawk, Mongolian, More, Nahuatl, Nama, Navajo, Neapolitan, Nenets, Nepali, Norse, North American Indian, Norwegian, Nyaneka, Nyanja, Occitan, Old English, Oriya, Panjabi, Pawnee, Persian, Peul, Polish, Polynesian, Portuguese, Purepecha, Pushto, Quechua, Quenya, Rajasthani, Romanian, Romany, Russian, Russian Sign Language, Ryukyuan, Saami, Samoan, Sanskrit, Sardinian, Scanian, Scots, Scottish Gaelic, Serbian, Serbo-Croatian, Shanghainese, Shanxi, Shona, Shoshoni, Sicilian, Sign Languages, Sindarin, Sinhalese, Sioux, Slovak, Slovenian, Somali, Songhay, Southern Sotho, Spanish, Spanish Sign Language, Swahili, Swedish, Swiss German, Syriac, Tagalog, Tajik, Tamil, Tarahumara, Tatar, Telugu, Thai, Tibetan, Tigrigna, Tok Pisin, Tonga, Tswana, Tulu, Tupi, Turkish, Turkmen, Tuvinian, Tzotzil, Uighur, Ukrainian, Ungwatsi, Urdu, Uzbek, Vietnamese, Visayan, Washoe, Welsh, Wolof, Xhosa, Yiddish, Yoruba, Zulu
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제:  각각의 감독이 제작한 영화 수가 25개 이상인 감독들을 찾으세요.</font><br>
</div>


```python
director_counts = list(movies.aggregate([{"$unwind": "$directors"}, {"$group": {"_id": "$directors", "count": {"$sum": 1}}}, {"$match": {"count": {"$gte": 25}}}]))
for director in director_counts:
    print('감독:', director['_id'], '영화 수:', director['count'])
```

    감독: Takashi Miike 영화 수: 34
    감독: Martin Scorsese 영화 수: 32
    감독: Michael Winterbottom 영화 수: 26
    감독: Steven Soderbergh 영화 수: 28
    감독: Werner Herzog 영화 수: 33
    감독: Johnnie To 영화 수: 27
    감독: Clint Eastwood 영화 수: 27
    감독: William Wyler 영화 수: 26
    감독: Spike Lee 영화 수: 28
    감독: George Cukor 영화 수: 29
    감독: Steven Spielberg 영화 수: 29
    감독: Ken Loach 영화 수: 27
    감독: Robert Altman 영화 수: 28
    감독: Woody Allen 영화 수: 40
    감독: Mario Monicelli 영화 수: 29
    감독: Sidney Lumet 영화 수: 30
    감독: Jean-Luc Godard 영화 수: 27
    감독: Ridley Scott 영화 수: 25
    감독: Michael Apted 영화 수: 29
    감독: Ingmar Bergman 영화 수: 25
    감독: John Huston 영화 수: 34
    감독: Wim Wenders 영화 수: 27
    감독: John Ford 영화 수: 35
    감독: Alfred Hitchcock 영화 수: 31
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제:  관람객 평점을 기준으로 상위 5개의 영화를 찾으세요 (1000표 이상의 영화에 한함).</font><br>
</div>


```python
top_rated_movies = movies.find( { "imdb.votes": { "$gte": 1000} } ).sort("imdb.rating", -1).limit(5)
for movie in top_rated_movies:
    print ("영화 제목:", movie['title'], "평점:", movie['imdb']['rating'])
```

    영화 제목: Band of Brothers 평점: 9.6
    영화 제목: Planet Earth 평점: 9.5
    영화 제목: The Civil War 평점: 9.4
    영화 제목: The Civil War 평점: 9.4
    영화 제목: The Shawshank Redemption 평점: 9.3
    


## 인덱스

### 0. MongoDB 인덱스
- MongoDB 인덱스는 데이터베이스 성능 최적화를 위한 중요한 도구임  
- 인덱스는 특정 필드 또는 필드 세트에 대한 특정 정렬 순서를 유지하는 데이터 구조
- 이를 통해 데이터베이스 엔진이 특정 쿼리를 더 빠르게 처리할 수 있음

#### 인덱스의 중요성
- 데이터 셋이 클 경우, 전체 데이터베이스를 스캔하는 것은 매우 비효율적
- 이러한 상황에서 인덱스는 필요한 문서를 훨씬 더 빠르게 찾도록 도와줌
- 인덱스는 특정 필드의 값들을 정렬된 순서로 유지하여 해당 필드에 대한 쿼리가 빠르게 실행될 수 있도록 함
- 하지만 인덱스도 스토리지 공간을 차지하므로 적절히 사용해야 하므로, 불필요한 인덱스는 성능을 저하시킬 수 있음

> 읽기 작업이 많은 경우 인덱스는 유용하지만, 쓰기 작업이 많은 경우에는 수시로 인덱스까지 업데이트해야 하므로, 인덱스 오버헤드로 성능이 오히려 저하될 수 있음


#### MongoDB 인덱스 유형
- 단일 필드 인덱스: MongoDB에서, 사용자는 단일 필드의 값을 기반으로 인덱스를 생성할 수 있음
- 복합 인덱스: 두 개 이상의 필드를 기반으로 인덱스를 만들 수도 있습니다. 이를 복합 인덱스라고 함
- 다중키 인덱스: 배열 데이터를 색인화하기 위해 MongoDB는 다중키 인덱스를 사용함
- 지리 공간 인덱스: 지리적 위치 데이터를 기반으로 인덱스를 생성하는 것도 가능함
- 텍스트 인덱스: 텍스트 쿼리를 지원하기 위해 MongoDB는 텍스트 인덱스를 제공함

#### 주요 문법
- 인덱스 생성: db.collection.createIndex({ field: 1 })
- 인덱스 삭제: db.collection.dropIndex("indexName")
- 인덱스 리스트 조회: db.collection.getIndexes()
- 복합 인덱스 생성: db.collection.createIndex({ field1: 1, field2: -1 })
- 다중키 인덱스 생성: db.collection.createIndex({ fieldArray: 1 })
- 텍스트 인덱스 생성: db.collection.createIndex({ field: "text" })

### 1. MongoDB 인덱스 사용법 이해
- sample_mflix 데이터넷을 기반으로, 테스트를 통해 MongoDB 인덱스 사용법 이해

#### 기본 pymongo 템플릿 코드

```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용

db = client.sample_mflix
movies = db.movies
```

#### 단일 필드 인덱스 생성
- 영화의 제목(title)에 대한 인덱스 만들기 
- create_index 메서드는 인덱스 이름을 반환


```python
result = movies.create_index("title")
# result = movies.create_index([("title", 1)])
print(result)
```

#### 인덱스 리스트 조회
- 컬렉션에 있는 모든 인덱스 조회
- 결과로 반환되는 객체는 각 인덱스를 표현하는 키-값 쌍의 딕셔너리
- 인덱스 리스트 조회 결과 예
   - **\_id\_** : 이는 MongoDB가 자동으로 생성하는 기본 인덱스입니다. 모든 MongoDB 문서는 기본적으로 _id 필드를 가지며, 이 필드에는 각 문서의 고유 식별자가 저장됩니다.
   - **title_1** : 이는 사용자가 만든 사용자 정의 인덱스입니다. 이 경우에는 title 필드에 대한 인덱스입니다.
   - 각 키에는 또 다른 딕셔너리가 연결되어 있습니다. 이 내부 딕셔너리는 인덱스에 대한 자세한 정보를 제공합니다.
   - **v** : 이는 인덱스의 버전을 나타냅니다. MongoDB는 시간이 지남에 따라 인덱스의 내부 표현을 최적화하기 위해 인덱스 버전을 업데이트합니다. 여기서 '2'는 인덱스의 버전이 2라는 것을 나타냅니다.
   - **key** : 이는 인덱스의 키 패턴을 나타냅니다. 이는 인덱스가 어떤 필드에 대해 구축되었는지, 그리고 해당 필드가 오름차순(1) 또는 내림차순(-1)으로 정렬되었는지를 나타냅니다.
```python
{'_id_': {'v': 2, 'key': [('_id', 1)]}, 'title_1': {'v': 2, 'key': [('title', 1)]}}
```


```python
indices = movies.index_information()
print(indices)
```

#### 복합 인덱스 생성
- 복합 인덱스는 두 개 이상의 필드에 대한 인덱스
- 아래는 제목과 년도에 대한 복합 인덱스를 만드는 방법
- 복합 인덱스의 이름은 각 필드 이름과 정렬 순서(1 또는 -1)를 결합한 문자열임
  - 오름차순(1) 또는 내림차순(-1)
- 이 경우 'title_1_year_-1'이 출력됨


```python
result = movies.create_index([("title", 1), ("year", -1)])
print(result)
```

#### 다중키 인덱스 생성

- 배열 필드에 인덱스를 생성하면 MongoDB는 다중키 인덱스를 자동으로 생성
- cast 필드는 값이 배열임 


```python
pipeline = [
    { "$limit": 1 }
]
for movie in movies.aggregate(pipeline):
    print(movie['cast'])
```


```python
result = movies.create_index("cast")
print(result)
```

#### 텍스트 인덱스 생성

- 텍스트 인덱스는 문자열 콘텐츠를 검색하는 데 사용
- 영화의 개요(plot)를 검색하는 데 사용할 수 있는 텍스트 인덱스 생성 예
   - 텍스트 인덱스의 이름은 'plot_text'


```python
result = movies.create_index([("plot", "text")])
print(result)
```

#### 인덱스 삭제

- 더 이상 필요하지 않은 인덱스는 삭제
- 별도 리턴값은 없음 (없는 인덱스 삭제 시도시는 에러 발생)


```python
movies.drop_index("title_1")
```


```python
movies.drop_index("plot_text")
```

#### 모든 인덱스 삭제
- 모든 인덱스를 한 번에 삭제하는 drop_indexes()라는 메서드를 제공
- 단, MongoDB는 각 컬렉션의 _id 필드에 대한 인덱스를 자동으로 생성하며, 이 인덱스는 drop_indexes() 메서드로 삭제할 수 없음


```python
movies.drop_indexes()
```

#### MongoDB 인덱스의 가중치 사용
- MongoDB의 텍스트 인덱스는 가중치를 사용하여 특정 필드의 중요성을 강조할 수 있음
- 가중치는 각 필드에 대해 설정할 수 있으며, 이는 해당 필드에서 일치하는 결과의 적합성 점수에 영향을 미침
- 텍스트 인덱스의 각 필드에 가중치를 설정하면, 해당 필드에서 일치하는 텍스트는 가중치가 더 낮은 다른 필드에서 일치하는 텍스트보다 더 높은 점수를 받음
  - 즉, 일치 결과의 정렬에 큰 영향을 미침


```python
result = movies.create_index([("title", "text"), ("plot", "text")],
                             weights={'title': 5, 'plot': 1})
```

- 위 코드는 'title' 필드의 가중치를 5로, 'plot' 필드의 가중치를 1로 설정
- 이렇게 하면, 'title' 필드에서 일치하는 단어는 'plot' 필드에서 일치하는 단어보다 검색 결과의 순서에 더 큰 영향을 미치게 됨
- 가중치가 적용된 텍스트 인덱스를 사용하여 쿼리를 실행하면, 각 문서에는 적합성(유사도) 점수가 부여됨
- 이 점수는 MongoDB 에서 textScore 로 해당 점수를 관리하며, 해당 점수를 가져오거나, 사용하여 정렬하려면, $meta 연산자를 함께 사용해야 함
   - 다음 `{"score": {"$meta": "textScore"}}` 코드에서 `score`는 임의로 지정한 필드 이름, 이 필드는 각 document의 'textScore'를 저장하기 위해, `$meta` 연산자를 사용해야함 


```python
cursor = movies.find(
    {"$text": {"$search": "thriller"}},
    {"score": {"$meta": "textScore"}}).sort([("score", {"$meta": "textScore"})]).limit(5)

for doc in cursor:
    print(doc)
```

- 위 코드는 "thriller"를 검색하는 쿼리를 실행하고, 각 결과 문서에 적합성 점수를 부여함 
- 결과는 적합성 점수에 따라 정렬됨
- 'title' 필드에서 "thriller"와 일치하는 문서는 'plot' 필드에서 "thriller"와 일치하는 문서보다 더 높은 적합성 점수를 받게 되어, 검색 결과의 상단에 더 가까이 위치하게 됨
- `sort([("score", {"$meta": "textScore"})])` 는 오름차순으로 설정할 수 없음 (유사도가 높은 순으로 정렬하는 특수 기능)

#### 참고
- 위 코드에서 sort("score") 는 정상 동작하지 않는 이유
   - score 필드에 저장된 값이 textScore를 계산하기 위한 **`$meta` 연산자에 의해 동적으로 생성된 값**
   - **동적으로 계산된 값을 기준으로 정렬하려면 해당 값을 다시 계산하도록 MongoDB에게 명시적으로 지시해야 함**
      - 따라서, 정렬을 수행하려면 MongoDB에게 textScore 값을 다시 계산하도록 지시해야 함
      - 이런 동작 방식은 MongoDB의 sort() 메소드가 동적으로 계산된 값에 대해서는 기본적으로 재계산을 수행하지 않기 때문
      - 동적으로 계산된 값을 기준으로 정렬하려면 해당 값을 다시 계산하도록 MongoDB에게 명시적으로 지시해야 함
   - 이를 위해 `sort([("score", {"$meta": "textScore"})])` 와 같이 $meta 연산자를 sort() 메소드에도 전달해야 함
   - 이렇게 하면 MongoDB는 각 문서의 textScore 값을 계산하여 이를 기준으로 정렬을 수행하게 됨
   

### 2. MongoDB 텍스트 인덱스와 텍스트 검색
- 텍스트 검색을 위해서는 텍스트 인덱스가 필요함
- 다음 코드는 텍스트 인덱스가 없을 경우, 에러 발생

```python
cursor = movies.find({"$text": {"$search": "Jaws"}})
for doc in cursor:
    print(doc)
```

```bash
ERROR: text index required for $text query
```

#### 텍스트 검색 방법

- **1단계: 텍스트 인덱스 생성**


```python
result = movies.create_index([("title", "text")])
```

- **2단계: 텍스트 검색 쿼리 실행**

  - 텍스트 인덱스를 생성한 후에는 `$text` 연산자와 `$search` 필드를 사용하여 텍스트 검색 쿼리를 실행할 수 있음 
  - 다음은 title 필드에서 "Jaws"를 찾는 쿼리 예시임


```python
cursor = movies.find({"$text": {"$search": "Jaws"}})

for doc in cursor:
    print(doc)
```

- **3단계: 적합성 점수를 사용한 정렬**
   - 텍스트 검색 쿼리는 `$meta` 연산자를 사용하여 적합성 점수에 따라 결과를 정렬할 수 있음  
   - 적합성 점수는 각 문서가 검색 문자열과 얼마나 잘 일치하는지를 나타냄
   - 다음과 같이 적합성 점수를 계산하고 이를 기준으로 결과를 정렬할 수 있음
   
```bash
cursor = movies.find(
    {"$text": {"$search": "Jaws"}},
    {"score": {"$meta": "textScore"}}).sort([("score", {"$meta": "textScore"})])
```

- `$text` 연산자를 이용한 검색 쿼리는 각 문서에 대해 검색 문자열과의 일치도를 기반으로 적합성 점수를 계산함  
   - 적합성 점수는 문서가 검색 쿼리와 얼마나 잘 일치하는지를 나타내는 지표임 
   - 이 점수는 각 문서에 포함된 검색 문자열의 빈도, 위치 등 여러 요인을 고려하여 계산됨
- 적합성 점수는 `$meta` 연산자를 사용하여 조회할 수 있으며, 이 연산자는 'textScore'라는 특별한 메타데이터 필드에 이 점수를 저장함 
- 이 때, 'textScore'는 MongoDB가 내부적으로 적합성 점수를 저장하기 위해 사용하는 필드 이름임
```bash
{"score": {"$meta": "textScore"}}
```
- 위 코드는 검색 결과로 반환되는 각 문서에 적합성 점수를 추가하는 프로젝션임
- 'score'는 이 코드의 작성자가 적합성 점수를 저장하기 위해 선택한 임의의 필드 이름임  
- 이 이름은 원하는 대로 변경할 수 있음
```bash
.sort([("score", {"$meta": "textScore"})])
```
- 위 코드는 적합성 점수를 기준으로 검색 결과를 정렬하는 코드임 
- 이 코드는 'score' 필드에 저장된 적합성 점수를 기준으로 검색 결과를 내림차순으로 정렬함 
- 이 때도 'score'는 위에서 지정한 필드 이름과 동일해야 함


```python
cursor = movies.find(
    {"$text": {"$search": "Jaws"}},
    {"score": {"$meta": "textScore"}}).sort([("score", {"$meta": "textScore"})])

for doc in cursor:
    print(doc)
```


## 몽고DB와 파이썬 크롤링

### 파이썬 크롤링
> 데이터를 자동으로 저장하는 모습을 보여드리기 위해, 크롤링 기술을 가볍게 활용하기로 함 <br>
> 파이썬 입문과 크롤링 부트캠프에서 익힌 크롤링 기술을 활용하기로 함


```python
import requests
from bs4 import BeautifulSoup

for page_num in range(10):
    if page_num == 0:
        res = requests.get('https://davelee-fun.github.io/')
    else:
        res = requests.get('https://davelee-fun.github.io/page' + str(page_num + 1))
    soup = BeautifulSoup(res.content, 'html.parser')
    data = soup.select('div.card-body')
    for item in data:
        category = item.select_one('h2.card-title').get_text().replace('관련 상품 추천', '').strip()
        product = item.select_one('h4.card-text').get_text().replace('상품명:', '').strip()
        print (category, product)
```

    매트리스커버 보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루
    여름이불세트 슈에뜨룸 선인장 리플 침구 세트, 베이지
    행거도어 선우랜드 레인보우 2단 문걸이용 옷걸이 _중형, 화이트, 상세페이지참조
    매트리스커버 보드래 헬로우 누빔 매트리스커버, 핑크
    매트리스커버 보드래 퍼펙트 누빔 매트리스커버, 차콜
    매트리스커버 피아블 클래식 방수 매트리스커버, 화이트
    매트리스커버 더자리 에코항균 마이크로 매트리스커버, 밀키차콜그레이
    매트리스커버 더자리 프레쉬 퓨어 매트리스 커버, 퓨어 차콜그레이
    매트리스커버 몽쉐어 알러스킨 항균 매트리스 커버, 카키그레이
    매트리스커버 쿠팡 브랜드 - 코멧 홈 40수 트윌 순면 100% 홑겹 매트리스커버, 그레이
    매트리스커버 패브릭아트 항균 마이크로 원단 매트리스 커버, 아이보리
    매트리스커버 바숨 순면 누빔 침대 매트리스커버, 차콜
    행거도어 WEMAX 다용도 문옷걸이, 화이트, 1개
    매트리스커버 타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑
    매트리스커버 보몽드 순면스퀘어 누빔매트커버, 다크그레이
    매트리스커버 보드래 국내산 순면 60수 누빔 매트리스커버, 그레이
    매트리스커버 보드래 퍼펙트 누빔 매트리스커버, 베이지핑크
    매트리스커버 쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜
    매트리스커버 바숨 순면 누빔 침대 매트리스커버, 화이트
    매트리스커버 프랑떼 항균 방수 매트리스커버, 화이트
    매트리스커버 보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루
    매트리스커버 네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이
    매트리스커버 쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 베이지
    매트리스커버 타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독
    매트리스커버 더자리 에코항균 마이크로 매트리스커버, 밀키그레이
    매트리스커버 보몽드 순면스퀘어 누빔매트커버, 화이트
    매트리스커버 피아블 클래식 방수 매트리스커버, 화이트
    매트리스커버 쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 차콜그레이
    여름이불세트 쉬즈홈 모던그리드 순면 여름이불 베개커버 패드세트, 핑크
    여름이불세트 스코홈 빅리플 여름 차렵이불패드 3종 세트, 마린그레이
    여름이불세트 아망떼 시어서커 리플 홑이불 패드세트, 웨이크
    여름이불세트 마이센스 무더운 여름엔 시어서커 여름이불 패드 베개 이불세트 30종, 시어서커_파스텔그레이
    여름이불세트 믹스앤매치 로라 프릴 시어서커 침구세트, 그레이
    여름이불세트 에피소드1 샤베트 프릴 시어서커 여름이불패드세트, 그레이
    여름이불세트 슈에뜨룸 선인장 리플 침구 세트, 베이지
    여름이불세트 아망떼 시어서커 리플 홑이불 패드세트, 허브티
    여름이불세트 지베딩 아이스베어 시어서커 여름침구 풀세트, 민트그레이
    여름이불세트 쁘리엘르 테스 시어서커 여름이불 패드세트, 그레이
    여름이불세트 쉬즈홈 시어서커 홑이불 + 토퍼 + 베개커버 세트, 나나 옐로우
    여름이불세트 아망떼 시어서커 리플 퀼팅 이불패드세트, 리엔나
    여름이불세트 바자르 트로피컬 인견 여름 이불세트 인견이불 + 베개커버 2p + 인견패드, 그린
    여름이불세트 바자르 라이닝 혼방 인견 여름 이불베개세트 + 패드 Q, 쿨 네이비
    여름이불세트 슈에뜨룸 비숑 피치스킨 침구세트, 그레이
    여름이불세트 스코홈 시어서커 여름 이불 패드 3종 세트, 차콜
    여름이불세트 스코홈 어번시리즈 순면 차렵이불 누빔 매트커버세트 S 차콜
    여름이불세트 쉬즈홈 루즈 시어서커 차렵이불 패드세트, 그레이
    여름이불세트 예가로드 메리엘 시어서커 누비이불 패드세트, 블루
    여름이불세트 에피소드1 샤베트 프릴 시어서커 여름이불패드세트, 화이트
    여름이불세트 쉬즈홈 플루 시어서커 차렵이불 패드세트, 그린
    여름이불세트 메종 레이스 차렵 이불 세트, 블루
    여름이불세트 믹스앤매치 로라 프릴 시어서커 침구세트, 그린
    여름이불세트 슈에뜨룸 발그레 피치 리플 침구 세트, 혼합 색상
    여름이불세트 보몽드 메종 레이스 차렵이불 3종 세트, 민트
    여름이불세트 슈에뜨룸 체크 피치스킨 침구세트, 모카
    여름이불세트 메리엘 시어서커 에어리플 이불세트, 그레이
    여름이불세트 슈에뜨룸 빠삐용 시어서커 침구세트, 네이비
    여름이불세트 믹스앤매치 에이프릴 리플 누비이불 패드세트, 화이트
    여름이불세트 쉬즈홈 시어서커 홑이불 토퍼세트, 루즈 그레이
    행거도어 이코디 5단 엔틱 도어 행거, 브라운, 1개
    행거도어 선우랜드 우드볼 도어훅 4구, 실버, 1개
    행거도어 리은상점 다용도 도어훅 문걸이 행거 모자걸이 머플러 목도리 걸이, 화이트, 5개
    행거도어 퍼니스코 다용도걸이 모자걸이 가방걸이 도어훅 도어행거 문걸이, 엔틱브라운, 1세트
    행거도어 스텐 도어후크 옷걸이/도어훅 문옷걸이 행거 바지걸이, 혼합 색상, 1개
    행거도어 디비플러스 키펙스 컬러 폭조절 오버 도어훅, 블랙, 1개
    행거도어 리빙스토리 1+1 문에 거는 문 옷걸이 음자리 도어후크 방문 행거, 음자리도어후크-로즈골드, 2개
    행거도어 나이스후크 도어행거 2개 세트 (문행거), 블랙+화이트
    행거도어 리빙파이 도어훅 옷걸이 행거 7구, 블랙, 1개
    행거도어 선우랜드 우드볼 도어훅 10구, 실버, 1개
    행거도어 웰렉스 도어행거 MH1060 신형 본사직발송 미니건조대 도어옷걸이 도어훅, 고동색, 1개
    행거도어 엔비 엔틱 7구 도어훅 옷걸이, 도어훅 1+1, 1+1
    행거도어 코시나 무타공 문걸이 후크선반 1단, 화이트, 1개
    행거도어 코시나 무타공 올스텐 문걸이행거, 혼합 색상, 1개
    행거도어 [아트박스 POOM/이케아] ENUDDEN 도어 행거, 본품, 수량
    행거도어 비스비바 우드 폴 다용도걸이 3구, 혼합 색상, 1개
    행거도어 숲속애 웨이브 도어후크 5구, 블랙, 1개
    행거도어 펀타스틱 다용도 문틀걸이, 화이트, 1개
    행거도어 선우랜드 우드볼 도어훅 4구, 화이트, 1개
    행거도어 네이쳐리빙 어반모카 와이어 도어훅 옷걸이 6구, 단일 색상, 1개
    행거도어 까사마루 블랑 접이식 문걸이 건조대, 1개
    행거도어 선우랜드 우드볼 도어훅 6구, 실버, 1개
    행거도어 이케아 ENUDDEN 문걸이 행거 402.516.66, 화이트, 1개
    행거도어 선우랜드 우드볼 도어훅 10구, 화이트, 1개
    행거도어 코멧 홈 우드볼 도어행거, 6구, 혼합색상
    행거도어 선우랜드 레인보우 2단 문걸이용 옷걸이 _중형, 화이트, 상세페이지참조
    행거도어 코시나 무타공 문걸이 후크선반 2단, 화이트, 1개
    행거도어 스파이더락 도어후크 8구, 화이트, 1개
    행거도어 선우랜드 우드볼 도어훅 6구, 화이트, 1개
    행거도어 코멧 홈 우드볼 도어행거, 10구, 혼합색상
    매트리스커버 보드래 헬로우 누빔 매트리스커버, 핑크
    매트리스커버 보몽드 순면스퀘어 솔리드 누빔매트커버, 아이보리
    매트리스커버 더자리 에코항균 마이크로 매트리스커버, 밀키핑크
    매트리스커버 타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고
    매트리스커버 네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이
    매트리스커버 프로텍트어베드 베이직 매트리스 방수커버, 그레이
    

### Schema 구성 (필요 없음)

### 크롤링 + MongoDB 저장


```python
import requests
from bs4 import BeautifulSoup
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용
db = client['test'] # 'test' 데이터베이스 선택
collection = db.daveshop  # 'daveshop' 컬렉션 선택

for page_num in range(10):
    if page_num == 0:
        res = requests.get('https://davelee-fun.github.io/')
    else:
        res = requests.get('https://davelee-fun.github.io/page' + str(page_num + 1))
    soup = BeautifulSoup(res.content, 'html.parser')
    data = soup.select('div.card-body')
    for item in data:
        category = item.select_one('h2.card-title').get_text().replace('관련 상품 추천', '').strip()
        product = item.select_one('h4.card-text').get_text().replace('상품명:', '').strip()
        data = dict()
        data['category'] = category
        data['product'] = product
        collection.insert_one(data)
        
client.close()   
```

### MongoDB 데이터 읽기


```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용

db = client['test'] # 'test' 데이터베이스 선택
collection = db.daveshop  # 'daveshop' 컬렉션 선택

documents = collection.find()  # 'users' 컬렉션의 모든 문서 조회
for document in documents: # find() 의 결과는 iterable 객체이므로 반복문을 통해 각 데이터를 가져와야 함
    print(document)

# 연결 종료
client.close()
```

    {'_id': ObjectId('6497c5cb19ed0d022b1bb243'), 'category': '매트리스커버', 'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb244'), 'category': '여름이불세트', 'product': '슈에뜨룸 선인장 리플 침구 세트, 베이지'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb245'), 'category': '행거도어', 'product': '선우랜드 레인보우 2단 문걸이용 옷걸이 _중형, 화이트, 상세페이지참조'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb246'), 'category': '매트리스커버', 'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb247'), 'category': '매트리스커버', 'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb248'), 'category': '매트리스커버', 'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb249'), 'category': '매트리스커버', 'product': '더자리 에코항균 마이크로 매트리스커버, 밀키차콜그레이'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb24a'), 'category': '매트리스커버', 'product': '더자리 프레쉬 퓨어 매트리스 커버, 퓨어 차콜그레이'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb24b'), 'category': '매트리스커버', 'product': '몽쉐어 알러스킨 항균 매트리스 커버, 카키그레이'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb24c'), 'category': '매트리스커버', 'product': '쿠팡 브랜드 - 코멧 홈 40수 트윌 순면 100% 홑겹 매트리스커버, 그레이'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb24d'), 'category': '매트리스커버', 'product': '패브릭아트 항균 마이크로 원단 매트리스 커버, 아이보리'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb24e'), 'category': '매트리스커버', 'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb24f'), 'category': '행거도어', 'product': 'WEMAX 다용도 문옷걸이, 화이트, 1개'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb250'), 'category': '매트리스커버', 'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb251'), 'category': '매트리스커버', 'product': '보몽드 순면스퀘어 누빔매트커버, 다크그레이'}
    {'_id': ObjectId('6497c5cb19ed0d022b1bb252'), 'category': '매트리스커버', 'product': '보드래 국내산 순면 60수 누빔 매트리스커버, 그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb253'), 'category': '매트리스커버', 'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb254'), 'category': '매트리스커버', 'product': '쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb255'), 'category': '매트리스커버', 'product': '바숨 순면 누빔 침대 매트리스커버, 화이트'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb256'), 'category': '매트리스커버', 'product': '프랑떼 항균 방수 매트리스커버, 화이트'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb257'), 'category': '매트리스커버', 'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb258'), 'category': '매트리스커버', 'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb259'), 'category': '매트리스커버', 'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 베이지'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb25a'), 'category': '매트리스커버', 'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb25b'), 'category': '매트리스커버', 'product': '더자리 에코항균 마이크로 매트리스커버, 밀키그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb25c'), 'category': '매트리스커버', 'product': '보몽드 순면스퀘어 누빔매트커버, 화이트'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb25d'), 'category': '매트리스커버', 'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb25e'), 'category': '매트리스커버', 'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 차콜그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb25f'), 'category': '여름이불세트', 'product': '쉬즈홈 모던그리드 순면 여름이불 베개커버 패드세트, 핑크'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb260'), 'category': '여름이불세트', 'product': '스코홈 빅리플 여름 차렵이불패드 3종 세트, 마린그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb261'), 'category': '여름이불세트', 'product': '아망떼 시어서커 리플 홑이불 패드세트, 웨이크'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb262'), 'category': '여름이불세트', 'product': '마이센스 무더운 여름엔 시어서커 여름이불 패드 베개 이불세트 30종, 시어서커_파스텔그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb263'), 'category': '여름이불세트', 'product': '믹스앤매치 로라 프릴 시어서커 침구세트, 그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb264'), 'category': '여름이불세트', 'product': '에피소드1 샤베트 프릴 시어서커 여름이불패드세트, 그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb265'), 'category': '여름이불세트', 'product': '슈에뜨룸 선인장 리플 침구 세트, 베이지'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb266'), 'category': '여름이불세트', 'product': '아망떼 시어서커 리플 홑이불 패드세트, 허브티'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb267'), 'category': '여름이불세트', 'product': '지베딩 아이스베어 시어서커 여름침구 풀세트, 민트그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb268'), 'category': '여름이불세트', 'product': '쁘리엘르 테스 시어서커 여름이불 패드세트, 그레이'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb269'), 'category': '여름이불세트', 'product': '쉬즈홈 시어서커 홑이불 + 토퍼 + 베개커버 세트, 나나 옐로우'}
    {'_id': ObjectId('6497c5cc19ed0d022b1bb26a'), 'category': '여름이불세트', 'product': '아망떼 시어서커 리플 퀼팅 이불패드세트, 리엔나'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb26b'), 'category': '여름이불세트', 'product': '바자르 트로피컬 인견 여름 이불세트 인견이불 + 베개커버 2p + 인견패드, 그린'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb26c'), 'category': '여름이불세트', 'product': '바자르 라이닝 혼방 인견 여름 이불베개세트 + 패드 Q, 쿨 네이비'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb26d'), 'category': '여름이불세트', 'product': '슈에뜨룸 비숑 피치스킨 침구세트, 그레이'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb26e'), 'category': '여름이불세트', 'product': '스코홈 시어서커 여름 이불 패드 3종 세트, 차콜'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb26f'), 'category': '여름이불세트', 'product': '스코홈 어번시리즈 순면 차렵이불 누빔 매트커버세트 S 차콜'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb270'), 'category': '여름이불세트', 'product': '쉬즈홈 루즈 시어서커 차렵이불 패드세트, 그레이'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb271'), 'category': '여름이불세트', 'product': '예가로드 메리엘 시어서커 누비이불 패드세트, 블루'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb272'), 'category': '여름이불세트', 'product': '에피소드1 샤베트 프릴 시어서커 여름이불패드세트, 화이트'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb273'), 'category': '여름이불세트', 'product': '쉬즈홈 플루 시어서커 차렵이불 패드세트, 그린'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb274'), 'category': '여름이불세트', 'product': '메종 레이스 차렵 이불 세트, 블루'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb275'), 'category': '여름이불세트', 'product': '믹스앤매치 로라 프릴 시어서커 침구세트, 그린'}
    {'_id': ObjectId('6497c5cd19ed0d022b1bb276'), 'category': '여름이불세트', 'product': '슈에뜨룸 발그레 피치 리플 침구 세트, 혼합 색상'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb277'), 'category': '여름이불세트', 'product': '보몽드 메종 레이스 차렵이불 3종 세트, 민트'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb278'), 'category': '여름이불세트', 'product': '슈에뜨룸 체크 피치스킨 침구세트, 모카'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb279'), 'category': '여름이불세트', 'product': '메리엘 시어서커 에어리플 이불세트, 그레이'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb27a'), 'category': '여름이불세트', 'product': '슈에뜨룸 빠삐용 시어서커 침구세트, 네이비'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb27b'), 'category': '여름이불세트', 'product': '믹스앤매치 에이프릴 리플 누비이불 패드세트, 화이트'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb27c'), 'category': '여름이불세트', 'product': '쉬즈홈 시어서커 홑이불 토퍼세트, 루즈 그레이'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb27d'), 'category': '행거도어', 'product': '이코디 5단 엔틱 도어 행거, 브라운, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb27e'), 'category': '행거도어', 'product': '선우랜드 우드볼 도어훅 4구, 실버, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb27f'), 'category': '행거도어', 'product': '리은상점 다용도 도어훅 문걸이 행거 모자걸이 머플러 목도리 걸이, 화이트, 5개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb280'), 'category': '행거도어', 'product': '퍼니스코 다용도걸이 모자걸이 가방걸이 도어훅 도어행거 문걸이, 엔틱브라운, 1세트'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb281'), 'category': '행거도어', 'product': '스텐 도어후크 옷걸이/도어훅 문옷걸이 행거 바지걸이, 혼합 색상, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb282'), 'category': '행거도어', 'product': '디비플러스 키펙스 컬러 폭조절 오버 도어훅, 블랙, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb283'), 'category': '행거도어', 'product': '리빙스토리 1+1 문에 거는 문 옷걸이 음자리 도어후크 방문 행거, 음자리도어후크-로즈골드, 2개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb284'), 'category': '행거도어', 'product': '나이스후크 도어행거 2개 세트 (문행거), 블랙+화이트'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb285'), 'category': '행거도어', 'product': '리빙파이 도어훅 옷걸이 행거 7구, 블랙, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb286'), 'category': '행거도어', 'product': '선우랜드 우드볼 도어훅 10구, 실버, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb287'), 'category': '행거도어', 'product': '웰렉스 도어행거 MH1060 신형 본사직발송 미니건조대 도어옷걸이 도어훅, 고동색, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb288'), 'category': '행거도어', 'product': '엔비 엔틱 7구 도어훅 옷걸이, 도어훅 1+1, 1+1'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb289'), 'category': '행거도어', 'product': '코시나 무타공 문걸이 후크선반 1단, 화이트, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb28a'), 'category': '행거도어', 'product': '코시나 무타공 올스텐 문걸이행거, 혼합 색상, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb28b'), 'category': '행거도어', 'product': '[아트박스 POOM/이케아] ENUDDEN 도어 행거, 본품, 수량'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb28c'), 'category': '행거도어', 'product': '비스비바 우드 폴 다용도걸이 3구, 혼합 색상, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb28d'), 'category': '행거도어', 'product': '숲속애 웨이브 도어후크 5구, 블랙, 1개'}
    {'_id': ObjectId('6497c5ce19ed0d022b1bb28e'), 'category': '행거도어', 'product': '펀타스틱 다용도 문틀걸이, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb28f'), 'category': '행거도어', 'product': '선우랜드 우드볼 도어훅 4구, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb290'), 'category': '행거도어', 'product': '네이쳐리빙 어반모카 와이어 도어훅 옷걸이 6구, 단일 색상, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb291'), 'category': '행거도어', 'product': '까사마루 블랑 접이식 문걸이 건조대, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb292'), 'category': '행거도어', 'product': '선우랜드 우드볼 도어훅 6구, 실버, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb293'), 'category': '행거도어', 'product': '이케아 ENUDDEN 문걸이 행거 402.516.66, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb294'), 'category': '행거도어', 'product': '선우랜드 우드볼 도어훅 10구, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb295'), 'category': '행거도어', 'product': '코멧 홈 우드볼 도어행거, 6구, 혼합색상'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb296'), 'category': '행거도어', 'product': '선우랜드 레인보우 2단 문걸이용 옷걸이 _중형, 화이트, 상세페이지참조'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb297'), 'category': '행거도어', 'product': '코시나 무타공 문걸이 후크선반 2단, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb298'), 'category': '행거도어', 'product': '스파이더락 도어후크 8구, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb299'), 'category': '행거도어', 'product': '선우랜드 우드볼 도어훅 6구, 화이트, 1개'}
    {'_id': ObjectId('6497c5cf19ed0d022b1bb29a'), 'category': '행거도어', 'product': '코멧 홈 우드볼 도어행거, 10구, 혼합색상'}
    {'_id': ObjectId('6497c5d019ed0d022b1bb29b'), 'category': '매트리스커버', 'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'_id': ObjectId('6497c5d019ed0d022b1bb29c'), 'category': '매트리스커버', 'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 아이보리'}
    {'_id': ObjectId('6497c5d019ed0d022b1bb29d'), 'category': '매트리스커버', 'product': '더자리 에코항균 마이크로 매트리스커버, 밀키핑크'}
    {'_id': ObjectId('6497c5d019ed0d022b1bb29e'), 'category': '매트리스커버', 'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고'}
    {'_id': ObjectId('6497c5d019ed0d022b1bb29f'), 'category': '매트리스커버', 'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'_id': ObjectId('6497c5d019ed0d022b1bb2a0'), 'category': '매트리스커버', 'product': '프로텍트어베드 베이직 매트리스 방수커버, 그레이'}
    

### 연습문제를 위한 사전 준비


```python
from pymongo import MongoClient

# MongoDB에 연결 (인증 미필요시)
client = MongoClient("mongodb://localhost:27017")
# client = MongoClient("mongodb://username:password@localhost:27017")
# 인증이 필요하지 않은 경우 위의 첫 번째 줄 사용, 인증이 필요한 경우 두 번째 줄 사용

db = client['test'] # 'test' 데이터베이스 선택
collection = db.daveshop  # 'daveshop' 컬렉션 선택
```

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 'category' 필드에 있는 모든 카테고리 종류를 조회하세요</font><br>
</div>


```python
categories = collection.distinct("category")
print(categories)
```

    ['매트리스커버', '여름이불세트', '행거도어']
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 모든 상품(product)을 조회하세요</font><br>
</div>


```python
for product in collection.find({}, {"_id": 0, "product": 1}):
    print(product)
```

    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'product': '슈에뜨룸 선인장 리플 침구 세트, 베이지'}
    {'product': '선우랜드 레인보우 2단 문걸이용 옷걸이 _중형, 화이트, 상세페이지참조'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키차콜그레이'}
    {'product': '더자리 프레쉬 퓨어 매트리스 커버, 퓨어 차콜그레이'}
    {'product': '몽쉐어 알러스킨 항균 매트리스 커버, 카키그레이'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 트윌 순면 100% 홑겹 매트리스커버, 그레이'}
    {'product': '패브릭아트 항균 마이크로 원단 매트리스 커버, 아이보리'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'product': 'WEMAX 다용도 문옷걸이, 화이트, 1개'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑'}
    {'product': '보몽드 순면스퀘어 누빔매트커버, 다크그레이'}
    {'product': '보드래 국내산 순면 60수 누빔 매트리스커버, 그레이'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 화이트'}
    {'product': '프랑떼 항균 방수 매트리스커버, 화이트'}
    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 베이지'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키그레이'}
    {'product': '보몽드 순면스퀘어 누빔매트커버, 화이트'}
    {'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 차콜그레이'}
    {'product': '쉬즈홈 모던그리드 순면 여름이불 베개커버 패드세트, 핑크'}
    {'product': '스코홈 빅리플 여름 차렵이불패드 3종 세트, 마린그레이'}
    {'product': '아망떼 시어서커 리플 홑이불 패드세트, 웨이크'}
    {'product': '마이센스 무더운 여름엔 시어서커 여름이불 패드 베개 이불세트 30종, 시어서커_파스텔그레이'}
    {'product': '믹스앤매치 로라 프릴 시어서커 침구세트, 그레이'}
    {'product': '에피소드1 샤베트 프릴 시어서커 여름이불패드세트, 그레이'}
    {'product': '슈에뜨룸 선인장 리플 침구 세트, 베이지'}
    {'product': '아망떼 시어서커 리플 홑이불 패드세트, 허브티'}
    {'product': '지베딩 아이스베어 시어서커 여름침구 풀세트, 민트그레이'}
    {'product': '쁘리엘르 테스 시어서커 여름이불 패드세트, 그레이'}
    {'product': '쉬즈홈 시어서커 홑이불 + 토퍼 + 베개커버 세트, 나나 옐로우'}
    {'product': '아망떼 시어서커 리플 퀼팅 이불패드세트, 리엔나'}
    {'product': '바자르 트로피컬 인견 여름 이불세트 인견이불 + 베개커버 2p + 인견패드, 그린'}
    {'product': '바자르 라이닝 혼방 인견 여름 이불베개세트 + 패드 Q, 쿨 네이비'}
    {'product': '슈에뜨룸 비숑 피치스킨 침구세트, 그레이'}
    {'product': '스코홈 시어서커 여름 이불 패드 3종 세트, 차콜'}
    {'product': '스코홈 어번시리즈 순면 차렵이불 누빔 매트커버세트 S 차콜'}
    {'product': '쉬즈홈 루즈 시어서커 차렵이불 패드세트, 그레이'}
    {'product': '예가로드 메리엘 시어서커 누비이불 패드세트, 블루'}
    {'product': '에피소드1 샤베트 프릴 시어서커 여름이불패드세트, 화이트'}
    {'product': '쉬즈홈 플루 시어서커 차렵이불 패드세트, 그린'}
    {'product': '메종 레이스 차렵 이불 세트, 블루'}
    {'product': '믹스앤매치 로라 프릴 시어서커 침구세트, 그린'}
    {'product': '슈에뜨룸 발그레 피치 리플 침구 세트, 혼합 색상'}
    {'product': '보몽드 메종 레이스 차렵이불 3종 세트, 민트'}
    {'product': '슈에뜨룸 체크 피치스킨 침구세트, 모카'}
    {'product': '메리엘 시어서커 에어리플 이불세트, 그레이'}
    {'product': '슈에뜨룸 빠삐용 시어서커 침구세트, 네이비'}
    {'product': '믹스앤매치 에이프릴 리플 누비이불 패드세트, 화이트'}
    {'product': '쉬즈홈 시어서커 홑이불 토퍼세트, 루즈 그레이'}
    {'product': '이코디 5단 엔틱 도어 행거, 브라운, 1개'}
    {'product': '선우랜드 우드볼 도어훅 4구, 실버, 1개'}
    {'product': '리은상점 다용도 도어훅 문걸이 행거 모자걸이 머플러 목도리 걸이, 화이트, 5개'}
    {'product': '퍼니스코 다용도걸이 모자걸이 가방걸이 도어훅 도어행거 문걸이, 엔틱브라운, 1세트'}
    {'product': '스텐 도어후크 옷걸이/도어훅 문옷걸이 행거 바지걸이, 혼합 색상, 1개'}
    {'product': '디비플러스 키펙스 컬러 폭조절 오버 도어훅, 블랙, 1개'}
    {'product': '리빙스토리 1+1 문에 거는 문 옷걸이 음자리 도어후크 방문 행거, 음자리도어후크-로즈골드, 2개'}
    {'product': '나이스후크 도어행거 2개 세트 (문행거), 블랙+화이트'}
    {'product': '리빙파이 도어훅 옷걸이 행거 7구, 블랙, 1개'}
    {'product': '선우랜드 우드볼 도어훅 10구, 실버, 1개'}
    {'product': '웰렉스 도어행거 MH1060 신형 본사직발송 미니건조대 도어옷걸이 도어훅, 고동색, 1개'}
    {'product': '엔비 엔틱 7구 도어훅 옷걸이, 도어훅 1+1, 1+1'}
    {'product': '코시나 무타공 문걸이 후크선반 1단, 화이트, 1개'}
    {'product': '코시나 무타공 올스텐 문걸이행거, 혼합 색상, 1개'}
    {'product': '[아트박스 POOM/이케아] ENUDDEN 도어 행거, 본품, 수량'}
    {'product': '비스비바 우드 폴 다용도걸이 3구, 혼합 색상, 1개'}
    {'product': '숲속애 웨이브 도어후크 5구, 블랙, 1개'}
    {'product': '펀타스틱 다용도 문틀걸이, 화이트, 1개'}
    {'product': '선우랜드 우드볼 도어훅 4구, 화이트, 1개'}
    {'product': '네이쳐리빙 어반모카 와이어 도어훅 옷걸이 6구, 단일 색상, 1개'}
    {'product': '까사마루 블랑 접이식 문걸이 건조대, 1개'}
    {'product': '선우랜드 우드볼 도어훅 6구, 실버, 1개'}
    {'product': '이케아 ENUDDEN 문걸이 행거 402.516.66, 화이트, 1개'}
    {'product': '선우랜드 우드볼 도어훅 10구, 화이트, 1개'}
    {'product': '코멧 홈 우드볼 도어행거, 6구, 혼합색상'}
    {'product': '선우랜드 레인보우 2단 문걸이용 옷걸이 _중형, 화이트, 상세페이지참조'}
    {'product': '코시나 무타공 문걸이 후크선반 2단, 화이트, 1개'}
    {'product': '스파이더락 도어후크 8구, 화이트, 1개'}
    {'product': '선우랜드 우드볼 도어훅 6구, 화이트, 1개'}
    {'product': '코멧 홈 우드볼 도어행거, 10구, 혼합색상'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 아이보리'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키핑크'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고'}
    {'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'product': '프로텍트어베드 베이직 매트리스 방수커버, 그레이'}
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: "매트리스커버" 카테고리의 모든 상품을 조회하세요<br> (find 와 aggregation 을 사용한 코드를 각각 작성해주세요)</font><br>
</div>


```python
for product in collection.find({"category": "매트리스커버"}, {"_id": 0, "product": 1}):
    print(product)
```

    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키차콜그레이'}
    {'product': '더자리 프레쉬 퓨어 매트리스 커버, 퓨어 차콜그레이'}
    {'product': '몽쉐어 알러스킨 항균 매트리스 커버, 카키그레이'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 트윌 순면 100% 홑겹 매트리스커버, 그레이'}
    {'product': '패브릭아트 항균 마이크로 원단 매트리스 커버, 아이보리'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑'}
    {'product': '보몽드 순면스퀘어 누빔매트커버, 다크그레이'}
    {'product': '보드래 국내산 순면 60수 누빔 매트리스커버, 그레이'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 화이트'}
    {'product': '프랑떼 항균 방수 매트리스커버, 화이트'}
    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 베이지'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키그레이'}
    {'product': '보몽드 순면스퀘어 누빔매트커버, 화이트'}
    {'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 차콜그레이'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 아이보리'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키핑크'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고'}
    {'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'product': '프로텍트어베드 베이직 매트리스 방수커버, 그레이'}
    


```python
pipeline = [
    {"$match": {"category": "매트리스커버"}},
    {"$project": {"_id": 0, "product": 1}}
]

result = list(collection.aggregate(pipeline))
for product in result:
    print(product)
```

    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키차콜그레이'}
    {'product': '더자리 프레쉬 퓨어 매트리스 커버, 퓨어 차콜그레이'}
    {'product': '몽쉐어 알러스킨 항균 매트리스 커버, 카키그레이'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 트윌 순면 100% 홑겹 매트리스커버, 그레이'}
    {'product': '패브릭아트 항균 마이크로 원단 매트리스 커버, 아이보리'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑'}
    {'product': '보몽드 순면스퀘어 누빔매트커버, 다크그레이'}
    {'product': '보드래 국내산 순면 60수 누빔 매트리스커버, 그레이'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 화이트'}
    {'product': '프랑떼 항균 방수 매트리스커버, 화이트'}
    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 다크블루'}
    {'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 베이지'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키그레이'}
    {'product': '보몽드 순면스퀘어 누빔매트커버, 화이트'}
    {'product': '피아블 클래식 방수 매트리스커버, 화이트'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 차콜그레이'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보몽드 순면스퀘어 솔리드 누빔매트커버, 아이보리'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키핑크'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고'}
    {'product': '네이쳐리빙 피아블 클래식 방수 매트리스커버, 그레이'}
    {'product': '프로텍트어베드 베이직 매트리스 방수커버, 그레이'}
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 각 카테고리별 상품 수를 조회하세요. 이를 위해 MongoDB의 aggregation 기능을 사용하세요</font><br>
</div>


```python
pipeline = [
    {"$group": { "_id": "$category", "count": { "$sum": 1} } },
    { "$project": { "_id": 0, "category": "$_id", "count": 1} }
]
for category_count in collection.aggregate(pipeline):
    print(category_count['category'] + ", count:", category_count['count'])
```

    {'_id': '여름이불세트', 'count': 31}
    {'_id': '매트리스커버', 'count': 31}
    {'_id': '행거도어', 'count': 32}
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 상품명(product)에 '핑크'가 포함된 모든 상품을 조회하세요</font><br>
</div>


```python
for product in collection.find({"product": {"$regex": ".*핑크.*"}}, {"_id": 0, "product": 1}):
    print(product)
```

    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'product': '쉬즈홈 모던그리드 순면 여름이불 베개커버 패드세트, 핑크'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키핑크'}
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: '매트리스커버' 카테고리의 상품 중, 상품명에 '차콜'이 포함된 상품을 조회하세요</font><br>
</div>


```python
products = collection.find( { "category": "매트리스커버", "product": { "$regex": ".*차콜.*" } }, { "_id": 0, "category":1, "product": 1} )
for product in products:
    print (product)
```

    {'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'product': '더자리 에코항균 마이크로 매트리스커버, 밀키차콜그레이'}
    {'product': '더자리 프레쉬 퓨어 매트리스 커버, 퓨어 차콜그레이'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'product': '쿠팡 브랜드 - 코멧 홈 순면 매트리스커버, 차콜그레이'}
    

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 'product' 필드에 대한 텍스트 인덱스를 생성하세요</font><br>
</div>


```python
collection.create_index([("product", "text")])
```




    'product_text'



<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="3em" style="color:#0D47A1;">연습문제: 'product' 필드에서 '누빔'이라는 단어를 포함하는 모든 문서를 텍스트 검색을 이용해 찾으세요<br> (find 와 aggregation 을 사용한 코드를 각각 작성해주세요)</font><br>
</div>


```python
for product in collection.find({"$text": {"$search": "누빔"}}, {"_id": 0, "product": 1}):
    print(product)
```

    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 화이트'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'product': '보드래 국내산 순면 60수 누빔 매트리스커버, 그레이'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고'}
    {'product': '스코홈 어번시리즈 순면 차렵이불 누빔 매트커버세트 S 차콜'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜'}
    


```python
pipeline = [
    {"$match": {"$text": {"$search": "누빔"}}},
    {"$project": {"_id": 0, "product": 1}}
]

result = list(collection.aggregate(pipeline))
for product in result:
    print(product)
```

    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 베이지핑크'}
    {'product': '보드래 퍼펙트 누빔 매트리스커버, 차콜'}
    {'product': '보드래 헬로우 누빔 매트리스커버, 핑크'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 화이트'}
    {'product': '바숨 순면 누빔 침대 매트리스커버, 차콜'}
    {'product': '보드래 국내산 순면 60수 누빔 매트리스커버, 그레이'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 미스밍고'}
    {'product': '스코홈 어번시리즈 순면 차렵이불 누빔 매트커버세트 S 차콜'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 프렌치불독'}
    {'product': '타카타카 프리미엄 나노 화이바 누빔 매트리스 커버, 젠틀핑핑'}
    {'product': '쿠팡 브랜드 - 코멧 홈 40수 순면 누빔 매트리스커버, 챠콜'}
    

<div class="alert alert-block" style="border: 2px solid #1976D2;background-color:#E3F2FD;padding:5px;font-size:0.9em;">
본 자료는 저작권법 제25조 2항에 의해 보호를 받습니다. 본 자료를 외부에 공개하지 말아주세요.<br>
본 강의만 잘 정리하면, 데이터 분석, 데이터 과학, 풀스택(백엔드, 프론트엔드) 개발 모두 가능합니다!<br>
<b><a href="https://school.fun-coding.org/">잔재미코딩</a> 에서 본 강의 기반 최적화된 로드맵도 확인하실 수 있습니다</b></div>
