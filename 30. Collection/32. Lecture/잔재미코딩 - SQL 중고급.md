---
collection:
  - 📼Lecture
---
## SQL Basic Summary
### 0. 기존 강의에서 익힌 항목 정리

- MySQL과 데이터베이스 부트캠프
	본 강의는 위 강의에서 익힌 SQL 기본을 기반으로 중고급 SQL 을 익히는 강의입니다.

### 1. 데이터베이스 및 MySQL 기본 개념

- 데이터베이스와 RDBMS(관계형 데이터베이스 관리 시스템) 개념
- 테이블(Table), 컬럼(Column), 행(Row) 등의 기본 용어
- 데이터베이스 스키마(Schema) 이해
- 데이터베이스 장점 및 단점

### 2. SQL(Structured Query Language)

- DDL (Data Definition Language): 데이터베이스 생성 및 관리
	- CREATE, ALTER, DROP
- DML (Data Manipulation Language): 데이터 관리 (CRUD)
	- SELECT, INSERT, UPDATE, DELETE
- 참고: DCL (Data Control Language): 사용자 계정 관리
	- CREATE USER

### 3. 문제 풀며 익히는 SQL 문법

- LIMIT: 특정 개수의 데이터만 가져오기
- COUNT: 결과의 행 수 세기
- DISTINCT: 중복된 값을 제거하고 유일한 값 출력
- SUM,AVG, MAX, MIN:특정 컬럼의 합계, 평균, 최대값, 최소값 계산
- GROUP BY: 특정 컬럼을 기준으로 그룹화
- ORDER BY: 특정 컬럼을 기준으로 데이터 정렬
- AS: 컬럼명 또는 결과에 별칭 부여

### 4. 중급 SQL

#### 1. 외래키 (FOREIGN KEY)
- 테이블 간 관계 설정 및 데이터 무결성 유지
- 외래키 제약 조건을 사용해 테이블 간 연결

#### 2. GROUP BY와 HAVING
- 집계 함수와 함께 조건 비교에 사용되는 HAVING 절
- GROUP BY와 함께 사용해 그룹화된 데이터에 조건 적용

#### 3. JOIN 구문
- INNER JOIN: 두 테이블에서 매칭되는 데이터를 결합하여 조회
- OUTER JOIN: 매칭되지 않는 데이터도 포함하여 조회
- LEFT OUTER JOIN: 왼쪽 테이블의 모든 데이터 포함
- RIGHT OUTER JOIN: 오른쪽 테이블의 모든 데이터 포함

#### 4. 서브 쿼리 (Subquery) 기본
- 메인 쿼리 안에 포함된 쿼리로, 검색 범위를 좁히거나 특정 조건을 만족하는 데이터를 조회

#### 5. 인덱스 (INDEX)
- 클러스터형 및 보조 인덱스를 통해 테이블 조회 성능을 최적화하고, 인덱스를 추가하거나 삭제하는 방법

### 5. 참고: 파이썬을 활용한 MySQL 다루기

첨부된 노트북에서 다루는 기술은 다음과 같습니다:

1. pymysql 설치 및 사용: Python에서 MySQL을 다루는 라이브러리.
2. MySQL 연결: pymysql.connect() 로 데이터베이스 연결.
3. SQL 실행: Cursor 객체로 쿼리 실행 및 데이터 조회.
4. 데이터 조작: INSERT , UPDATE , DELETE 쿼리 실행.
5. 트랜잭션 관리: commit() 으로 변경사항 저장.

### 본 강의에서 익히는 중고급 SQL

- 각 문법을 익히고, 해당 문법을 활용한 가벼운 문제를 풀도록 구성
- 이후에는 실전 데이터 분석 문제를 기존에 익힌 문법 + 본 강의에서 익힌 문법을 사용하여, 푸는 연습
- 이를 통해 어떤 SQL 코딩테스트 문제 +실전 데이터 분석이 가능하도록 구성
	- 다양한 SQL 함수
	- 서브 쿼리 중급
	- 집합 연산자
	- 트랜잭션 제어
	- VIEW
	- WITH 절
	- CASE WHEN 절
	- GROUP_CONCAT() 기본 문법
	- 고급 원도우 함수

### 1. SQL 함수

SQL 함수는 값을 반환하는 내장 메소드입니다. 계산을 수행하거나 문자열을 조작하거나 날짜와 시간을 처리하거나 다른 데 이터 조작을 수행하는 데 사용할 수 있습니다. 대부분의 SQL 함수는 데이터베이스 서버에 내장되어 있으므로 모든 SQL 쿼리 에서 사용할 수 있습니다. 함수에는 여러 유형이 있습니다. 각 SQL 함수에 대한 설명과 예시를 반으로 테스트해보며 알아보겠습니다.

#### 1. 문자열 함수

- `LENGTH(string)` : 문자열의 길이를 반환합니다.
	- 예: film 테이블의 title 컬럼에 대한 각 영화 제목의 길이를 조회합니다
		- `{SQL} SELECT title, LENGTH(title) AS title_length FROM film LIMIT 10`
- `UPPER(string)` : 문자열을 대문자로 변환합니다.
	- 예: film 테이블의 title 컬럼에 대한 영화 제목을 대문자로 변환하여 조회합니다. 
		- `{SQL}SELECT UPPER(title) AS uppercased_title FROM film LIMIT 10; 
- `LOWER(string)` : 문자열을 소문자로 변환합니다. 
	- 예: film 테이블의 title 컬럼에 대한 영화 제목을 소문자로 변환하여 조회합니다. 
		- `{SQL} SELECT LOWER(title) AS lowercased_title FROM film LIMIT 10; 
- `CONCAT(string1, string2, ...)` : 두 개 이상의 문자열을 하나로 연결합니다. 
	- 예: actor 테이블에서 first_name 과 last_name 을 연결하여 전체 이름을 조회합니다
		- `{SQL} SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM actor LIMIT 10;`
- `SUBSTRING(string, start, length)` : 문자열에서 부분 문자열을 추출합니다
	- 예: film 테이블의 description 컬럼에서 첫 10글자를 추출합니다.
		- `{SQL} SELECT SUBSTRING(description, 1, 10) AS short_description FROM film LIMIT 10;`

#### 2. 날짜/시간 함수

