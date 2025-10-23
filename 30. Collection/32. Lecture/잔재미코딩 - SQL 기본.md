---
collection:
  - 📼Lecture
---

# 1. SQL 기초

## 1. RDBMS(Relational Database Management System) 이해

### 1.1 데이터베이스란?

- 체계화된 데이터의 모임
- 여러 응용 시스템들의 통합된 정보를 저장하여, 운영할 수 있는 공용 데이터의 묶음
- 논리적으로 연관된 하나 이상의 자료 모음으로, 데이터를 고도로 구조화함으로써 검색/갱신등의 데이터 관리를 효율화함
- DBMS: 데이터베이스를 관리하는 시스템
- 데이터베이스 장점
    1. 데이터 중복 최소화
    2. 데이터 공유
    3. 일관성, 무결성, 보안성 유지
    4. 최신의 데이터 유지
    5. 데이터의 표준화 가능
    6. 데이터의 논리적, 물리적 독립성
    7. 용이한 데이터 접근
    8. 데이터 저장 공간 절약
- 데이터베이스 단점
    1. 데이터베이스 전문가 필요
    2. 많은 비용 부담
    3. 시스템의 복잡함
- 데이터베이스 랭킹 예
    - [https://db-engines.com/en/ranking](https://db-engines.com/en/ranking)

### 1.2 RDBMS(Relational Database Management System, 관계형 데이터베이스 관리 시스템)

- 데이터베이스의 한 종류로, 가장 많이 사용됨
- 역사가 오래되어, 가장 신뢰성이 높고, 데이터 분류, 정렬, 탐색 속도가 빠름
- 관계형 데이터베이스 = 테이블!
- 2차원 테이블(Table) 형식을 이용하여 데이터를 정의하고 설명하는 데이터 모델
- 관계형 데이터베이스에서는 데이터를 속성(Attribute)과 데이터 값(Attribute Value)으로 구조화(2차원 Table 형태로 만들어짐)
- 데이터를 구조화한다는 것은 속성(Attribute)과 데이터 값(Attribute Value) 사이에서 관계(Relation)을 찾아내고 이를 테이블 모양의 구조로 도식화함의 의미함
- 주요 용어
	![Image|425](https://davelee-fun.github.io/fixeddata/rdbms_term1.png)

- Primary Key and Foreign Key
    - Primary Key(기본키): Primary Key는 한 테이블(Table)의 각 로우(Row)를 유일하게 식별해주는 컬럼(Column)으로,  
        각 테이블마다 Primary Key가 존재해야 하며, NULL 값을 허용하지 않고, 각 로우(Row)마다 유일한 값이어야 한다.
    - Foreign Key(외래키 또는 외부키): Foreign Key는 한 테이블의 필드(Attribute) 중 다른 테이블의 행(Row)을 식별할 수 있는 키
    - ![Image](https://davelee-fun.github.io/fixeddata/rdbms_keys.png)

### 1.3 데이터베이스 스키마(Schema)

- 데이터베이스의 테이블 구조 및 형식, 관계 등의 정보를 형식 언어(formal language)로 기술한 것
    1. 관계형 데이터베이스를 사용하여 데이터를 저장할 때 가장 먼저 할 일은 데이터의 공통 속성을 식별하여 컬럼(Column)으로 정의하고, 테이블(Table)을 만드는 것
    2. 통상적으로 하나의 테이블이 아닌 여러 개의 테이블로 만들고, 각 테이블 구조, 형식, 관계를 정의함
    3. 이를 스키마라고 하며, 일종의 데이터베이스 설계도로 이해하면 됨
    4. 데이터베이스마다 스키마를 만드는 언어가 존재하며, 해당 스키마만 있으면 동일한 구조의 데이터베이스를 만들 수 있음 (데이터베이스 백업과는 달리 데이터 구조만 동일하게 만들 수 있음)
    - 예시
        ![Image|475](https://davelee-fun.github.io/fixeddata/schema.png)


### 1.4 SQL(Structured Query Language)
 
 - 관계형 데이터베이스 관리 시스템에서 데이터를 관리하기 위해 사용되는 표준 프로그래밍 언어(Language)
 - 데이터베이스 스키마 생성 및 수정, 테이블 관리, 데이터 추가, 수정, 삭제, 조회 등, 데이터베이스와 관련된 거의 모든 작업을 위해 사용되는 언어
 - 데이터베이스마다 문법에 약간의 차이가 있지만, 표준 SQL을 기본으로 하므로, 관계형 데이터베이스를 다루기 위해서는 필수적으로 알아야 함
 - SQL은 크게 세 가지 종류로 나뉨
   - 데이터 정의 언어(DDL, Data Definition Language)
   - 데이터 처리 언어(DML, Data Manipulation Language)
   - 데이터 제어 언어(DCL, Data Control Language)
 
#### 1.4.1 데이터 정의 언어(DDL, Data Definition Language): 데이터 구조 정의
 - 테이블(TABLE), 인덱스(INDEX) 등의 개체를 만들고 관리하는데 사용되는 명령
 - CREATE, ALTER, DROP 등이 있음
 
#### 1.4.2 데이터 조작 언어(DML, Data Manipulation Language): 데이터 CRUD (Create(생성), Read(읽기), Update(갱신), Delete(삭제))
 - INSERT	테이블(Table)에 하나 이상의 데이터 추가.
 - UPDATE	테이블(Table)에 저장된 하나 이상의 데이터 수정.
 - DELETE	테이블(Table)의 데이터 삭제.
 - SELECT	테이블(Table)에 저장된 데이터 조회.
 
#### 1.4.3 데이터 제어 언어(DCL, Data Control Language): 데이터 핸들링 권한 설정, 데이터 무결성 처리 등 수행
 - GRANT	데이터베이스 개체(테이블, 인덱스 등)에 대한 사용 권한 설정.
 - BEGIN	트랜잭션(Transaction) 시작.
 - COMMIT	트랜잭션(Transaction) 내의 실행 결과 적용.
 - ROLLBACK	트랜잭션(Transaction)의 실행 취소.

## 2. MySQL 이해 및 실습 
 - MySQL(마이에스큐엘)은 세계에서 가장 많이 쓰이는 오픈 소스 관계형 데이터베이스 관리 시스템
 - MySQL는 오라클사가 소유. 불확실한 라이선스 정책으로 인해, 동일 소스를 기반으로 MariaDB 가 파생됨 (거의 유사, MariaDB가 오픈소스 라이센스를 따르고 있다고 보면 됨)
 
## 3. SQL DDL(Data Definition Language) 이해 및 실습

### 3.1 데이터베이스
 - 데이터베이스 안에는 여러 개의 데이터베이스 이름이 존재한다.
 - 각 데이터베이스 이름 안에는 여러 개의 테이블이 존재한다.

<center><img src="https://davelee-fun.github.io/fixeddata/db_table.png" /></center>

1. 데이터베이스 생성
```sql    
mysql> CREATE DATABASE dbname;
```
    
2. 데이터베이스 목록 보기
```sql
mysql> SHOW DATABASES;
```
    
3. dbname 데이터베이스 사용 시
```sql
mysql> USE dbname;
```
    
4. dbname 데이터베이스 삭제
   - IF EXISTS 옵션은 해당 데이타베이스 이름이 없더라도 오류를 발생시키지 말라는 의미로 옵션임
```sql
mysql> DROP DATABASE [IF EXISTS] dbname;
```

- 참고
	- CREATE DATABASE dbname과 동일한 명령임
```sql
mysql> CREATE SCHEMA dbname;
```
  <div class="alert alert-block custom-background" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 데이터베이스 생성, 목록 보기, 사용, 삭제</font><br>
다음과 같이 데이터베이스 생성, 목록 보기, 사용, 삭제를 실행해보세요
</div>

```sql
mysql> CREATE DATABASE dave;
Query OK, 1 row affected (0.00 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| dave               |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> USE dave;
Database changed
mysql> DROP DATABASE IF EXISTS dave;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.00 sec)
```

### 3.2 테이블

#### 3.2.1 테이블 생성
- 기본 문법 (CREATE TABLE 구문)
```sql
CREATE TABLE 테이블명 (
    컬럼명 데이터형,
    컬러명 데이터형,
    .
    .
    기본키 셋
);
```

##### 1. 테이블을 생성할 데이터베이스를 먼저 사용하겠다고 명령한 후에,
```sql
mysql> CREATE DATABASE dave;
mysql> USE dave;
```

##### 2. 테이블 생성
```sql
mysql> CREATE TABLE 테이블명 (
    컬럼명 데이터형,
    컬러명 데이터형,
    .
    .
    Primary Key 가 될 필드 지정
);
```

##### 숫자 타입의 컬럼 정의 문법

```sql
mysql> CREATE TABLE dave_table (
    -> id INT [UNSIGNED] [NOT NULL] [AUTO_INCREMENT],
```

- id : 컬럼명, 가능한 영어 소문자 중심으로 명명
- INT : 컬럼에 대한 데이터 타입 선언 (참고4 참조)
- [UNSIGNED] : 옵션 사항
             예) TINYINT 로 지정시 -128 ~ +127 
                 TINYINT UNSIGNED 로 지정시 0 ~ 255
- [NOT NULL] : NOT NULL 명시하면 데이터 입력시, 해당 컬럼 데이터에 값이 할당되지 않는 경우를 허락하지 않겠다는 의미
- [AUTO_INCREMENT] : AUTO_INCREMENT 명시하면, 해당 테이블에 데이터 등록시 해당 컬럼은 자동으로 숫자가 1씩 증가하여 저장됨
                   해당 컬럼은 양의 정수만 등록할 수 있어야 하고, 테이블 안에서 AUTO_INCREMENT 컬럼은 하나만 지정 가능함

<center><img src="https://davelee-fun.github.io/fixeddata/numeric_column.png" /></center>

##### 문자 타입의 컬럼 정의 문법
```sql
mysql> CREATE TABLE dave_table (
    -> name VARCHAR(50),
```

- name : 컬럼명, 가능한 영어 소문자 중심으로 명명
- VARCHAR(n) : 컬럼에 대한 문자형 데이터 타입 선언 (참고4 참조)
<center><img src="https://www.fun-coding.org/00_Images/string_column.png" /></center>

##### 시간 타입의 컬럼 정의 문법
```sql
mysql> CREATE TABLE dave_table (
    -> ts DATE,
```

- ts : 컬럼명, 가능한 영어 소문자 중심으로 명명
- DATE : 컬럼에 대한 시간 타입 선언
<center><img src="https://www.fun-coding.org/00_Images/date_column.png" /></cemter>
##### Primary Key 가 될 필드 지정 문법
- 컬럼명1, 컬럼명2, ... : PRIMARY KEY 로 지정할 컬럼명을 넣음 (한 개 이상을 지정할 수 있음, 보통은 한 개를 지정함)
- 따라서, 해당 컬럼은 보통 NOT NULL(NULL 값 방지) AUTO_INCREMENT(유일함) 선언이 되어 있는 경우가 많음
- PRIMARY KEY 로 지정할 컬럼은 NULL 값을 등록할 수 없어야 하고, 컬럼 안에서 같은 값이 없도록 각 값이 유일해야 함

```sql
mysql> CREATE TABLE dave_table (
    -> 컬럼명 데이터형,
    -> .
    -> PRIMARY KEY(컬럼명1, 컬럼명2, ...)
    -> );
```

```sql
예)
CREATE TABLE mytable (
  id INT UNSIGNED NOT NULL AUTO_INCREMENT,
  name VARCHAR(50) NOT NULL,
  modelnumber VARCHAR(15) NOT NULL,
  series VARCHAR(30) NOT NULL,
  PRIMARY KEY(id)
);
```

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 테이블 생성</font><br>
다음과 같이 데이터베이스 및 테이블을 생성해보세요.
</div>


1. 데이터베이스 만들기: 이름 customer_db
2. 테이블 만들기

<img src="https://www.fun-coding.org/00_Images/table_ex.png" />

3. 테이블 잘못만들어졌으면 DROP TABLE [IF EXISTS] dbname; 로 테이블 삭제 후 재생성
##### 실습 모범 답안
```sql
CREATE DATABASE customer_db;
USE customer_db;

CREATE TABLE customer (
	no INTEGER NOT NULL AUTO_INCREMENT,
    name CHAR(20) NOT NULL,
    age TINYINT,
    phone VARCHAR(20),
    email VARCHAR(30) NOT NULL,
    address VARCHAR(50),
    PRIMARY KEY(no)
);
```

#### 3.2.1 테이블 조회
- 기본 문법 (SHOW TABLES)

```sql
mysql> SHOW TABLES;
+----------------+
| Tables_in_dave |
+----------------+
| mytable        |
+----------------+
1 row in set (0.00 sec)
```

- 기본 문법 (DESC 테이블명)

```sql
mysql> desc mytable;
+-------------+------------------+------+-----+---------+----------------+
| Field       | Type             | Null | Key | Default | Extra          |
+-------------+------------------+------+-----+---------+----------------+
| id          | int(10) unsigned | NO   | PRI | NULL    | auto_increment |
| name        | varchar(50)      | NO   |     | NULL    |                |
| modelnumber | varchar(15)      | NO   |     | NULL    |                |
| series      | varchar(30)      | NO   |     | NULL    |                |
+-------------+------------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)
```

#### 3.2.2 테이블 삭제
- 기본 문법 (DROP TABLE 테이블명)
  - IF EXISTS 옵션은 해당 데이타베이스 이름이 없더라도 오류를 발생시키지 말라는 의미로 옵션임
```sql
mysql> DROP TABLE [IF EXISTS] 테이블명;
```

#### 3.2.3 테이블 구조 수정(참고)

- 테이블에 새로운 컬럼 추가
```sql
문법: ALTER TABLE [테이블명] ADD COLUMN [추가할 컬럼명][추가할 컬럼 데이터형] 
mysql> ALTER TABLE mytable ADD COLUMN model_type varchar(10) NOT NULL;
```

- 테이블 컬럼 타입 변경
```sql
문법: ALTER TABLE [테이블명] MODIFY COLUMN [변경할 컬럼명][변경할 컬럼 타입]
mysql>ALTER TABLE mytable MODIFY COLUMN name varchar(20) NOT NULL; 
```

- 테이블 컬럼 이름 변경
```sql
문법: ALTER TABLE [테이블명] CHANGE COLUMN [기존 컬럼 명][변경할 컬럼 명][변경할 컬럼 타입]
mysql>ALTER TABLE mytable CHANGE COLUMN modelnumber model_num varchar(10) NOT NULL;
```

- 테이블 컬럼 삭제
```sql
문법: ALTER TABLE [테이블명] DROP COLUMN [삭제할 컬럼 명]
mysql>ALTER TABLE mytable DROP COLUMN series;
```

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 테이블 생성, 조회</font><br>
다음과 같이 데이터베이스 및 테이블을 생성한 후, 연습문제를 풀어보세요.
</div>

```sql
mysql> CREATE DATABASE dave;
mysql> USE dave;
mysql> CREATE TABLE mytable (
    ->   id INT UNSIGNED NOT NULL AUTO_INCREMENT,
    ->   name VARCHAR(50) NOT NULL,
    ->   modelnumber VARCHAR(15) NOT NULL,
    ->   series VARCHAR(30) NOT NULL,
    ->   PRIMARY KEY(id)
    -> );
mysql> SHOW TABLES;
+----------------+
| Tables_in_dave |
+----------------+
| mytable        |
+----------------+
1 row in set (0.00 sec)
mysql> desc mytable;
+-------------+------------------+------+-----+---------+----------------+
| Field       | Type             | Null | Key | Default | Extra          |
+-------------+------------------+------+-----+---------+----------------+
| id          | int unsigned     | NO   | PRI | NULL    | auto_increment |
| name        | varchar(50)      | NO   |     | NULL    |                |
| modelnumber | varchar(15)      | NO   |     | NULL    |                |
| series      | varchar(30)      | NO   |     | NULL    |                |
+-------------+------------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)
```

##### 연습문제1: 다음과 같이 보이도록 테이블 컬럼을 수정하시오
```sql
mysql> desc mytable;
+------------+------------------+------+-----+---------+----------------+
| Field      | Type             | Null | Key | Default | Extra          |
+------------+------------------+------+-----+---------+----------------+
| id         | int     unsigned | NO   | PRI | NULL    | auto_increment |
| name       | varchar(20)      | NO   |     | NULL    |                |
| model_num  | varchar(10)      | NO   |     | NULL    |                |
| model_type | varchar(10)      | NO   |     | NULL    |                |
+------------+------------------+------+-----+---------+----------------+
```

##### 연습문제2 - 위 테이블을 삭제한 후, 연습문제1과 같은 컬럼을 가진 테이블을 생성하시오 (테이블명은 model_info 로 하시오)

#### 실습 모범 답안
```sql
CREATE TABLE mytable (
       id INT UNSIGNED NOT NULL AUTO_INCREMENT,
       name VARCHAR(50) NOT NULL,
       modelnumber VARCHAR(15) NOT NULL,
       series VARCHAR(30) NOT NULL,
       PRIMARY KEY(id)
);

ALTER TABLE mytable MODIFY COLUMN name varchar(20) NOT NULL;
ALTER TABLE mytable CHANGE COLUMN modelnumber model_num varchar(10) NOT NULL;
ALTER TABLE mytable CHANGE COLUMN series model_type varchar(10) NOT NULL;

DROP TABLE mytable;
CREATE TABLE model_info (
	id INT UNSIGNED NOT NULL AUTO_INCREMENT,
    name VARCHAR(20) NOT NULL,
    model_num VARCHAR(10) NOT NULL,
    model_type VARCHAR(10) NOT NULL,
    PRIMARY KEY(id)
);
```

### 4. SQL DML(Data Manipulation Language) 이해 및 실습 (focusing on CRUD)
#### 4.1. CRUD (Create(생성), Read(읽기), Update(갱신), Delete(삭제))
- 데이터 관리는 결국 데이터 생성, 읽기(검색), 수정(갱신), 삭제 를 한다는 의미

#### 4.1.1 데이터 생성 
- 테이블에 컬럼에 맞추어 데이터를 넣는 작업
- 기본 문법 (INSERT)
    1. 테이블 전체 컬럼에 대응하는 값을 모두 넣기
    ```sql
        mysql> INSERT INTO 테이블명 VALUES(값1, 값2, ...);
    ```
    
    2. 테이블 특정 컬럼에 대응하는 값만 넣기 (지정되지 않은 컬럼은 디폴트값 또는 NULL값이 들어감)
    ```sql
        mysql> INSERT INTO 테이블명 (col1, col2, ...) VALUES(값1, 값2, ...);
    ```

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 데이터 생성(입력)</font><br>
</div>


##### 1. 학생 정보를 저장하는 students 테이블을 생성

```sql
mysql> CREATE DATABASE school;
mysql> USE school;
mysql> CREATE TABLE students (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    age INT UNSIGNED,
    grade VARCHAR(10)
);
```

##### 2. 데이터 삽입 예시:

```sql
mysql> INSERT INTO students VALUES(1, '홍길동', 15, '9학년');
mysql> INSERT INTO students (name, age, grade) VALUES('김철수', 16, '10학년');
```

##### 3. 데이터 확인: 데이터 읽기(검색) 문법 참고 

```sql
mysql> SELECT * FROM students;
+----+----------+------+--------+
| id | name     | age  | grade  |
+----+----------+------+--------+
|  1 | 홍길동     |   15 | 9학년   |
|  2 | 김철수     |   16 | 10학년  |
+----+----------+------+--------+
```

##### 4. `students` 테이블에 아래의 학생 데이터를 추가하세요

   - 이름: 이영희, 나이: 14, 학년: 8학년
   - 이름: 박민수, 나이: 17, 학년: 11학년

   ```sql
   mysql> INSERT INTO students (name, age, grade) VALUES('이영희', 14, '8학년');
   mysql> INSERT INTO students (name, age, grade) VALUES('박민수', 17, '11학년');
   ```

##### 5. 모든 학생의 정보를 조회하세요.

   ```sql
   mysql> SELECT * FROM students;
   ```

#### 4.1.2 데이터 읽기(검색)

- 테이블에 저장된 데이터를 읽는 작업

##### 기본 문법 (SELECT)

- **테이블 전체 컬럼의 데이터 모두 읽기**
  ```sql
  mysql> SELECT * FROM 테이블명;
  ```

- **테이블 특정 컬럼의 데이터만 읽기**
  ```sql
  mysql> SELECT 컬럼1, 컬럼2 FROM 테이블명;
  ```

##### **예시:**
```sql
mysql> SELECT name, age FROM students;
+----------+------+
| name     | age  |
+----------+------+
| 홍길동     |   15 |
| 김철수     |   16 |
| 이영희     |   14 |
| 박민수     |   17 |
+----------+------+
```

##### 조건에 맞는 데이터만 검색하기 (비교 연산자 사용)

- **WHERE 조건문**을 사용하여 특정 조건에 맞는 데이터를 검색할 수 있음
- **비교 연산자:**
  - `=` : 같다
  - `!=` 또는 `<>` : 같지 않다
  - `<` : 작다
  - `>` : 크다
  - `<=` : 작거나 같다
  - `>=` : 크거나 같다

##### **예시:**
1. **나이가 16세인 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE age = 16;
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  2 | 김철수     |   16 | 10학년  |
   +----+----------+------+--------+
   ```

2. **나이가 15세 이상인 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE age >= 15;
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  1 | 홍길동     |   15 | 9학년   |
   |  2 | 김철수     |   16 | 10학년  |
   |  4 | 박민수     |   17 | 11학년  |
   +----+----------+------+--------+
   ```

3. **학년이 '10학년'이 아닌 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE grade != '10학년';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  1 | 홍길동     |   15 | 9학년   |
   |  3 | 이영희     |   14 | 8학년   |
   |  4 | 박민수     |   17 | 11학년  |
   +----+----------+------+--------+
   ```

##### 조건에 맞는 데이터만 검색하기 (논리 연산자)

- 여러 조건을 조합하여 데이터를 검색할 수 있음
  - **AND 연산자**: 모든 조건을 만족하는 데이터 검색
  - **OR 연산자**: 하나 이상의 조건을 만족하는 데이터 검색

##### **예시:**

1. **나이가 15세 이상이고 학년이 '10학년'인 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE age >= 15 AND grade = '10학년';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  2 | 김철수     |   16 | 10학년  |
   +----+----------+------+--------+
   ```

2. **나이가 14세 이하이거나 학년이 '11학년'인 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE age <= 14 OR grade = '11학년';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  3 | 이영희     |   14 | 8학년   |
   |  4 | 박민수     |   17 | 11학년  |
   +----+----------+------+--------+
   ```

##### 조건에 맞는 데이터만 검색하기 (LIKE를 활용한 부분 일치)

- 문자열의 일부를 검색할 때 **LIKE 연산자**를 사용
	- `%` : 0개 이상의 문자를 대체
	- `_` : 단일 문자를 대체

##### **예시:**

1. **이름이 '박'으로 시작하는 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE name LIKE '박%';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  4 | 박민수     |   17 | 11학년  |
   +----+----------+------+--------+
   ```

2. **이름에 '영'이 들어간 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE name LIKE '%영%';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  3 | 이영희     |   14 | 8학년   |
   +----+----------+------+--------+
   ```

3. **이름이 두 글자인 학생 조회**
   ```sql
   mysql> SELECT * FROM students WHERE name LIKE '__';
   ```

**결과:**
   ```sql
   Empty set (0.00 sec)
   ```

현재 데이터에서는 이름이 두 글자인 학생이 없습니다.

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 데이터 읽기(검색)</font><br>
</div>

##### 1. **나이가 16세 이상이고 학년이 '10학년'인 학생 조회**

   ```sql
   mysql> SELECT * FROM students WHERE age >= 16 AND grade = '10학년';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  2 | 김철수     |   16 | 10학년  |
   +----+----------+------+--------+
   ```

##### 2. **이름에 '민'이 포함되지 않은 학생의 이름과 나이 조회**

   ```sql
   mysql> SELECT name, age FROM students WHERE name NOT LIKE '%민%';
   +----------+------+
   | name     | age  |
   +----------+------+
   | 홍길동     |   15 |
   | 김철수     |   16 |
   | 이영희     |   14 |
   +----------+------+
   ```

##### 3. **학년이 '9학년'인 학생 조회**

   ```sql
   mysql> SELECT * FROM students WHERE grade = '9학년';
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  1 | 홍길동     |   15 | 9학년   |
   +----+----------+------+--------+
   ```

#### 4.1.3 데이터 수정

테이블에 저장된 데이터를 수정하는 작업입니다.

##### 기본 문법 (UPDATE)

- **특정 조건에 맞는 데이터를 수정**
 ```sql
  mysql> UPDATE 테이블명 SET 수정할 컬럼명 = '새로운 값' WHERE 조건;
  ```

- **다수의 컬럼 값을 수정할 수도 있음**
 ```sql
  mysql> UPDATE 테이블명 SET 컬럼명1 = '값1', 컬럼명2 = '값2' WHERE 조건;
  ```

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 데이터 수정</font><br>
</div>

##### 1. **이름이 '박민수'인 학생의 나이를 18로 수정하세요.**

   ```sql
   mysql> UPDATE students SET age = 18 WHERE name = '박민수';
   ```

##### 2. **나이가 15이상인 학생들의 grade 를 10학년으로 수정하세요.**

   학년 정보가 문자열로 저장되어 있으므로, 문자열 조작을 통해 학년 숫자를 증가시킵니다.

   ```sql
   mysql> UPDATE students SET grade = '10학년' WHERE age >= 15;
   ```

   **변경 결과 확인:**

   ```sql
   mysql> SELECT * FROM students;
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  1 | 홍길동     |   15 | 10학년  |
   |  2 | 김철수     |   16 | 10학년  |
   |  3 | 이영희     |   14 | 8학년   |
   |  4 | 박민수     |   18 | 10학년  |
   +----+----------+------+--------+
   ```

#### 4.1.4 데이터 삭제

테이블에 저장된 데이터를 삭제하는 작업입니다.

##### 기본 문법 (DELETE)

- **특정 조건에 맞는 데이터를 삭제**

  ```
  mysql> DELETE FROM 테이블명 WHERE 조건;
  ```

- **테이블에 저장된 모든 데이터를 삭제할 수도 있음**

  ```
  mysql> DELETE FROM 테이블명;
  ```

<div class="alert alert-block" style="border: 2px solid #1565C0;background-color:#E3F2FD;padding:10px">
<font size="4em" style="font-weight:bold;color:#0D47A1;">실습 - 데이터 삭제</font><br>
</div>

##### 1. **이름이 '김철수'인 학생을 삭제하세요.**

   ```sql
   mysql> DELETE FROM students WHERE name = '김철수';
   ```

   **삭제 후 데이터 확인:**

   ```sql
   mysql> SELECT * FROM students;
   +----+----------+------+--------+
   | id | name     | age  | grade  |
   +----+----------+------+--------+
   |  1 | 홍길동     |   15 | 10학년  |
   |  3 | 이영희     |   14 | 8학년   |
   |  4 | 박민수     |   18 | 10학년  |
   +----+----------+------+--------+
   ```

### 5. SQL DCL(Data Control Language) 이해 및 참고

> SQL DCL 명령은 MySQL 관리자(데이터베이스 관리자)를 위한 명령이므로, 가볍게 참고하시면 됩니다.

#### MySQL 접속하기

> MySQL에 접속하려면 터미널(명령 프롬프트)에서 다음 명령을 사용합니다.

```bash
mysql -u 사용자이름 -p
```

- `-u`: 접속할 사용자 이름을 지정합니다.
- `-p`: 비밀번호 입력을 요구합니다.

- **예시:**
	- `root` 사용자로 접속하기:

  ```bash
  mysql -u root -p
  ```

  비밀번호 입력 프롬프트가 나타나면 `root` 사용자의 비밀번호를 입력합니다.

#### 5.1 MySQL 사용자 관리

MySQL에서 사용자 계정을 관리하는 기본 명령어입니다.

##### 1. 사용자 확인

> 현재 MySQL에 등록된 사용자 목록을 확인합니다.

```sql
# mysql -u root -p
mysql> USE mysql;
mysql> SELECT host, user FROM user;
```

##### 2. 사용자 추가

> 새로운 사용자를 생성합니다.

- **로컬에서만 접속 가능한 사용자 생성**
  ```sql
  mysql> CREATE USER 'userid'@'localhost' IDENTIFIED BY '비밀번호';
  ```

- **모든 호스트에서 접속 가능한 사용자 생성**
  ```sql
  mysql> CREATE USER 'userid'@'%' IDENTIFIED BY '비밀번호';
  ```

##### 3. 사용자 비밀번호 변경

> 기존 사용자의 비밀번호를 변경합니다.

```sql
mysql> SET PASSWORD FOR 'userid'@'호스트' = '신규비밀번호';
```

##### 4. 사용자 삭제

> 사용자를 삭제합니다.

```sql
mysql> DROP USER 'userid'@'호스트';
```

#### 5.2 MySQL 접속 권한 설정

사용자의 접속 권한을 설정하는 방법입니다.

##### 1. 권한 확인

> 특정 사용자가 가진 권한을 확인합니다.

```sql
mysql> SHOW GRANTS FOR 'userid'@'호스트';
```

##### 2. 접속 허용 설정

- **로컬에서만 접속 허용**
  ```sql
  mysql> GRANT ALL ON 데이터베이스.테이블 TO 'userid'@'localhost';
  ```

- **특정 권한만 허용**
  ```sql
  mysql> GRANT SELECT, UPDATE ON 데이터베이스.테이블 TO 'userid'@'호스트';
  ```

---

##### 옵션 설명

- **권한 종류**
   - `ALL`: 모든 권한을 부여합니다.
   - `SELECT`, `UPDATE`: 특정 권한만 부여하여 권한을 제한할 수 있습니다.
   - 예시: `{SQL} GRANT INSERT, UPDATE, SELECT ON *.* TO 'username'@'localhost';

- **데이터베이스 및 테이블 지정**
   - `데이터베이스.테이블`: 특정 데이터베이스의 특정 테이블에만 권한을 부여합니다.
   - `*.*`: 모든 데이터베이스의 모든 테이블에 대한 권한을 의미합니다.

- **사용자명과 호스트**
   - `'userid'@'호스트'` 형식으로 지정합니다.
   - `'localhost'`: 로컬 호스트에서의 접속을 의미합니다.
   - `'%'`: 모든 호스트에서의 접속을 허용합니다.

- **참고:** 권한 변경 후 변경 사항을 적용하려면 `FLUSH PRIVILEGES;` 명령을 실행할 수 있습니다.
	- 예시: `{SQL} FLUSH PRIVILEGES;`

# 2. Sakila 데이터로 익히는 데이터 분석과 SQL

## 1. 파일 실행

#### sakila database sql 파일 실행
- Mysql Workbench 
	- File -> Open SQL Script -> sakila-schema.sql 선택 후 실행 
	- File -> Open SQL Script -> sakila-data.sql 선택 후 실행
- sakila 테이블 정보 참고
	- https://downloads.mysql.com/docs/sakila-en.pdf

#### 실습 환경 맞추기
- Mysql Workbench 에서 Schemes 탭 선택 후, refresh 버튼을 눌러 sakila 데이터베이스 있는지 확인해보기

#### 전체 sakila 데이터베이스 테이블 확인해보기
>실제 현업에서 사용하는 데이터베이스에는 다양한 테이블이 있지만, 각 테이블에 대한 매우 친절하고, 상세한 설명이 없 는 경우도 많습니다. 데이터를 보며 유추하기도 합니다.

- 전체 데이터에 대한 꼼꼼한 설명은 https://downloads.mysql.com/docs/sakila-en.pdf 에 있음

## 2. SQL SELECT 문법 실습

#### SQL SELECT 문법1 : LIMIT
- 결과중 일부만 데이터 가져오기
	- 예) 결과중 처음부터 10개만 가져오기
		- `{sql}SELECT * FROM 테이블이름 LIMIT 10` (테이블 데이터 중 최상위에 있는 10개의 데이터만 가져오기)
		- `{sql} SELECT * FROM 테이블이름 WHERE 조건문 LIMIT 1` (특정 조건에 맞는 데이터 중 최상위에 있는 1개의 데이터만 가져오기)
- 연습문제를 풀기 위해 이해가 필요한 정보
	- film 테이블 : DVD 렌탈샵에서 렌탈할 수 있는 모든 영화 정보를 가지고 있는 테이블
		- 테이블의 각 컬럼은 실제 컬럼값과 함께 확인해야 이해가 쉬움
		- 보통 다양한 컬럼이 있으므로, 이 중에 필요한 컬럼만 이해하면 됨
- 특정 테이블의 컬럼과 컬럼값 확인을 위해 LIMIT 1 을 많이 사용함
	- `{sql}SELECT * FROM film LIMIT 1 `

#### SQL SELECT 문법2: COUNT
- 결과 수 세기 (데이터 행의 수 세기)
	- 예) 결과 수 세기
		- `{SQL} SELECT COUNT(*) FROM 테이블이름` (테이블 전체 데이터 수 세기)
		- `{SQL} SELECT COUNT(*) FROM 테이블이름 WHERE 조건문` (특정 조건에 맞는 테이블 데이터 수 세기)
- ##### 연습문제 1
	- 영화 테이블(film)에서 총 영화 수 알아내기
	- `{sql} SELECT COUNT(*) FROM film;`

#### SQL SELECT 문법3: DISTICNT
- 특정 컬럼값 출력시 중복된 값을 출력하지 않음
	- 예) 유일한 컬럼값 확인하기
		- `{SQL}SELECT DISTINCT 컬럼명 FROM 테이블이름` (특정 컬럼에 들어가 있는 컬럼값 종류 확인하기)
		- `{SQL} SELECT DISTINCT 컬럼명 FROM 테이블이름 WHERE 조건문` (특정 조건에 맞는, 특정 컬럼에 들어가 있 는 컬럼값 종류 확인하기)
