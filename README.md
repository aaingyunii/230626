# Bootcamp_SQL

### 230626_SQL기초_Python연동 🐍💪
### 수업 내용 : 

#### ✔ 이전 수업 내용 복습
#### ✔ SQL 기초 학습 및 Python 연동 실습

#### ➕ [PlanetScale](https://planetscale.com/)
#### ➕ [Supabase](https://supabase.com/)
#### 🔗[TIL](https://github.com/aaingyunii/Bootcamp_TIL/issues/14)


# SQL 기초

### SQL CRUD
- CREATE
 ```
 CREATE TABLE 테이블명 (
      column 데이터타입
      ...
);
 ```
- SELECT
```
SELECT * FROM 테이블 명;
SELECT colunm1, column2, ... FROM 테이블명;
```
- INSERT
```
INSERT INTO 테이블명 (column1, column2, ...)
VALUES (value1, value2, ...);
```
- UPDATE
```
UPDATE 테이블명 SET column1 = changing_value
WHERE 조건문;
```
- DELETE
```
DELETE FROM 테이블명 WHERE 조건문;
```
- ALTER
```
ALTER TABLE 테이블명
ADD COLUNM 컬럼명 데이터 타입; # 열 추가

DROP COLUNM 컬럼명; # 열 삭제

MODIFY 컬럼명 NEW_데이터타입; # 데이터 타입 변경
```

**파이썬 보다 직관적이다.**

## 정렬과 그룹화
- ORDER BY
 ```
SELECT *
FROM 테이블명
ORDER BY 컬럼명 ASC(오름차순);
               DESC(내림차순);
```
- GROUP BY : 데이터 그룹화
```
SELECT column1, column2, ...
FROM 테이블명
GROUP BY 컬럼명;
```
- COUNT : 그룹 내 레코드 수를 계산
```
SELECT COUNT("컬럼명")
FROM 테이블명;
```
- SUM : 그룹 내 열의 합계를 계산
```
SELECT SUM("컬럼명")
FROM 테이블명;
```
- AVG : 그룹 내 열의 평균을 계산
```
SELECT AVG("컬럼명")
FROM 테이블명;
```
## JOIN
> 다중 테이블 연결하기 (JOIN) : 2개 이상의 테이블을 연결하여 관련 데이터를 가져오는 방법<br>
> - **INNER JOIN** : 두 테이블 간의 일치하는 데이터만 가져옵니다.<br>
> - **LEFT JOIN** : 왼쪽 테이블의 모든 데이터와 오른쪽 테이블의 일치하는 데이터를 가져옵니다.<br>
> - **RIGHT JOIN** : 오른쪽 테이블의 모든 데이터와 왼쪽 테이블의 일치하는 데이터를 가져옵니다.<br>


- INNER JOIN
    - USING
- LEFT JOIN
- RIGHT JOIN
```
SELECT table1.column1, table2.column2
FROM table1
INNER JOIN table2 ON 조건식;
LEFT JOIN table2 ON 조건식;
RIGHT JOIN table2 ON 조건식;
                  USING (KEY);
```


## Planetscale, MySQL 환경 사용

- **`Planetscale`**
 ![image](https://github.com/aaingyunii/230626/assets/31847834/b8b98e1e-cd39-4521-aba9-0a969fe2f8c7)

- **`MySQL`**
![image](https://github.com/aaingyunii/Bootcamp_SQL/assets/31847834/b1514b02-b7b0-4df1-a8ab-1edbebaa3831)



### Python 연동
```python
!pip install pymysql -q
import pymysql

# SQL 데이터베이스 연결 설정
connection = pymysql.connect(
    host='your_host', # DB의 저장위치, IP주소
    port=your_port,   #
    user='your_username',
    password='your_password',
    database='your_database',
    ssl_ca='/etc/ssl/certs/ca-certificates.crt',
)

connection.close()
```


  