- `NOW()` : 현재 날짜와 시간을 반환합니다.
	- 예: 현재 날짜와 시간을 조회합니다.
		 - `{SQL} SELECT NOW() AS current_date_time;
 - `CURDATE()` : 현재 날짜를 반환합니다.
	- 예: 현재 날짜를 조회합니다.
		- `{SQL} SELECT CURDATE() AS current_date;
- `CURTIME()` : 현재 시간을 반환합니다.
	- 예: 현재 시간을 조회합니다.
		- `{SQL} SELECT CURTIME() AS current_time;
- `DATE_ADD(date, INTERVAL, unit)` : 날짜에 간격을 추가합니다.
	- 예: rental 테이블에서 각 대여 시작 날짜(rental_date )에 7일을 추가합니다.
		- `{SQL} SELECT rental_date, DATE_ADD(rental_date, INTERVAL 7 DAY) AS return_date FROM rental LIMIT 10;
- `DATE_SUB(date, INTERVAL, unit)` : 날짜에서 간격을 뺍니다.
	- 예: rental 테이블에서 각 대여 시작 날짜(rental_date )에서 7일을 뺍니다.
		- `{SQL}SELECT rental_date, DATE_SUB(rental_date, INTERVAL 7 DAY) AS  earlier_date FROM rental LIMIT 10;

#### 3. 숫자 함수

- ABS(number) : 숫자의 절대값을 반환합니다.
	- 예: 아래 예제는 해당 쿼리에서 실제로 음수 값이 없음을 가정하고 작성된 것입니다.
		- `{sql} SELECT ABS(-payment.amount) AS absolute_amount FROM payment LIMIT 10;
- CEIL(number) : 숫자보다 크거나 같은 가장 작은 정수 값을 반환합니다.
	- 예: payment 테이블에서 amount 컬럼의 값을 올림하여 조회합니다.
		- `{sql} SELECT CEIL(amount) AS ceiling_amount FROM payment LIMIT 10;
- FLOOR(number) : 숫자 이하의 가장 큰 정수 값을 반환합니다.
	- 예: payment 테이블에서 amount 컬럼의 값을 내림하여 조회합니다.
		- `{sql} SELECT FLOOR(amount) AS floor_amount FROM payment LIMIT 10;
- ROUND(number, decimals) : 숫자를 특정 소수점 자리수로 반올림합니다.
	- 예: payment 테이블에서 amount 컬럼의 값을 소수점 두 자리로 반올림하여 조회합니다.
		- `{sql} SELECT ROUND(amount, 2) AS rounded_amount FROM payment LIMIT 10;
- SQRT(number) : 숫자의 제곱근을 반환합니다. 
	- 예: film 테이블에서 length 컬럼의 제곱근을 계산합니다.
		- `{sql} SELECT SQRT(length) AS sqrt_length FROM film LIMIT 10;

#####  연습문제

1. film 테이블에서 영화 제목( title )의 길이가 15자인 영화들을 찾아주세요.
2. actor 테이블에서 첫 번째 이름( first_name )이 소문자로 'john'인 배우들의 전체 이름을 대문자로 출력해주세요.
3. film 테이블에서 description 의 3번째 글자부터 6글자가 'Action'인 영화의 제목을 찾아주세요.
4. rental 테이블에서 대여 시작 날짜( rental_date )가 2006년 1월 1일 이후인 모든 대여에 대해, 예상 반납 날짜를 대여 날짜로부터 5일 뒤로 설정해주세요.
5. payment 테이블에서 결제 금액( amount )이 5 이하인 모든 결제에 대해, 절대값을 계산하여 출력해주세요.
6. film 테이블에서 영화 길이( length )가 120분 이상인 모든 영화에 대해, 영화 길이의 제곱근을 계산해주세요.
7. payment 테이블에서 결제 금액( amount )을 소수점 첫 번째 자리에서 반올림하여 출력해주세요.

### 2. 서브쿼리 중급

서브쿼리(Sub query)는 중첩 쿼리(Nested query) 라고도 하며, 다른 SQL 쿼리의 맥락 안에 포함되는 쿼리입니다. 추가적 인 서브쿼리 예제를 테스트해보며, 서브 쿼리에 대해서도 보다 익숙해지도록 합니다.

#### 1. 간단한 서브 쿼리

평균 결제 금액보다 많은 결제를 한 고객을 찾아봅시다:

```SQL
SELECT first_name, last_name
FROM customer
WHERE customer_id IN (
	SELECT customer_id
	FROM payment
	WHERE amount > (SELECT AVG(amount) FROM payment)
);
```

이 쿼리에서 가장 안쪽 쿼리는 평균 결제 금액을 계산합니다. 중간 쿼리는 이 평균 금액보다 큰 결제의 customer_id 를 찾습니다. 가장 바깥 쿼리는 이들 고객의 이름을 가져옵니다.

#### 2. GROUP BY가 있는 서브쿼리

평균 결제 횟수보다 많은 결제를 한 고객을 찾아봅시다:

```SQL
SELECT first_name, last_name
FROM customer
WHERE customer_id IN (
	SELECT customer_id
	FROM payment
	GROUP BY customer_id
	 HAVING COUNT(*) > (
		SELECT AVG(payment_count) 
		FROM (
			SELECT COUNT(*) AS payment_count
			FROM payment
			GROUP BY customer_id
		)
	)
);
```

이 쿼리에서 가장 안쪽 쿼리는 각 고객에 대한 결제 횟수를 세고 그 평균을 계산합니다. 중간 쿼리는 이 평균보다 더 많은 결제 를 한 고객의 customer_id 를 찾습니다. 가장 바깥 쿼리는 이들 고객의 이름을 가져옵니다.

#### 3. 최대값을 가진 행 찾기

가장 많은 결제를 한 고객을 찾아봅시다:

```SQL
SELECT first_name, last_name
FROM customer
WHERE customer_id = (
	SELECT customer_id
	FROM (
		SELECT customer_id, COUNT(*) AS payment_count
		FROM payment
		GROUP BY customer_id
	) AS payment_counts
	ORDER BY payment_count DESC
	LIMIT 1
);
```

이 쿼리에서는 가장 안쪽 쿼리가 각 고객의 결제 횟수를 계산하고, 중간 쿼리가 결제 횟수를 내림차순으로 정렬하여 가장 많은 결제를 한 고객의 customer_id 를 찾습니다. 그리고 가장 바깥 쿼리가 해당 고객의 이름을 가져옵니다.