- ##### 연습문제 2
	- 영화 테이블(film) 에서 영화 등급 종류 알아내기, 각 영화의 영화 등급은 rating 컬럼에 들어 있음
		- 참고: 각 컬럼값 이해를 위한 배경 지식이 필요할 때가 있음 (이것을 도메인이라고 이야기함)
		- `{SQL} SELECT DISTINCT rating FROM film;`
- ##### 연습문제 3
	- 영화 테이블(film) 에서 영화 release 연도 종류 알아내기, 각 영화의 release 연도는 release_year 컬럼에 있음
		- `{sql} SELECT DISTINCT release_year FROM film;`
- ##### 연습문제 4
	- 영화 렌탈 테이블(rental) 에서 10개 데이터만 출력하기, rental 테이블은 DVD 를 언제, 누가 빌려갔고, 반환했는지에 대 한 정보를 가지고 있음
		- `{sql} SELECT * FROM rental LIMIT 10;`
- ##### 연습문제 5
	- 영화 렌탈 테이블(rental) 에서 inventory_id 가 367 인 로우(Row) 전체 출력하기, inventory_id 는 빌려간 DVD 의 ID 를 의미함
		- `{sql} SELECT * FROM rental where inventory_id = 367;`

#### 테이블과 테이블 간 관계
- inventory_id, customer_id 와 같이 다른 테이블에 상세 정보가 있고, 각 정보를 구별할 수 있는 ID 값으로 연결되어 있는 경우가 많음
	- 하나의 테이블에 모든 정보를 담지 않습니다.
