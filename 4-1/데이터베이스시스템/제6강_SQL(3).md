
# 6강 - SQL(3)

# SQL(3)

# 1. 데이터 정렬과 특수연산자

## 데이터의 정렬

- ORDER BY 절을 사용
    - ASC
    - DESC

## 특수연산자

- 범위, 부분 일치 여부, 포함 여부 등 RDBMS에서 사용되도록 고안된 연산자
    - BETWEEN
    - LIKE
    - IN

## 집합 연산자

- 테이블은 집합, 레코드는 집합에 포함된 원소
- 집합 이론에서의 이진 연산
    - 합집합 : UNION, UNION ALL
    - 교집합: INTERSECT
    - 차집합 : EXCEPT
- 집합 연산자 사용 조건
    - 테이블 R과 S의 차수 및 각 컬럼의 도메인이 일치
- 교집합 및 차집합은 지원하지 않는 상용 DBMS가 있어 NOT IN 등의 연산자를 사용하여 우회

# 2. 함수의 사용

## 숫자 함수

- 삼각함수, 상수, 올림과 버림, 난수 등
    - ABS()
    - SIN(), COS() 등
    - CEILING(), FLOOR()
    - LN() - 자연 로그
    - PI()
    - POWER(X,Y) - 거듭제곱 X^Y
    - RAND()
    - ROUND()
    - SQRT()
    - TRUNCATE()

## 문자 함수

- 문자열 조작 및 문자 형식 변환 등의 문자와 관련된 다양한 연산을 지원하는 함수
    - CHAR_LENGTH()
    - CONCAT()
    - LOWER()
    - UPPER()
    - SUBSTRING()
    - TRIM() / LTRIM() / RTRIM()

## 날짜 함수

- 날짜 및 시간 데이터 타입에 적용되어 산술연산 및 시간 형 변환 등의 조작을 위한 함수
    - ADDDATE(),
    - ADDTIME(),
    - CURDATE(), CURRENT_DATE()
    - CURTIME(), CURRENT_TIME()
    - DATE()
    - YEAR()

# 3. 집계 함수의 사용

## 집계함수

- 특정 컬럼에 집계함수를 통해 다양한 통계 연산을 수행할 수 있는 기능
- SELECT 절 또는 HAVING 절에 기술
- 집계함수의 종류
    - COUNT
    - SUM
    - AVG
    - MAX
    - MIN

## 그룹질의

- 특정 기준으로 레코드를 그룹화하고 각 레코드 그룹에 대해 집계 함수를 적용하는 질의
- [주의] SELECT 절에 그룹의 기준과 집계 함수 이외의 컬럼은 포함 불가능

## 조건 그룹 질의

- 그룹 질의의 결과 레코드에 대해 출력 조건을 기술하는질의
- SELECT GROUP BY HAVING
- 조건에 대한 기술
    - WHERE : 레코드에 대한 조건을 기술
    - HAVING : 집계 결과 레코드에 대한 조건을 기술