#### 4. 상관 서브쿼리

각 고객에 대해 자신이 결제한 평균 금액보다 큰 결제를 한 경우의 결제 정보를 찾아봅시다:
```sql
SELECT P.customer_id, P.amount, P.payment_date
FROM payment P
WHERE P.amount > (
  SELECT AVG(amount)
  FROM payment
  WHERE customer_id = P.customer_id
);
```

##### 연습문제

- 평균 영화 길이보다 긴 영화 제목 찾기
```sql
SELECT title
FROM film
WHERE length > (SELECT AVG(length) FROM film);
```

- 평균 대여 횟수보다 많이 대여한 고객 이름
```sql
SELECT first_name, last_name
FROM customer
WHERE customer_id IN (
  SELECT customer_id
  FROM rental
  GROUP BY customer_id
  HAVING COUNT(*) > (
    SELECT AVG(rental_count)
    FROM (
      SELECT COUNT(*) AS rental_count
      FROM rental
      GROUP BY customer_id
    ) AS rental_counts
  )
);
```

- 가장 많은 영화를 대여한 고객
```sql
SELECT first_name, last_name
FROM customer
WHERE customer_id = (
  SELECT customer_id
  FROM (
    SELECT customer_id, COUNT(*) AS rental_count
    FROM rental
    GROUP BY customer_id
  ) AS rental_counts
  ORDER BY rental_count DESC
  LIMIT 1
);
```

- 각 고객이 평균보다 더 긴 영화를 대여한 목록
```sql
SELECT C.first_name, C.last_name, F.title
FROM customer C
JOIN rental R ON R.customer_id = C.customer_id
JOIN inventory I ON I.inventory_id = R.inventory_id
JOIN film F ON F.film_id = I.film_id
WHERE F.length > (
  SELECT AVG(FIL.length)
  FROM film FIL
  JOIN inventory INV ON INV.film_id = FIL.film_id
  JOIN rental REN ON REN.inventory_id = INV.inventory_id
  WHERE REN.customer_id = C.customer_id
);
```

### 3. 집합 연산자: UNION, UNION ALL, INTERSECT, EXCEPT

#### 1. UNION  
중복을 제거하고 두 SELECT 결과를 합침  
```sql
SELECT film_id FROM film
UNION
SELECT film_id FROM inventory;
```

#### 2. UNION ALL  
중복도 포함하여 결과 합침  
```sql
SELECT film_id FROM film
UNION ALL
SELECT film_id FROM inventory;
```

#### 3. INTERSECT  
두 SELECT 결과의 교집합  
```sql
SELECT film_id FROM film
INTERSECT
SELECT film_id FROM inventory;
```

#### 4. EXCEPT  
첫 SELECT 결과에는 있지만 두 번째 SELECT 결과에는 없는 행  
```sql
SELECT film_id FROM film
EXCEPT
SELECT film_id FROM inventory;
```

##### 연습문제
1. 중복 없이 film_id 조회  
```sql
SELECT film_id FROM film
UNION
SELECT film_id FROM film_category;
```

2. 중복 포함 film_id 조회  
```sql
SELECT film_id FROM film
UNION ALL
SELECT film_id FROM film_category;
```

3. 두 테이블 모두 존재하는 film_id 조회  
```sql
SELECT film_id FROM film
INTERSECT
SELECT film_id FROM film_category;
```

4. film에는 있고 film_category에는 없는 film_id 조회  
```sql
SELECT film_id FROM film
EXCEPT
SELECT film_id FROM film_category;
```

---

### 트랜잭션, COMMIT, ROLLBACK

#### 개념
- `START TRANSACTION;` : 트랜잭션 시작
- `COMMIT;` : 변경 사항 저장
- `ROLLBACK;` : 변경 사항 취소

#### 예제
```sql
START TRANSACTION;
UPDATE rental SET return_date = NOW() WHERE rental_id = 1;
UPDATE rental SET return_date = NOW() WHERE rental_id = 2;
COMMIT;
```

```sql
START TRANSACTION;
UPDATE rental SET return_date = NOW() WHERE rental_id = 3;
UPDATE rental SET return_date = NOW() WHERE rental_id = 4;
ROLLBACK;
```

##### 연습문제
1. payment_id가 1001인 amount를 3.99로 변경
```sql
START TRANSACTION;
UPDATE payment SET amount = 3.99 WHERE payment_id = 1001;
COMMIT;
```

2. payment_id가 1001인 amount를 2.99로 변경
```sql
START TRANSACTION;
UPDATE payment SET amount = 2.99 WHERE payment_id = 1001;
COMMIT;
```

---

### SQL VIEW 사용법

#### VIEW 생성
```sql
CREATE VIEW ActorInfo AS
SELECT first_name, last_name
FROM actor
WHERE actor_id < 50;
```

#### VIEW 수정
```sql
CREATE OR REPLACE VIEW ActorInfo AS
SELECT first_name, last_name
FROM actor
WHERE actor_id < 100;
```

#### VIEW 삭제
```sql
DROP VIEW ExpensiveFilms;
```

##### 연습문제
1. ActorInfo 생성 (actor_id < 50)
2. ExpensiveFilms 생성 (rental_rate > 2.00)
3. ActorInfo 수정 (actor_id < 100)
4. ExpensiveFilms 삭제

---

### WITH 절 (CTE)

#### 문법
```sql
WITH cte_name AS (
  SELECT ...
)
SELECT ...
```

#### 예제
```sql
WITH FilmInventory AS (
  SELECT DISTINCT film_id FROM inventory
)
SELECT f.film_id, f.title
FROM film f
JOIN FilmInventory fi ON f.film_id = fi.film_id;
```

---

### CASE WHEN 절

#### 문법
```sql
CASE
  WHEN condition1 THEN result1
  WHEN condition2 THEN result2
  ...
  ELSE result
END
```

#### 예제
```sql
SELECT title,
CASE
  WHEN rental_rate < 1 THEN 'Cheap'
  WHEN rental_rate BETWEEN 1 AND 3 THEN 'Moderate'
  ELSE 'Expensive'
END AS PriceCategory
FROM film;
```

---

#### WITH + CASE 연습문제

##### 1. 각 rating별 평균 영화 길이
```sql
WITH AvgFilmLength AS (
  SELECT rating, AVG(length) AS avg_length
  FROM film
  GROUP BY rating
)
SELECT * FROM AvgFilmLength;
```