- ##### 연습문제 6
	- customer 테이블에서 customer 수 알아내기
		- `{sql} SELECT COUNT(*) FROM customer;`

#### SQL SELECT 문법 4: SUM, AVG, MAX, MIN
- 특정 컬럼값을 기반으로 SUM, AVG, MAX, MIN 구하기
	- 예) 컬럼값 분석하기
		- `{SQL} SELECT SUM(컬럼명) FROM 테이블이름` (특정 컬럼에 들어가 있는 컬럼값의 합계 구하기)
		- `{SQL} SELECT AVG(컬럼명) FROM 테이블이름 WHERE 조건문` (특정 조건에 맞는, 특정 컬럼에 들어가 있는 컬 럼값의 평균 구하기)
- ##### 연습문제 7
	- payment 테이블에서 렌탈비용 합계, 평균, 최대값, 최소값 구하기, payment 테이블은 렌탈 비용을 포함한 정보를 담고 있는 테이블임
		- 팁: 단계별로 진행하세요
			- 1단계 - payment 테이블 컬럼 확인하기
			- 2단계 - payment 테이블 amount 컬럼에서 렌탈비용 합계, 평균, 최대값, 최소값 구하기
		- `{sql} SELECT SUM(amount), AVG(amount), MAX(amount), MIN(amount) FROM payment ;`