##### 2. active 컬럼으로 고객 상태 구분
```sql
SELECT customer_id,
CASE
  WHEN active = 1 THEN 'Active'
  ELSE 'Inactive'
END AS CustomerStatus
FROM customer;
```

##### 3. 각 rating별 평균 rental_duration
```sql
WITH AvgRentalDuration AS (
  SELECT rating, AVG(rental_duration) AS avg_duration
  FROM film
  GROUP BY rating
)
SELECT * FROM AvgRentalDuration;
```

##### 4. Active/Inactive 고객 수
```sql
SELECT 
CASE
  WHEN active = 1 THEN 'Active'
  ELSE 'Inactive'
END AS CustomerStatus,
COUNT(*)
FROM customer
GROUP BY CustomerStatus;
```

##### 5. 고객별 총 지불액 기준으로 Low/Medium/High 분류
```sql
WITH CustomerPayments AS (
  SELECT customer_id, SUM(amount) AS total_payment
  FROM payment
  GROUP BY customer_id
)
SELECT customer_id,
CASE
  WHEN total_payment BETWEEN 0 AND 50 THEN 'Low'
  WHEN total_payment BETWEEN 51 AND 100 THEN 'Medium'
  ELSE 'High'
END AS PaymentStatus,
total_payment
FROM CustomerPayments;
```


## Sakila 데이터로 연습하는 SQL 데이터 분석 (중급)

### 연습문제1
**category 테이블에서 "Comedy", "Sports", "Family" 카테고리의 category_id 알아내기 (category_id 와 카테고리 명 출력하기)** 

```sql
SELECT name, category_id FROM category WHERE name = 'Comedy' OR name = 'Sports' OR name = 'Family'
```


---

### 연습문제2
**film_category 테이블에서 영화 아이디(film_id)가 2인 영화의 카테고리 ID 알아내기** 

1.  **단계별로 진행하세요: 1단계 - film_category 테이블 컬럼 확인하기** 
    ```sql
    SELECT * FROM film_category LIMIT 1
    ```
    

2.  **단계별로 진행하세요: 2단계 - film_id 가 2인 영화 데이터(행) 확인하기** 
    ```sql
    SELECT category_id FROM film_category WHERE film_id = 2
    ```
    

---

### 연습문제3
**film_category 테이블에서 카테고리 ID별 영화 수 알아내기** 

```sql
SELECT category_id, COUNT(*) FROM film_category GROUP BY category_id;
```


---

### 연습문제4
**카테고리가 Comedy 인 영화 수 알아내기 (JOIN, 서브쿼리 각각 작성)** 
(category 테이블에는 카테고리 이름과 category_id, film_category 테이블에는 category_id와 각 영화 id가 있음) 

1.  **단계별로 진행하세요: 1단계 - category 테이블 컬럼 확인하기** 
    ```sql
    SELECT * FROM category LIMIT 1
    ```
    

2.  **단계별로 진행하세요: 2단계 - Comedy 의 category_id 알아내기** 
    ```sql
    SELECT * FROM category WHERE name = 'Comedy'
    ```
    

3.  **단계별로 진행하세요: 3단계 - category 와 film_category 테이블을 JOIN 해서, Comedy 카테고리 영화 데이터만 출력하기** 
    ```sql
    SELECT * FROM film_category A
    JOIN category B
    ON B.category_id = A.category_id
    WHERE B.name = 'Comedy'
    ```
    

4.  **단계별로 진행하세요: 4단계 - category 와 film_category 테이블을 JOIN 해서, Comedy 카테고리 영화 데이터 수 출력하기** 
    ```sql
    SELECT COUNT(*) FROM film_category
    JOIN category
    ON category.category_id = film_category.category_id
    WHERE category.name = 'Comedy'
    ```
    

**서브쿼리로 작성시** 
```sql
SELECT COUNT(*) FROM film_category
WHERE category_id IN
(SELECT category_id FROM category WHERE name="Comedy");
```


---

### 연습문제5
**카테고리가 Comedy, Sports, Family 인 영화 수 알아내기 (JOIN 사용하기)** 
(category 테이블에는 카테고리 이름과 category_id, film_category 테이블에는 category_id와 각 영화 id가 있음) 

1.  **단계별로 진행하세요: 1단계 - Comedy, Sports, Family 인 총 영화 수 알아내기** 
    ```sql
    SELECT COUNT(*) FROM film_category
    JOIN category
    ON category.category_id = film_category.category_id
    WHERE category.name = 'Comedy' OR category.name = 'Sports' OR category.name = 'Family'
    ```
    

2.  **단계별로 진행하세요: 2단계 - Comedy, Sports, Family 인 각각의 영화 수 알아내기** 
    ```sql
    SELECT COUNT(*) FROM film_category
    JOIN category
    ON category.category_id = film_category.category_id
    WHERE category.name = 'Comedy' OR category.name = 'Sports' OR category.name = 'Family'
    GROUP BY category.category_id
    ```
    

3.  **단계별로 진행하세요: 3단계 - Comedy, Sports, Family 인 각각의 영화 수를 각각의 카테고리 이름과 함께 출력하기** 
    ```sql
    SELECT category.name, COUNT(*) FROM film_category
    JOIN category
    ON category.category_id = film_category.category_id
    WHERE category.name = 'Comedy' OR category.name = 'Sports' OR category.name = 'Family'
    GROUP BY category.category_id
    ```
    

4.  **단계별로 진행하세요: 4단계 - Comedy, Sports, Family 인 각각의 영화 수를 각각의 카테고리 이름과 함께 출력하되, 영화 수 컬럼명을 film_count 로 변경해서 출력하기** 
    ```sql
    SELECT category.name, COUNT(*) AS film_count FROM film_category
    JOIN category
    ON category.category_id = film_category.category_id
    WHERE category.name = 'Comedy' OR category.name = 'Sports' OR category.name = 'Family'
    GROUP BY category.category_id
    ```
    

5.  **단계별로 진행하세요: 5단계 - 4단계에서 작성한 SQL에서, 단 각각의 테이블명을 간결히 변경해서, SQL 구문을 간결하게 바꿔보세요.** 
    ```sql
    SELECT C.name, COUNT(*) AS film_count FROM film_category F
    JOIN category C
    ON C.category_id = F.category_id
    WHERE C.name = 'Comedy' OR C.name = 'Sports' OR C.name = 'Family'
    GROUP BY C.category_id
    ```
    