- ##### 연습문제 8
	- 영화 렌탈 테이블(rental) 에서 inventory_id 가 367 이고, staff_id가 1인 로우(Row) 전체 출력하기
		- `{sql} SELECT * FROM rental where inventory_id = 367 and staff_id = 1;`

#### SQL SELECT 문법5: GROUP BY
- 특정 컬럼값을 기반으로 그룹핑하기
	- 예)`{SQL} SELECT rating FROM film GROUP BY rating` (film 테이블의 rating 값을 그룹핑해라, 즉 rating 값별로 출력하므로, rating 값 종류를 확인할 수 있음)
	- 예) `{SQL} SELECT COUNT(*) FROM film GROUP BY rating `(각 rating 값 종류별로, 몇 개의 데이터가 있는지를 확인)
	- 예) `{SQL} SELECT COUNT(*) FROM film WHERE 조건문 GROUP BY rating` (특정 조건에 맞는 데이터 중 rating 값 종류별로, 몇 개의 데이터가 있는지를 확인)
- ##### 연습문제 9
	- 영화(film table)에 매겨진 등급(rating) 종류를 모두 출력하시요 (GROUP BY 를 사용하세요)
		- `{sql} SELECT rating FROM film GROUP BY rating;`
- ##### 연습문제 10
	- 영화(film table)에 매겨진 등급(rating) 종류에 따른 영화 갯수를 모두 출력하시요 (rating 값과 각 rating 값에 따른 영 화 갯수를 출력하세요)
		- `{sql} SELECT rating, count(*) FROM film GROUP BY rating;`
- ##### 연습문제 11
	- 영화(film table)에서 영화가 PG 또는 G 등급의 영화 수를 각 등급별로 출력하세요 (rating 값과 각 rating 값에 따른 영 화 갯수를 출력하세요)
		- `{sql} SELECT rating, count(*) FROM film WHERE rating = "PG" or rating = "G" GROUP BY rating;`
- ##### 연습문제 12
	- 영화(film table)에서 영화가 G 등급인 영화 제목을 출력하세요
		- `{sql} SELECT title FROM film WHERE rating = "G";`
- ##### 연습문제 13
	- 영화(film table)에서 영화가 PG 또는 G 등급인 영화 제목을 출력하세요
		- `{SQL} SELECT title FROM film WHERE rating = "G" or rating = "PG";`
- ##### 연습문제 14
	- 영화(film table)에서 release 연도가 2006 또는 2007 연도이고, 영화가 PG 또는 G 등급인 영화 제목을 출력하세요
		- 처음부터 다음과 같은 데이터를 추출하고자 한다면, 단계를 나눠서 하나씩 작성해보세요
		- 영화(film table)에서 release 연도가 2006 또는 2007 연도이고, 영화가 PG 또는 G 등급인 영화 제목을 출력하세요
		- `{SQL} SELECT title FROM film WHERE release_year = 2006 or 2007 and rating = "PG" or "G";`

#### SQL과 데이터 분석
- 실제 요구사항은 여러 조건이 있을 수 있습니다. → 단계별로 나눠서 SQL을 작성
- ##### 연습문제 15~17
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수와 rating (등급), 각 그룹별 평균 rental_rate (렌 탈 비용) 출력하세요
- ##### 연습문제 15
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수 출력하기 (각 등급별 갯수 출력하기)
- ##### 연습문제 16
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수 출력하기 (등급과 각 등급별 갯수 출력하기)
- ##### 연습문제 17
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수와 각 등급별 평균 렌탈 비용 출력하기 (등급과 각 등급별 갯수, 각 등급별 평균 렌탈 비용 출력하기)

#### SQL SELECT 문법6: ORDER BY
- 특정 컬럼값을 기준으로 데이터 정렬하기
	- `{SQL} ORDER BY 정렬할 기준 컬럼명 DESC|ASC
		- 예) `{SQL} SELECT * FROM film ORDER BY rating DESC` (rating 값을 기준으로 내림차순으로 정렬해서 데이 터를 가져와라)
		- 예) `{SQL} SELECT * FROM film ORDER BY rating ASC` (rating 값을 기준으로 올림차순으로 정렬해서 데이터 를 가져와라)
		- 예) `{SQL} SELECT * FROM film WHERE 조건문 ORDER BY rating ASC` (특정 조건에 맞는 데이터를 rating 값 을 기준으로 올림차순으로 정렬해서 데이터를 가져와라)
		- 예) `{SQL} SELECT COUNT(*) FROM film WHERE 조건문 GROUP BY 컬럼 ORDER BY COUNT(*) ASC` (특정 조건에 맞는 데이터를 특정 컬럼값을 기준으로 그룹핑하되, rating 값을 기준으로 올림차순으로 정렬해서 데이터를 가져와라)
		- DESC 또는 ASC 를 안쓰면 ASC 로 정렬
- SQL 조건 순서
	- SELECT 컬럼
	- FROM 테이블명
	- WHERE 조건
	- GROUP BY 컬럼
	- ORDER BY 컬럼
	- LIMIT
- ##### 연습문제 18
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수와 각 등급별 평균 렌탈 비용 출력하기, 단 평균 렌 탈비용이 높은 순으로 출력하기 (등급과 각 등급별 갯수, 각 등급별 평균 렌탈 비용 출력하기)

#### SQL SELECT 문법7: AS
- 표시할 컬럼명도 다르게 하기
	- 예) `{SQL} SELECT COUNT(*) AS total FROM film` (film의 전체 데이터 갯수를 COUNT(*) 로 표시하지 말고, total 로 표시하기)
- ##### 연습문제 19
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수와 rating (등급), 각 그룹별 평균 rental_rate (렌 탈 비용) 출력하되, 영화 갯수와 평균 렌탈 비용은 각각 total_films, avg_rental_rate 으로 출력하고, avg_rental_rate 이 높은 순으로 출력하시오
- ##### 연습문제 20
	- film테이블에서 rating (등급)으로 그룹을 묶어서, 각 등급별 영화 갯수와 rating (등급), 각 그룹별 평균 rental_rate (렌 탈 비용) 출력하되, 영화 갯수와 평균 렌탈 비용은 각각 total_films, avg_rental_rate 으로 출력하고, avg_rental_rate 이 높은 순으로 출력하시오 (SQL 구문을 보기 좋게 여러 줄에 걸쳐서 써보기)
- ##### 실습
	- 각 등급별 영화 길이가 130분 이상인 영화의 갯수와 등급을 출력해보세요

# 3. 중급 SQL

## 1. 외래키(Foreign Key)

#### Foreign key 생성
```sql
DROP DATABASE IF EXISTS sqlDB;
CREATE DATABASE sqlDB;
USE sqlDB;
DROP TABLE IF EXISTS userTbl;
CREATE TABLE userTbl (
 userID CHAR(8) NOT NULL PRIMARY KEY,
 name VARCHAR(10) UNIQUE NOT NULL,
 birthYear INT NOT NULL,
 addr CHAR(2) NOT NULL,
 mobile1 CHAR(3),
 mobile2 CHAR(8),
 height SMALLINT,
 mDate DATE,
UNIQUE INDEX idx_userTbl_name (name),
INDEX idx_userTbl_addr (addr)
);
DROP TABLE IF EXISTS buyTbl;
CREATE TABLE buyTbl (
 num INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
 userID CHAR(8) NOT NULL,
 prodName CHAR(4),
 groupName CHAR(4),
 price INT NOT NULL,
 amount SMALLINT NOT NULL,
FOREIGN KEY (userID) REFERENCES userTbl(userID)
);
INSERT INTO userTbl VALUES('LSG', '이승기', 1987, '서울', '011', '11111111',
182, '2008-8-8');
INSERT INTO buyTbl (userID, prodName, groupName, price, amount)
VALUES('LSG', '운동화', '의류', 30, 2);
```

- buyTbl에 데이터 추가
```sql
INSERT INTO buyTbl (userID, prodName, groupName, price, amount)
VALUES('STJ', '운동화', '의류', 30, 2);
```
- 에러가 나면 정상임
	- userTbl 에 userID가 STJ인 데이터가 없기 때문에, 
		- FOREIGN KEY (userID) REFERENCES userTbl(userID) 
		- buyTbl 테이블의 userID 커럼은 userTbl 테이블의 userID를 참조할 때, userTbl 테이블에 userID가 STJ인 데 이터가 없으면, 입력이 안됨 
		- **데이터 무결성 (두 테이블간 관계에 있어서, 데이터의 정확성을 보장하는 제약 조건을 넣는 것임)** 
		- 현업에서는 꼭 필요한 경우만 사용하는 경우가 많음 (비즈니스 로직이 다양하기 때문에, 제약을 걸어놓을 경우, 예 외적인 비즈니스 로직 처리가 어렵기 때문)

- 다음 데이터 넣어보기
```sql
INSERT INTO buyTbl (userID, prodName, groupName, price, amount)
VALUES('LSG', '운동화', '의류', 30, 2);
```

- 다음 SQL query 실행해보기
	- 이번에는 userTbl 에 userID가 STJ 인 데이터를 넣어준 후에, 다시 buyTbl userID에 STJ 관련 데이터를 넣어줍니다.
```sql
INSERT INTO userTbl VALUES('STJ', '서태지', 1975, '경기', '011', '00000000',
171, '2014-4-4');
INSERT INTO buyTbl (userID, prodName, groupName, price, amount)
VALUES('STJ', '운동화', '의류', 30, 2);
```
- 다음 SQL query 실행해보기
	- 이번에는 userTbl에 userID가 STJ 관련 데이터를 삭제해봅니다.
```sql
DELETE FROM userTbl WHERE userID = 'STJ'
```
- 에러나면 정상입니다.
	- buyTbl 에 해당 userID를 참조하는 데이터가 있기 때문입니다.

## 2. GROUP BY와 HAVING

- HAVING 절은 집계함수를 가지고 조건비교를 할 때 사용한다.**(WHERE절은 집계함수와 같이 사용 불가)**
- HAVING절은 GROUP BY절과 함께 사용
- 예
	`{SQL} SELECT provider FROM items GROUP BY provider HAVING COUNT(*) >= 100;`

- HAVING절을 포함한 복합 검색
```SQL
SELECT provider, COUNT(*)
FROM items
WHERE provider != '스마일배송' -- 스마일배송은 제외
GROUP BY provider HAVING COUNT(*) > 100 -- 판매자별로 베스트상품이 100개 이상 등록된 경우만 검색
ORDER BY COUNT(*) DESC; -- 베스트상품 등록갯수 순으로 검색
```

## 3. JOIN 구문 익히기

- JOIN은 두 개 이상의 테이블로부터 필요한 데이터를 연결해 하나의 포괄적인 구조로 결합시키는 연산
- JOIN은 다음과 같이 세분화될 수 있지만, 보통은 INNER JOIN을 많이 사용함
	- INNER JOIN (일반적인 JOIN): 두 테이블에 해당 필드값이 매칭되는 (두 테이블의 모든 필드로 구성된) 레코드만 가져옴
	- OUTER JOIN (참고)
		- LEFT OUTER JOIN: 왼쪽 테이블에서 모든 레코드와 함께, 오른쪽 테이블에 왼쪽 테이블 레코드와 매칭되 는 레코드를 붙여서 가져옴
		- RIGHT OUTER JOIN: 오른쪽 테이블에서 모든 레코드와 함께, 왼쪽 테이블에 왼쪽 테이블 레코드와 매칭되 는 레코드를 붙여서 가져옴
- 데이터베이스 분야에서는 조인을 많이 사용, **개발에서는 가급적 지양(속도 저하)**

#### 3.1 JOIN (INNER JOIN)
- INNER JOIN은 조인하는 테이블의 ON 절의 조건이 일치하는 결과만 출력
- 사용법: FROM 테이블1 INNER JOIN 테이블2 ON 테이블1과 테이블2의 매칭조건
```SQL
SELECT * FROM items INNER JOIN ranking ON ranking.item_code =
items.item_code WHERE ranking.main_category = "ALL"
```
- 테이블 이름 다음에 한칸 띄고 새로운 이름을 쓰면, SQL구문 안에서 해당 이름으로 해당 테이블을 가리킬 수 있음 (AS 용법과 동일함)
	- 일반적으로 이와 같이 많이 사용됨
```SQL
SELECT * FROM items a INNER JOIN ranking b ON a.item_code = b.item_code
WHERE b.main_category = "ALL"
```
- ##### 연습문제 1 전체 베스트상품(ALL 메인 카테고리)에서 판매자별 베스트상품 갯수 출력해보기
```sql
SELECT items.provider, COUNT(*) 
FROM ranking 
JOIN items ON items.item_code=ranking.item_code
 WHERE ranking.main_category = "ALL"
 GROUP BY items.provider