---

### 연습문제6 (HAVING 문법을 사용해서 작성해보세요!)
**카테고리에 포함되는 각각의 영화 수가 70 이상인 카테고리명을 출력하기** 

```sql
SELECT C.name, COUNT(*) AS film_count FROM film_category F
JOIN category C
ON C.category_id = F.category_id
GROUP BY C.category_id
HAVING COUNT(*) > 70
```


---

### 연습문제7
**각 카테고리에 포함된 영화들의 렌탈 횟수 구해보기 (각 카테고리별에 포함된 영화들의 총 렌탈 횟수와 각 카테고리명을 출력하는 것이 최종 목표)** 

-   rental 테이블에 렌탈 기록이 있음 
-   inventory 테이블에 물품현황과 해당 물품(DVD)에 들어 있는 영화 아이디가 있음 
-   film_category 테이블에 영화 아이디에 매칭되는 카테고리 아이디가 있음 
-   category 테이블에 카테고리 아이디에 매칭되는 카테고리명이 있음 

1.  **단계별로 진행하세요: 1단계 - rental, inventory, film_category, category 테이블 확인하기** 
2.  **단계별로 진행하세요: 2단계 - rental, inventory, film_category, category 테이블 연결고리로 연결하기** 
    ```sql
    SELECT * FROM rental
    JOIN inventory ON rental.inventory_id = inventory.inventory_id
    JOIN film_category ON inventory.film_id = film_category.film_id
    JOIN category ON film_category.category_id = category.category_id
    LIMIT 1
    ```
    
3.  **단계별로 진행하세요: 3단계 - category_id 로 그룹핑해서, 각 카테고리별 카운트값(렌탈 횟수)과 카테고리명을 출력하세요** 
    ```sql
    SELECT category.name, COUNT(*) FROM rental
    JOIN inventory ON rental.inventory_id = inventory.inventory_id
    JOIN film_category ON inventory.film_id = film_category.film_id
    JOIN category ON film_category.category_id = category.category_id
    GROUP BY category.category_id
    ```
    

---

### 연습문제8
**"Comedy", "Sports", "Family" 카테고리에 포함되는 영화들의 렌탈 횟수 출력하기 (카테코리명, 렌탈 횟수)** 
-   rental 테이블에 렌탈 기록이 있음 
-   inventory 테이블에 물품현황과 해당 물품(DVD)에 들어 있는 영화 아이디가 있음 
-   film_category 테이블에 영화 아이디에 매칭되는 카테고리 아이디가 있음 
-   category 테이블에 카테고리 아이디에 매칭되는 카테고리명이 있음 

```sql
SELECT category.name, COUNT(*) FROM rental
JOIN inventory ON rental.inventory_id = inventory.inventory_id
JOIN film_category ON inventory.film_id = film_category.film_id
JOIN category ON film_category.category_id = category.category_id
WHERE category.name = 'Comedy' OR category.name = 'Sports' OR category.name = 'Family'
GROUP BY category.category_id
```


---

### 연습문제9
**카테고리가 Comedy 인 데이터의 렌탈 횟수 출력하기 (서브쿼리 문법으로 작성해보세요)** 

```sql
SELECT COUNT(*) FROM rental WHERE inventory_id IN
(
    SELECT inventory_id FROM inventory WHERE film_id IN
    (
        SELECT film_id FROM film_category WHERE category_id IN
        (SELECT category_id FROM category WHERE name = 'Comedy')
    )
)
```


---

### 연습문제10
**카테고리가 Comedy 인 데이터의 영화 갯수 출력하기 (JOIN 문법으로 작성해보세요)** 

```sql
SELECT COUNT(*) FROM film_category
JOIN category ON category.category_id = film_category.category_id
WHERE category.name = 'Comedy'
```


---

### 연습문제11
**카테고리가 Comedy 인 데이터의 영화 갯수 출력하기 (서브쿼리 문법으로 작성해보세요)** 

```sql
SELECT COUNT(*) FROM film_category
WHERE film_category.category_id IN
(SELECT category.category_id FROM category WHERE category.name = 'Comedy')
```


---

### 연습문제12
**address 테이블에는 address_id 가 있지만, customer 테이블에는 없는 데이터의 갯수 출력하기 (RIGHT JOIN 문법으로 작성해보세요!)** 

```sql
SELECT COUNT(*) FROM customer C
RIGHT OUTER JOIN address A
ON A.address_id=C.address_id
WHERE C.customer_id IS NULL
```


---

### 연습문제13 (실전)
**캐나다 고객에게 이메일 마케팅 캠페인을 진행하고자 합니다. 캐나다 고객의 이름과, email 주소 리스트를 뽑아주세요** 

```sql
SELECT
first_name, last_name, email
FROM customer CU
JOIN address A ON CU.address_id=A.address_id
JOIN city CI ON CI.city_id=A.city_id
JOIN country CTR ON CTR.country_id=CI.country_id
WHERE CTR.country='canada';
```


---

### 연습문제14 (실전)
**젊은 가족 사이에서 매출이 저조해서, 모든 가족 영화를 홍보 대상으로 삼으려고 합니다. 가족 영화로 분류된 모든 영화 리스트를 뽑아주세요** 

```sql
SELECT F.title
FROM film F
JOIN film_category FC ON F.film_id = FC.film_id
JOIN category CA ON FC.category_id = CA.category_id
WHERE CA.name = 'Family';
```


---

### 연습문제15 (실전)
**가장 자주 대여하는 영화 리스트를 참고로 보고 싶습니다. 가장 자주 대여하는 영화 순으로 100개만 뽑아주세요 title (영화제목)과 Rentals (렌탈 횟수)로 보고 싶습니다.** 

```sql
SELECT
title, COUNT(title) AS Rentals
FROM film
JOIN inventory ON (film.film_id = inventory.film_id)
JOIN rental ON (inventory.inventory_id = rental.inventory_id)
GROUP by title
ORDER BY rentals DESC
LIMIT 100
```


---

### 연습문제16 (실전)
**각 스토어별로 매출을 확인하고 싶습니다. 관련 데이터를 출력해주세요** 
**스토어가 위치한 '도시, 국가'를 Store 항목으로, 스토어 ID를 Store ID로, 각 스토어별 총 매출을 'Total Sales' 항목으로 출력해주세요** 

```sql
SELECT
CONCAT(ct.city, ', ', c.country) AS 'Store',
st.store_id AS 'Store ID',
SUM(amount) AS 'Total Sales'
FROM payment p
JOIN staff sf ON sf.staff_id = p.staff_id
JOIN store st ON st.store_id = sf.store_id
JOIN address a ON a.address_id = st.address_id
JOIN city ct ON ct.city_id = a.city_id
JOIN country c ON c.country_id = ct.country_id
GROUP BY st.store_id;
```


---

### 연습문제17 (실전)
**각 스토어의 스토어 ID, 도시, 및 국가를 알고싶습니다. 관련 데이터를 출력해주세요 store_id, city, country 로 보고 싶습니다.** 

```sql
SELECT store_id, city, country
FROM store s
JOIN address a ON s.address_id = a.address_id
JOIN city cit ON cit.city_id = a.city_id
JOIN country ctr ON cit.country_id = ctr.country_id
```


---

### 연습문제18 (실전)
**가장 렌탈비용을 많이 지불한 상위 10명에게 선물을 배송하고자 합니다. 가장 렌탈비용을 많이 지불한 상위 10명의 주소(address)와 이메일, 그리고 각 고객당 총 지불 비용을 출력해주세요** 

```sql
SELECT
CONCAT(c.first_name, ' ',c.last_name) as customer_name,
SUM(p.amount) as total_amount,
a.address,
c.email
FROM payment as p
JOIN customer as c ON p.customer_id = c.customer_id
JOIN address as a ON a.address_id = c.address_id
GROUP BY p.customer_id
ORDER BY sum(p.amount) DESC
LIMIT 10;
```


---

### 연습문제19 (실전)
**actor 테이블의 배우 이름을 first name 과 last name 을 대문자로 Actor Name 항목으로 출력해주세요** 

```sql
SELECT UPPER(CONCAT(first_name, ' ', last_name)) AS 'Actor Name' FROM actor;
```


---

### 연습문제20 (실전)
**언어가 영어 인 영화 중, 영화 타이틀이 K와 Q로 시작하는 영화의 타이틀만 출력해주세요 (서브쿼리를 사용해보세요)** 

```sql
SELECT title
FROM film
WHERE language_id IN (
SELECT language_id FROM language
WHERE name = 'English'
) AND (title LIKE 'K%' OR title LIKE 'Q%');
```


---

### 연습문제21 (실전)
**Alone Trip 에 나오는 배우 이름을 모두 출력하세요 (배우 이름은 actor_name 항목으로 출력해주세요. 서브쿼리를 사용하여보세요)** 

```sql
SELECT CONCAT(first_name, ' ', last_name) as actor_name FROM actor
WHERE actor_id IN
(SELECT actor_id FROM film_actor WHERE film_id IN
(SELECT film_id FROM film WHERE title = 'Alone Trip'))
```


---

### 연습문제22 (실전)
**2005년 8월에 각 스태프 멤버가 올린 매출을 스태프 멤버는 Staff Member 항목으로, 매출은 Total Amount 항목으로 출력해주세요.** 

```sql
SELECT
CONCAT(s.first_name, ' ',s.last_name) AS 'Staff Member',
SUM(p.amount) AS 'Total Amount'
FROM payment p
JOIN staff s ON p.staff_id=s.staff_id
WHERE payment_date like '2005-08%'
GROUP BY p.staff_id;
```


```sql
SELECT
CONCAT(S.first_name, ' ', S.last_name) AS 'Staff Member',
SUM(P.amount) AS 'Total Amount'
FROM payment P
JOIN staff S ON P.staff_id = S.staff_id
WHERE
EXTRACT(YEAR FROM P.payment_date) = 2005 AND
EXTRACT(MONTH FROM P.payment_date) = 8
GROUP BY P.staff_id
```


---

### 연습문제23 (실전)
**각 카테고리의 평균 영화 러닝타임이 전체 평균 러닝타임보다 큰 카테고리들의 카테고리명과 해당 카테고리의 평균 러닝타임을 출력하세요** 

```sql
SELECT CA.name, AVG(FI.length)
FROM film FI
JOIN film_category FC ON FI.film_id = FC.film_id
JOIN category CA ON CA.category_id = FC.category_id
GROUP BY CA.name
HAVING AVG(FI.length) > (
SELECT AVG(length) FROM film
);
```


---

### 연습문제24 (실전)
**각 카테고리별 평균 영화 대여 시간 (영화 대여 및 반납 시간의 차이, hour 단위)과 해당 카테고리명을 출력하세요** 

```sql
SELECT
CA.name,
AVG(TIMESTAMPDIFF(HOUR, RE.rental_date, RE.return_date)) AS avg_rental_duration
FROM rental RE
JOIN inventory INV ON RE.inventory_id = INV.inventory_id
JOIN film_category FC ON INV.film_id = FC.film_id
JOIN category CA ON CA.category_id = FC.category_id
GROUP BY CA.name;
```


---

### 연습문제25 (실전)
**새로운 임원이 부임했습니다. 총 매출액 상위 5개 장르의 매출액을 수시로 확인하고자 합니다. Total Sales (각 장르별 총 매출액)과 Genre (각 장르 이름) 으로 해당 데이터를 수시로 확인할 수 있는 view 를 top5_genres 로 만들고, 현재까지의 상위 5장르의 매출액을 출력해주세요** 

```sql
CREATE OR REPLACE VIEW top5_genres AS
SELECT C.name AS 'Genre', SUM(amount) AS 'Total Sales'
FROM payment P
JOIN rental R ON R.rental_id = P.rental_id
JOIN inventory I ON I.inventory_id = R.inventory_id
JOIN film_category F ON F.film_id= I.film_id
JOIN category C ON C.category_id = F.category_id
GROUP BY C.name
ORDER BY SUM(amount) DESC
LIMIT 5;
```


```sql
SELECT * FROM top5_genres
```


---

### 연습문제26 (실전)
**top5_genres view를 삭제해주세요** 

```sql
DROP VIEW top5_genres
```


---

### 연습문제27 (실전)
**2005년 5월에 가장 많이 대여된 영화 3개를 찾으세요. 영화 제목과 대여 횟수를 보여주세요.** 