```
- ##### 연습문제 2 메인 카테고리가 패션의류인 서브 카테고리 포함, 패션의류 전체 베스트상품에서 판매자별 베스트 상품 갯수가 5이상인 판매자와 베스트상품 갯수 출력해보기
```SQL
SELECT items.provider, COUNT(*) FROM ranking 
JOIN items ON items.item_code=ranking.item_code
 WHERE ranking.main_category='패션의류'
 GROUP BY items.provider HAVING COUNT(*) >= 5;
```
- ##### 연습문제 3 메인 카테고리가 신발/잡화인 서브 카테고리 포함, 전체 베스트상품에서 판매자별 베스트상품 갯 수가 10이상인 판매자와 베스트상품 갯수를 베스트상품 갯수 순으로 출력해보기
```SQL
SELECT provider, COUNT(*)
FROM items JOIN ranking ON items.item_code = ranking.item_code
WHERE main_category ="신발/잡화"
GROUP BY provider HAVING COUNT(*) >= 10
ORDER BY COUNT(*) DESC;
```
- ##### 연습문제 4 메인 카테고리가 화장품/헤어인 서브 카테고리 포함, 전체 베스트상품의 평균, 최대, 최소 할인 가 격 출력해보기
```sql
SELECT AVG(dis_price), MAX(dis_price), MIN(dis_price)
FROM items JOIN ranking ON items.item_code = ranking.item_code
WHERE main_category ="화장품/헤어"
```


#### 3.2 OUTER JOIN(참고)
- OUTER JOIN은 조인하는 테이블의 ON 절의 조건 중 한쪽의 데이터를 모두 가져옴
- OUTER JOIN은 LEFT OUTER JOIN, RIGHT OUTER JOIN 이 있음

- LEFT OUTER JOIN 예시
```SQL
SELECT * FROM customer_table C LEFT OUTER JOIN order_table O ON
C.customer_id = O.customer_id
```
![](https://i.imgur.com/oHUVkYe.png)

- RIGHT OUTER JOIN 예시
```SQL
SELECT * FROM customer_table C RIGHT OUTER JOIN order_table O ON
C.customer_id = O.customer_id
```
![](https://i.imgur.com/w2YNdqO.png)

- ##### 연습문제 5
	- sakila 데이터베이스에서 address 테이블에는 address_id 가 있지만, customer 테이블에는 없는 데이터의 갯수 출력하기

## 4. 서브쿼리

- SQL문 안에 포함되어 있는 SQL문
	- SQL문 안에서 괄호() 를 사용해서, 서브쿼리문을 추가할 수 있음
- 테이블과 테이블간의 검색시, 검색 범위(테이블 중 필요한 부분만 먼저 가져오도록)를 좁히는 기능에 주로 사용

#### 서브쿼리 사용법
- JOIN은 출력 결과에 여러 테이블의 열이 필요한 경우 유용
- 대부분의 서브쿼리(Sub Query) 는 JOIN 문으로 처리가 가능

##### 예1: 서브카테코리가 '여성신발'인 상품 타이틀만 가져오기
- JOIN SQL을 사용해서 작성하는 방법
```sql
SELECT title
 FROM items
 INNER JOIN ranking ON items.item_code = ranking.item_code
 WHERE ranking.sub_category = '여성신발'
```
- 서브쿼리를 사용해서 작성하는 방법
	- 컬럼값 IN 서브쿼리 출력값 -> 컬럼값과 서브쿼리값이 같을 때
```sql
SELECT title 
FROM items
 WHERE item_code IN
 (SELECT item_code FROM ranking WHERE sub_category = '여성신발')
```

##### 예2: 서브카테코리가 '여성신발'인 상품중 할인가격이 가장 높은 상품의 할인가격 가져오기
- JOIN SQL을 사용해서 작성하는 방법
```sql
SELECT MAX(items.dis_price)
 FROM items
 INNER JOIN ranking ON items.item_code = ranking.item_code
 WHERE ranking.sub_category = '여성신발'
```
- 서브쿼리를 사용해서 작성하는 방법
```sql
SELECT MAX(dis_price) 
FROM items 
WHERE item_code IN 
(SELECT item_code FROM ranking WHERE sub_category = '여성신발')
```

##### 참고: 다양한 서브 쿼리 삽입 위치 (중요x)
- 비교
```sql
SELECT category_id, COUNT(*) AS film_count FROM film_category
 WHERE film_category.category_id >
 (SELECT category.category_id FROM category WHERE category.name = 'Comedy')
 GROUP BY film_category.category_id
```
- FROM 절(거의 쓸 일 없음)
```sql
SELECT
  a, b, c
 FROM
 (SELECT * FROM  atoz_table)
```

##### 연습문제 5 - 메인 카테고리별로 할인 가격이 10만원 이상인 상품이 몇개 있는지를 출력해보기 (JOIN 활용 SQL 과 서브쿼리 활용 SQL 모두 작성해보기)
- JOIN 활용
```sql
SELECT main_category, COUNT(*)
FROM items INNER JOIN ranking ON items.item_code = ranking.item_code
WHERE dis_price >= 100000
GROUP BY main_category;
```

- 서브쿼리
```sql
SELECT main_category, COUNT(*)
FROM ranking
WHERE item_code IN 
	(SELECT item_code FROM items WHERE dis_price >= 100000)
GROUP BY main_category;
```

##### 연습문제 6 - 'items' 테이블에서 'dis_price'가 200000 이상인 아이템들 중, 각 'sub_category'별 아이템 수 를 구하시오. 이때 서브쿼리를 사용하시오.
- JOIN 활용
```sql
SELECT 	sub_category, COUNT(*)
FROM items INNER JOIN ranking ON items.item_code = ranking.item_code
WHERE dis_price >= 200000
GROUP BY sub_category;
```

- 서브쿼리
```SQL
SELECT sub_category, COUNT(*)
FROM ranking
WHERE item_code IN
	(SELECT item_code FROM items WHERE dis_price >= 200000)