```sql
SELECT
f.title,
COUNT(*) as rental_count
FROM
rental r
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id
WHERE
MONTH(r.rental_date) = 5 AND
YEAR(r.rental_date) = 2005
GROUP BY
f.title
ORDER BY
rental_count DESC
LIMIT 3;
```


---

### 연습문제28 (실전)
**대여된 적이 없는 영화를 찾으세요.** 

```sql
# 다음 쿼리는 하나의 영화가 여러 inventory 를 가졌을 때, 그 중 하나의 inventory 라도 대여되지 않았다면, 해당 영화 타이틀도 출력함
SELECT
f.title
FROM
film f
LEFT OUTER JOIN inventory i ON f.film_id = i.film_id
LEFT OUTER JOIN rental r ON i.inventory_id = r.inventory_id
WHERE
r.rental_id IS NULL;
```


```sql
#위 쿼리를 보완하기 위해, 다음과 같이 작성 가능
SELECT
f.title
FROM
film f
LEFT JOIN
inventory i ON f.film_id= i.film_id
LEFT JOIN
rental r ON i.inventory_id = r.inventory_id
GROUP BY
f.title
HAVING
COUNT(r.rental_id) = 0;
```


```sql
#또는 다음과 같이 작성도 가능
SELECT title FROM film
WHERE film_id NOT IN (
SELECT DISTINCT(I.film_id) FROM rental R
JOIN inventory I ON R.inventory_id = I.inventory_id
);
```

### 연습문제29 (실전)
**각 고객의 총 지출 금액의 평균 보다 총 지출 금액이 더 큰 고객 리스트를 찾으세요. 그들의 이름과 그들이 지출한 총 금액을 보여주세요.** 

-   각 고객의 총 지출 금액 계산 방법: 
    -   고객 A 5번 렌트, 총 100$ 
    -   고객 B 3번 렌트, 총 80$ 
    -   고객당 평균 지출: 90$

---
```SQL
SELECT
c.first_name,
c.last_name,
SUM(p.amount) as total_spent
FROM
payment p
JOIN customer c ON p.customer_id = c.customer_id
GROUP BY
c.customer_id
HAVING
total_spent > (SELECT AVG(sum_amount) FROM (SELECT SUM(amount) as sum_amount FROM payment GROUP BY customer_id) as sub_query);
```

---

### 연습문제30 (실전)
**가장 많은 결제를 처리한 직원이 누구인지 찾으세요.** 

```sql
SELECT
s.staff_id,
s.first_name,
s.last_name,
COUNT(*) as payment_count
FROM
staff s
JOIN payment p ON s.staff_id = p.staff_id
GROUP BY
s.staff_id
ORDER BY
payment_count DESC
LIMIT 1;
```


---

### 연습문제31 (실전)
**'액션' 카테고리에서 높은 영화 영상 등급을 받은 순으로, 상위 5개의 영화를 보여주세요. (높은 영화 영상 등급 순으로의 정렬은 ORDER BY rating DESC 으로 처리 가능)** 

```sql
SELECT
f.title,
f.rating
FROM
film f
JOIN film_category fc ON f.film_id = fc.film_id
JOIN category c ON fc.category_id = c.category_id
WHERE
c.name = 'Action'
ORDER BY
f.rating DESC
LIMIT 5;
```


---

### 연습문제32 (실전)
**각 영화 영상등급의 영화별 대여 기간(film.rental_duration)의 평균을 찾으세요.** 

```sql
SELECT
f.rating,
AVG(f.rental_duration) as avg_duration
FROM
film f
GROUP BY
f.rating;
```


---

### 연습문제33 (실전)
**매장 ID별 총 매출을 보여주는 뷰를 생성하세요.** 

```sql
CREATE VIEW total_sales_by_store AS
SELECT
s.store_id,
SUM(p.amount) as total_sales
FROM
store s
JOIN staff st ON s.store_id = st.store_id
JOIN payment p ON st.staff_id = p.staff_id
GROUP BY
s.store_id;
```


---

### 연습문제34 (실전)
**이전 연습문제에서 생성한 뷰를 삭제하세요.** 

```sql
DROP VIEW total_sales_by_store;
```


---

### 연습문제35 (실전)
**가장 많은 고객이 있는 상위 5개 국가를 보여주세요.** 

```sql
SELECT
co.country,
COUNT(*) as customer_count
FROM
country co
JOIN city ci ON co.country_id = ci.country_id
JOIN address a ON ci.city_id = a.city_id
JOIN customer cu ON a.address_id = cu.address_id
GROUP BY
co.country
ORDER BY
customer_count DESC
LIMIT 5;
```


---

### 연습문제36 (실전)
**각 고객이 어떤 영화 카테고리를 가장 자주 대여하는지 알고 싶습니다. 각 고객별로 가장 많이 대여한 영화 카테고리와 해당 카테고리에서의 총 대여 횟수, 그리고 해당 고객 이름을 조회하는 SQL 쿼리를 작성해주세요. 자주 대여하는 카테고리에 동률이 있을 경우 모두 보여주세요.** 

```sql
SELECT
c.first_name,
c.last_name,
cat.name as category_name,
COUNT(*) as rental_count
FROM
customer c
JOIN rental r ON c.customer_id = r.customer_id
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film_category fc ON i.film_id = fc.film_id
JOIN category cat ON fc.category_id = cat.category_id
GROUP BY
c.customer_id,
cat.name
HAVING
COUNT(*) = (
SELECT
COUNT(*)
FROM
rental r2
JOIN inventory i2 ON r2.inventory_id = i2.inventory_id
JOIN film_category fc2 ON i2.film_id = fc2.film_id
WHERE
r2.customer_id = c.customer_id
GROUP BY
fc2.category_id
ORDER BY
COUNT(*) DESC
LIMIT 1
)
```


---

### 연습문제37 (실전)
**2006-02-14 날짜를 기준으로, 2006-01-15일(이전 30일) 부터, 2006-02-14 날짜까지 영화를 대여하지 않은 고객을 찾으세요.** 

```sql
SELECT
c.customer_id,
c.first_name,
c.last_name
FROM
customer c
LEFT JOIN rental r ON c.customer_id = r.customer_id AND TIMESTAMPDIFF(DAY, r.rental_date, '2006-02-14') <= 30
WHERE
r.rental_id IS NULL;
```


---