GROUP BY sub_category;
```
15:57:36	SELECT main_category, sub_category, AVG(dis_price), AVG(discount_percent) FROM items INNER JOIN ranking ON items.item_code = ranking.item_code GROUP BY sub_category LIMIT 0, 1000	
Error Code: 1055. Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'bestproducts.ranking.main_category' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql_mode=only_full_group_by	0.031 sec


## 파이널 SQL 복합 문제 연습

##### 연습문제 1 - 메인 카테고리, 서브 카테고리에 대해, 평균할인가격과 평균할인율을 출력해보기

```sql
SELECT main_category, sub_category, AVG(dis_price), AVG(discount_percent)
FROM items INNER JOIN ranking ON items.item_code = ranking.item_code
GROUP BY main_category, sub_category;
```

##### 연습문제 2 -  판매자별, 베스트상품 갯수, 평균할인가격, 평균할인율을 베스트상품 갯수가 높은 순으로 출력해 보기

```sql
SELECT provider, count(*), AVG(dis_price), AVG(discount_percent)
FROM items INNER JOIN ranking ON items.item_code = ranking.item_code
GROUP BY provider
ORDER BY count(*) DESC;
```

##### 연습문제 3 - 각 메인 카테고리에서 베스트 상품 갯수가 20개 이상인 판매자의 판매자별 평균할인가격, 평균할 인율, 베스트 상품 갯수 출력해보기

```sql
SELECT main_category, provider, AVG(dis_price), AVG(discount_percent), count(*)
FROM items INNER JOIN ranking ON items.item_code = ranking.item_code
GROUP BY main_category, provider Having count(*) >= 20
ORDER BY main_category, provider DESC;
```

##### 연습문제 4 - 'items' 테이블에서 'dis_price'가 50000 이상인 상품들 중, 각 'main_category'별 평균 'dis_price'와 'discount_percent' 출력해보기

```sql
SELECT main_category, AVG(dis_price), AVG(discount_percent)
FROM items INNER JOIN ranking ON items.item_code = ranking.item_code
WHERE dis_price >= 50000
GROUP BY main_category;
```


## (참고) 개발자와 데이터베이스 관리자를 위한 인덱스

- 데이터베이스 분야에 있어서 테이블에 대한 동작의 속도를 높여주는 자료 구조
- 인덱스를 저장하는 데 필요한 디스크 공간은 보통 테이블을 저장하는 데 필요한 디스크 공간보다 작음
	- 인덱스는 키-필드만 갖고 있고, 나머지 세부 테이블 컬럼 정보는 가지고 있지 않기 때문
- 어떤 데이터를 인덱스로 만드느냐에 따라 방대한 데이터의 경우 성능에 큰 영향을 미칠 수 있음

#### 7.1. 인덱스 종류
- 클러스터형 인덱스: 영어 사전과 같은 형태로 데이터를 재정렬하여 저장한다고 생각하면 됨
	- 테이블의 데이터를 실제로 재정렬하여 디스크에 저장
	- 테이블에 PRIMARY KEY 로 정의한 컬럼이 있을 경우, 자동 생성
	- 한 테이블당 하나의 클러스터형 인덱스만 가질 수 있음
- 보조 인덱스: 데이터는 그대로 두고, 일반 책 뒤에 있는 <찾아보기> 와 같은 형태가 만들어진다고 생각하면 됨
	- 클러스터형 인덱스와는 달리 데이터를 디스크에 재정렬하지 않고, 각 데이터의 위치만 빠르게 찾을 수 있는 구조 로 구성

##### userTbl 테이블 생성
```sql
CREATE TABLE userTbl (
  userID CHAR(8) NOT NULL PRIMARY KEY,
  name  VARCHAR(10) NOT NULL,
  birthYear INT NOT NULL,
  addr  CHAR(2) NOT NULL,
  mobile1 CHAR(3),
  mobile2 CHAR(8),
  height SMALLINT,
  mDate DATE 
);
```

##### 인덱스 확인
```sql
SHOW INDEX FROM userTbl
```

![](https://i.imgur.com/YuyA3M3.png)

- Key_name 이 PRIMARY 로 된 것은 **클러스터형 인덱스**를 의미
- Column_name 이 userID 임을 확인할 수 있음
- (참고) 주요 인덱스 컬럼
	- Table: The name of the table.
	- Non_unique: 0 if the index cannot contain duplicates, 1 if it can.
	- Key_name: The name of the index. If the index is the primary key, the name is always PRIMARY.
	- Seq_in_index: The column sequence number in the index, starting with 1.
	- Column_name: The column name.
	- Collation: How the column is sorted in the index. This can have values A (ascending) or NULL (not sorted).
	- Cardinality: An estimate of the number of unique values in the index.
	- Index_type: The index method used (BTREE, FULLTEXT, HASH, RTREE)

##### buyTbl 테이블 구조
```SQL
CREATE TABLE buyTbl (
  num INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
  userID CHAR(8) NOT NULL,
  prodName CHAR(4),
  groupName CHAR(4),
  price   INT NOT NULL,
  amount  SMALLINT NOT NULL,
 FOREIGN KEY (userID) REFERENCES userTbl(userID)
 );
```

##### 인덱스 확인
```sql
SHOW INDEX FROM buyTbl
```

![](https://i.imgur.com/MvcDJIf.png)

- Key_name 이 PRIMARY 가 아닌 것은 **보조 인덱스**를 의미
- foreign key로 설정된 컬럼이 인덱스가 없다면, 인덱스를 자동 생성

##### 참고: 테이블 변경
- `{SQL} ALERT TABLE 테이블이름 ADD [CONSTRAINT 제약조건명] UNIQUE(컬럼명)
- 테이블에 특정 컬럼에 duplicate 값이 나오지 않도록 제약조건을 추가하기

##### 참고: UNIQUE 제약을 넣으면, 보조 테이블이 만들어짐
- `{SQL} SHOW INDEX FROM userTbl`

#### 7.2. 인덱스 생성 및 삭제
- 인덱스를 필요에 따라 생성/삭제 가능

##### 생성된 테이블에 인덱스 추가하기
- 기본 문법
	- `{SQL} CREATE INDEX 인덱스명 ON 테이블명 ( column 1, column 2, ... );
	- `{SQL} ALTER TABLE 테이블명 ADD INDEX 인덱스명 ( column 1, column 2, ... );`
- 생성된 테이블에 인덱스 추가 예제(CREATE INDEX 사용)
	- `{SQL} CREATE INDEX idx_name ON userTbl (name);`
- 인덱스 확인
	- `{SQL} SHOW INDEX FROM userTbl;`
- 생성된 테이블에 인덱스 추가 예제 (ALTER TABLE 사용)
	- `{SQL} ALTER TABLE userTbl ADD INDEX idx_addr (addr);`
- 인덱스 확인
	- `{SQL} SHOW INDEX FROM userTbl;`

##### 연습문제 1 - groupName 으로 인덱스 추가하고 확인해보기
```SQL
CREATE INDEX idx_prodName ON buyTbl(prodName);
```

##### 연습문제 2 - prodName 으로 인덱스 추가하고 확인해보기
```SQL
CREATE INDEX idx_prodName ON buyTbl(prodName);
```

#### 7.3. 테이블 생성하며 인덱스도 함께 만들기
- 기본 문법
	- INDEX <인덱스명> ( 컬럼명1, 컬럼명2 )
	- UNIQUE INDEX <인덱스명> ( 컬럼명 ) --> 항상 유일해야 함.
		- UNIQUE INDEX 의 경우 컬럼명은 유일한 값을 가지고 있어야 함
```SQL
DROP DATABASE IF EXISTS sqlDB;
 CREATE DATABASE sqlDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
 USE sqlDB;
 DROP TABLE IF EXISTS userTbl;
 CREATE TABLE userTbl (
  userID CHAR(8) NOT NULL PRIMARY KEY,
  name VARCHAR(10) UNIQUE NOT NULL,
  birthYear INT NOT NULL,
  addr CHAR(2) NOT NULL,
  mobile1 CHAR(3),
  mobile2 CHAR(8),
  height SMALLINT,
  mDate  
DATE,
 UNIQUE INDEX idx_userTbl_name (name),
 INDEX idx_userTbl_addr (addr)
 ) DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
 DROP TABLE IF EXISTS buyTbl;
 CREATE TABLE buyTbl (
  num INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
  userID CHAR(8) NOT NULL,
 prodName CHAR(4),
  groupName CHAR(4),
  price  
INT NOT NULL,
  amount  SMALLINT NOT NULL
 ) DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
 INSERT INTO userTbl VALUES('LSG', '이승기', 1987, '서울', '011', '11111111', 
182, '2008-8-8');
 INSERT INTO buyTbl (userID, prodName, groupName, price, amount) 
VALUES('KBS', '운동화', '의류', 30, 2);
```
- UNIQUE INDEX idx_uerTbl_name (name) : name 컬럼에 대해 idx_userTbl_name 이름으로 인덱스 생성, name 은 UNIQUE 제약조건 필요
- INDEX idx_userTbl_addr (addr) : addr 컬럼에 대해 idx_userTbl_addr 이름으로 인덱스 생성

#### 인덱스 삭제
- 기본 문법
	- ALTER TABLE 테이블명 DROP INDEX 인덱스명
- idx_userTbl_name 인덱스 삭제
	- `{SQL} ALTER TABLE userTbl DROP INDEX idx_userTbl_name
- idx_userTbl_addr 인덱스 삭제
	- `{SQL} ALTER TABLE userTbl DROP INDEX idx_userTbl_addr`

##### 연습문제 3 - PRIMARY KEY 놔두고 모든 인덱스 삭제하기
```SQL
ALTER TABLE userTbl DROP INDEX name;
```


##  파이썬으로 다루는 MySQL

### 0. pymysql 라이브러리 소개 및 설치

- mysql을 python에서 사용할 수 있는 라이브러리
    - pymysql 라이브러리 이외에도 MySQLdb(Mysql-pytion), MySQL connector 등 다양한 라이브러리 존재
    - 이 중에서 가장 쉽고 많이 사용하는 라이브러리임

### 1. pymysql 기본 코드 패턴

- SQL 쿼리의 경우 Cursor 객체의 fetchall(), fetchone(), fetchmany() 등의 메서드를 사용하여 서버로부터 가져온 데이타를 코드에서 활용
- 삽입, 갱신, 삭제 등의 DML(Data Manipulation Language) 문장을 실행하는 경우, INSERT/UPDATE/DELETE 후 Connection 객체의 commit() 메서드를 사용하여 데이타를 확정