### 연습문제38 (실전)
**가장 최근에 영화를 반납한 상위 10명의 고객 이름과 그들이 대여한 영화의 이름, 그리고 대여 기간을 출력해 주세요. 고객 이름은 customer_name, 영화 이름은 movie_title, 대여 기간은 rental_duration으로 출력해주세요.** 

```sql
SELECT
CONCAT(c.first_name, ' ', c.last_name) AS customer_name,
f.title AS movie_title,
TIMESTAMPDIFF(DAY, r.rental_date, r.return_date) AS rental_duration
FROM
rental r
JOIN
customer c ON r.customer_id = c.customer_id
JOIN
inventory i ON r.inventory_id = i.inventory_id
JOIN
film f ON i.film_id = f.film_id
ORDER BY
r.return_date DESC
LIMIT 10;
```


---

### 연습문제39 (실전)
**각 직원의 매출을 찾고, 각 직원의 매출이 전체 매출 중 어느 정도 비율을 차지하는지 찾으세요. 결과는 직원 ID, 직원 이름, 총 매출, 전체 매출에 대한 비율(%)로 보여주세요.** 

```sql
SELECT
s.staff_id,
CONCAT(s.first_name, ' ', s.last_name) AS staff_name,
SUM(p.amount) as staff_revenue,
(SUM(p.amount) / (SELECT SUM(amount) FROM payment) * 100) as revenue_percentage
FROM
payment p
JOIN
staff s ON p.staff_id=s.staff_id
GROUP BY
s.staff_id;
```


---

### 연습문제40 (실전)
**가장 많은 수의 종류가 다른(동일 영화를 반복하여 대여하지 않고) 영화를 대여한 고객을 찾아내고, 대여한 종류가 다른 (동일 영화를 반복하여 대여하지 않고) 영화의 수를 확인하세요. 또한 해당 고객이 대여한 영화(여기서는 동일 영화 반복 대여도 가능)가 가장 많이 속해있는 카테고리를 찾아내세요.** 

```sql
SELECT
cus.customer_id,
CONCAT(cus.first_name, ' ',cus.last_name) AS customer_name,
COUNT(DISTINCT inv.film_id) AS unique_films_rented,
(
SELECT cat.name
FROM category cat
JOIN film_category fc ON cat.category_id = fc.category_id
JOIN inventory inv2 ON fc.film_id = inv2.film_id
JOIN rental ren2 ON inv2.inventory_id = ren2.inventory_id
WHERE ren2.customer_id = cus.customer_id
GROUP BY cat.name
ORDER BY COUNT(*) DESC
LIMIT 1
) AS most_common_category
FROM
customer cus
JOIN
rental ren ON ren.customer_id = cus.customer_id
JOIN
inventory inv ON ren.inventory_id = inv.inventory_id
GROUP BY
cus.customer_id
ORDER BY
unique_films_rented DESC
LIMIT 1;
```


**카테고리별 대여한 영화 수가 최대인 카테고리가 여러개인 경우, 이를 모두 출력하는 쿼리** 
```sql
SELECT
C.customer_id,
C.first_name, C.last_name,
COUNT(DISTINCT I.film_id) AS unique_films_rented,
(
    SELECT GROUP_CONCAT(name ORDER BY name)
    FROM (
        SELECT name, COUNT(*) AS category_count
        FROM category C2
        JOIN film_category FC2 ON C2.category_id = FC2.category_id
        JOIN inventory I2 ON FC2.film_id = I2.film_id
        JOIN rental R2 ON I2.inventory_id = R2.inventory_id
        WHERE R2.customer_id = C.customer_id
        GROUP BY name
    ) AS category_counts
    WHERE category_count = (
        SELECT MAX(category_count3)
        FROM (
            SELECT COUNT(*) AS category_count3
            FROM category C3
            JOIN film_category FC3 ON C3.category_id = FC3.category_id
            JOIN inventory I3 ON FC3.film_id=I3.film_id
            JOIN rental R3 ON I3.inventory_id = R3.inventory_id
            WHERE R3.customer_id = C.customer_id
            GROUP BY C3.name
        ) AS category_counts3
    )
) AS most_common_categories
FROM rental R
JOIN customer C ON C.customer_id = R.customer_id
JOIN inventory I ON I.inventory_id = R.inventory_id
GROUP BY C.customer_id
ORDER BY unique_films_rented DESC
LIMIT 1
```


**가장 많은 수의 종류가 다른 영화를 대여한 고객이 여러 명일 경우 그 고객들 모두를 출력하고, 각 고객이 대여한 영화가 가장 많이 속해있는 카테고리(여러 개인 경우 모두)를 출력하는 쿼리** 
```sql
WITH CustomerUniqueFilms AS (
    SELECT
    C.customer_id,
    CONCAT(C.first_name, ' ', C.last_name) AS customer_name,
    COUNT(DISTINCT I.film_id) AS unique_films_rented
    FROM rental R
    JOIN inventory I ON R.inventory_id = I.inventory_id
    JOIN customer C ON C.customer_id = R.customer_id
    GROUP BY C.customer_id
),
MaxUniqueFilms AS (
    SELECT MAX(unique_films_rented) AS max_unique_films
    FROM CustomerUniqueFilms
)
SELECT
cuf.customer_id, cuf.customer_name, cuf.unique_films_rented,
(
    SELECT GROUP_CONCAT(name ORDER BY name)
    FROM (
        SELECT name, COUNT(*) AS category_count
        FROM category CAT
        JOIN film_category FC ON CAT.category_id = FC.category_id
        JOIN inventory INV ON FC.film_id = INV.film_id
        JOIN rental REN ON REN.inventory_id = INV.inventory_id
        WHERE REN.customer_id = cuf.customer_id
        GROUP BY CAT.name
    ) AS inner_cat
    WHERE category_count = (
        SELECT MAX(category_count2)
        FROM (
            SELECT COUNT(*) AS category_count2
            FROM category CAT2
            JOIN film_category FC2 ON CAT2.category_id = FC2.category_id
            JOIN inventory INV2 ON FC2.film_id = INV2.film_id
            JOIN rental REN2 ON REN2.inventory_id = INV2.inventory_id
            WHERE REN2.customer_id = cuf.customer_id
            GROUP BY CAT2.name
        ) AS subquery_cat
    )
)
FROM CustomerUniqueFilms cuf
JOIN MaxUniqueFilms muf ON cuf.unique_films_rented = muf.max_unique_films
```