#### 1. PyMySql 모듈 import
```PYTHON
import pymysql
```

#### 2. pymysql.connect() 메소드를 사용하여 MySQL에 연결
- 호스트명, 포트, 로그인, 암호, 접속할 DB 등을 파라미터로 지정
- 주요 파라미터
	- host : 접속할 mysql server 주소
	- port : 접속할 mysql server 의 포트 번호
	- user : mysql ID
	- passwd : mysql ID의 암호
	- db : 접속할 데이터베이스
	- charset='utf8' : mysql에서 select하여 데이타를 가져올 때 한글이 깨질 수 있으므로 연결 설정에 넣어줌
```PYTHON
db = pymysql.connect(
    host='localhost', # 127.0.0.1 , 0.0.0.0 
    port=3306, 
    user='funcoding', # root
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')
```

#### 3.  MySQL 접속이 성공하면, Connection 객체로부터 cursor() 메서드를 호출하여 Cursor 객체를 가져옴

#### 4. Cursor 객체의 execute() 메서드를 사용하여 SQL 문장을 DB 서버에 전송

#### 5. 테이블 생성
  - Cursor Object 가져오기: cursor = db.cursor()  
  - SQL 실행하기: cursor.execute(SQL)
  - 실행 mysql 서버에 확정 반영하기: db.commit()
```PYTHON
ecommerce = db.cursor()
```

#### 6. cursor 는 control structure of database 입니다. (연결된 객체로 보셔도 좋습니다.)
```PYTHON
sql = """
    CREATE TABLE product (
        PRODUCT_CODE VARCHAR(20) NOT NULL,
        TITLE VARCHAR(200) NOT NULL,
        ORI_PRICE INT,
        DISCOUNT_PRICE INT,
        DISCOUNT_PERCENT INT,
        DELIVERY VARCHAR(2),
        PRIMARY KEY(PRODUCT_CODE)
    );
"""
```

#### 7. SQL 실행 (Cursor 객체의 execute() 메서드를 사용하여 INSERT, UPDATE 혹은 DELETE 문장을 DB 서버에 보냄)
```PYTHON
ecommerce.execute(sql)
```

#### 8. 삽입, 갱신, 삭제 등이 모두 끝났으면 Connection 객체의 commit() 메서드를 사용하여 데이타를 Commit
```PYTHON
db.commit()
```

#### 9. Connection 객체의 close() 메서드를 사용하여 DB 연결을 닫음
```PYTHON
db.close()
```

### 기본 패턴 코드

```python
# 1. 라이브러리 가져오기
import pymysql

# 2. 접속하기
db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')

# 3. 커서 가져오기
cursor = db.cursor()

# 4. SQL 구문 만들기 (CRUD SQL 구문 등)
sql = '''
    CREATE TABLE product (
        PRODUCT_CODE VARCHAR(20) NOT NULL,
        TITLE VARCHAR(200) NOT NULL,
        ORI_PRICE INT,
        DISCOUNT_PRICE INT,
        DISCOUNT_PERCENT INT,
        DELIVERY VARCHAR(2),
        PRIMARY KEY(PRODUCT_CODE)
    );
'''

# 5. SQL 구문 실행하기
cursor.execute(sql)

# 6. DB에 Complete 하기
db.commit()

# 7. DB 연결 닫기
db.close()
```

### 데이터 삽입(INSERT) 패턴 코드
- Cursor Object 가져오기: cursor = db.cursor()  
- SQL 실행하기: cursor.execute(SQL)
- 실행 mysql 서버에 확정 반영하기: db.commit()
```PYTHON
# 1. 라이브러리 가져오기
import pymysql

# 2. 접속하기
db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')

# 3. 커서 가져오기
cursor = db.cursor()

for index in range(10):
    product_code = 215673140 + index + 1
    SQL = """INSERT INTO product VALUES('""" + str(product_code) + """',
    '스위트바니 여름신상5900원~롱원피스티셔츠/긴팔/반팔', 23000, 6900, 70, 'F'
    );
    """
    print(SQL)
    cursor.execute(SQL)


# 6. DB에 Complete 하기
db.commit()

# 7. DB 연결 닫기
db.close()
```

### 데이터 조회(SELECT) 패턴 코드
- Cursor Object 가져오기: cursor = db.cursor()  
- SQL 실행하기: cursor.execute(SQL)
- mysql 서버로부터 데이터 가져오기: 다음과 같은 fetch 관련 메서드 사용

   1. **fetchall()** : 이 메소드는 쿼리 결과의 모든 행을 가져옵니다. 결과는 튜플의 튜플로 반환됩니다. 각 내부 튜플은 하나의 레코드를 나타냅니다.

```python
cursor.execute("SELECT * FROM MyTable")
rows = cursor.fetchall()
for row in rows:
    print(row)
```
    
    위 코드에서 `fetchall()`은 테이블의 모든 행을 반환합니다. 

2. **fetchone()** : 이 메소드는 쿼리 결과의 다음 행을 가져옵니다. 결과는 하나의 튜플로 반환되며, 튜플의 각 요소는 각 필드를 나타냅니다. 더 이상 가져올 행이 없으면 None을 반환합니다.

```python
cursor.execute("SELECT * FROM MyTable")
row = cursor.fetchone()
while row is not None:
    print(row)
    row = cursor.fetchone()
```
    위 코드에서 `fetchone()`은 테이블의 한 행씩 순차적으로 반환합니다.

3. **fetchmany(size)** : 이 메소드는 쿼리 결과의 다음 행들을 가져옵니다. 'size'는 가져올 행의 수를 지정합니다. 결과는 튜플의 튜플로 반환됩니다.

```python
cursor.execute("SELECT * FROM MyTable")
rows = cursor.fetchmany(5)
while rows:
    print(rows)
    rows = cursor.fetchmany(5)
```
    위 코드에서 `fetchmany(5)`는 테이블의 다섯 행씩 순차적으로 반환합니다.

```PYTHON
# 1. 라이브러리 가져오기
import pymysql

# 2. 접속하기
db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')

# 3. 커서 가져오기
cursor = db.cursor()
SQL = "SELECT * FROM product"
cursor.execute(SQL)
rows = cursor.fetchall()
for row in rows:
    print (row)

# 7. DB 연결 닫기
db.close()
```

### 데이터 수정(UPDATE)
- Cursor Object 가져오기: cursor = db.cursor()  
- SQL 실행하기: cursor.execute(SQL)
- 실행 mysql 서버에 확정 반영하기: db.commit()

```PYTHON
# 1. 라이브러리 가져오기
import pymysql

# 2. 접속하기
db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')

# 3. 커서 가져오기
cursor = db.cursor()

SQL = """
    UPDATE product SET
        TITLE ='달리샵린넨원피스 뷔스티에 썸머 가디건 코디전',
        ORI_PRICE=33000,
        DISCOUNT_PRICE=9900,
        DISCOUNT_PERCENT=70
    WHERE PRODUCT_CODE = '215673141'
"""
print(SQL)

cursor.execute(SQL)
db.commit()
db.close()
```

### 데이터 삭제(DELETE)
- Cursor Object 가져오기: cursor = db.cursor()
- SQL 실행하기: cursor.execute(SQL)
- 실행 mysql 서버에 확정 반영하기: db.commit()
```PYTHON
import pymysql

db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')
cursor = db.cursor()

SQL = """DELETE FROM product WHERE PRODUCT_CODE = '215673142'; """
print(SQL)

cursor.execute(SQL)
db.commit()
db.close()
```

## 데이터 수집부터 저장까지 파이썬 기반 MySQL 다루기

#### 파이썬 크롤링
```PYTHON
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

#### Schema 구성
> workbench 를 통해, schema 구성 <br>
> 일회성 schema 는 파이썬으로 자동으로 하기보다는 workbench 를 활용하는 것이 일반적임

```sql
DROP DATABASE IF EXISTS ecommerce;
CREATE DATABASE ecommerce;
USE ecommerce;
CREATE TABLE teddyproducts (
    ID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    TITLE VARCHAR(200) NOT NULL,
    CATEGORY VARCHAR(20) NOT NULL,
    PRIMARY KEY(ID)
);
```

#### 크롤링 + mysql 저장
```python
import requests
from bs4 import BeautifulSoup
import pymysql

db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')
cursor = db.cursor()

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
        SQL = """INSERT INTO teddyproducts (TITLE, CATEGORY) VALUES('""" + product + """', '""" + category + """');"""
        print(SQL)
        cursor.execute(SQL)        

db.commit()
db.close()  
```

#### mysql 데이터 읽기
```python
# 1. 라이브러리 가져오기
import pymysql

# 2. 접속하기
db = pymysql.connect(
    host='localhost', 
    port=3306, 
    user='funcoding', 
    passwd='funcoding', 
    db='ecommerce', 
    charset='utf8')

# 3. 커서 가져오기
cursor = db.cursor()
SQL = "SELECT * FROM teddyproducts WHERE CATEGORY = '행거도어';"
cursor.execute(SQL)
rows = cursor.fetchall()
for row in rows:
    print (row[1])

# 7. DB 연결 닫기
db.close()
```

##### 기본 데이터 분석
- 카테고리 종류를 알려주세요
```sql
SELECT DISTINCT CATEGORY FROM teddyproducts
```

- 카테고리별 상품 갯수를 알려주세요
```sql
SELECT CATEGORY, COUNT(*) FROM teddyproducts GROUP BY CATEGORY
```