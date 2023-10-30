# MySQL
## MySQL과 Oracle의 차이점
MySQL은 오픈 소스이며 무료로 사용 가능하지만 Oracle은 상용 제품으로 라이센스 비용이 발생한다. <br><br>

쿼리문 입력방식은 서로 크게 다르지 않으며 주로 함수명이 다르다. <br><br>

## CREATE
Oracle
``` Oracle
CREATE TABLE mytable (
    id NUMBER PRIMARY KEY,
    name VARCHAR2(50)
);
```
MySQL
``` mysql
CREATE TABLE mytable (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50)
);
```
1. 가변형 캐릭터 데이터타입 [VARCHAR2 vs VARCHAR] <br>
가변형 캐릭터타입인 VARCHAR에 대해 오라클은 VARCHAR 뒤에 숫자2를 사용하는 반면, <br>
MySQL은 숫자없이 VARCHAR로 사용한다. <br><br>

2. 숫자형 데이터타입 [NUMBER vs INT]<br>
숫자형 데이터타입에 대해 오라클은 NUMBER를 사용하는 반면, MySQL은 INT로 사용한다.<br><br>

3. 날짜형 데이터타입 [SYSDATE vs DATETIME]<br>
숫자형 데이터타입에 대해 오라클은 SYSDATE를 사용하는 반면, MySQL은 DATETIME으로 사용한다.<br><br><br>

## ALTER
컬럼 추가 (Add) <br>
ALTER TABLE [테이블명] ADD COLUMN [컬럼명] varchar(32) NOT NULL; <br><br>

컬럼 변경 (Modify) <br>
ALTER TABLE [테이블명] MODIFY COLUMN [컬럼명] varchar(16) NULL; <br><br>

컬럼 이름까지 변경 (Change) <br>
ALTER TABLE [테이블명] CHANGE COLUMN [컬럼명] [바꿀 컬럼명] varchar(16) NULL; <br><br>

컬럼 삭제 (Drop) <br>
ALTER TABLE [테이블명] DROP COLUMN [컬럼명]; <br><br>

테이블 이름 변경 (RENAME) <br>
ALTER TABLE [테이블명] RENAME [바꿀 테이블명]; <br><br><br>


## Drop
DROP TABLE [테이블명] <br><br><br>


## SELECT
SELECT 필드이름 <br>
FROM 테이블이름 <br>
[WHERE 조건] <br><br><br>


## INSERT
1. INSERT INTO [테이블명](필드명1, 필드명2, 필드명3, ...) <br>
   VALUES (데이터값1, 데이터값2, 데이터값3, ...) <br><br>

2. INSERT INTO [테이블명] <br>
   VALUES (데이터값1, 데이터값2, 데이터값3, ...) <br><br><br>


## UPDATE
UPDATE 테이블명 <br>
SET 필드명1=데이터값1, 필드명2=데이터값2, ... <br>
WHERE 필드명=데이터값 <br><br><br>


## DELETE
DELETE FROM 테이블명 <br>
WHERE 필드명=데이터값 <br><br>

### 만약 WHERE 절을 생략하면, 해당 테이블에 저장된 모든 데이터가 삭제된다.
DELETE FROM 테이블이름; <br><br><br>


## INDEX
CREATE INDEX [인덱스명] <br>
ON [테이블명] (필드명1, 필드명2, ...) <br><br>

### INDEX 조회
SHOW INDEX <br>
FROM [테이블명] <br><br>

### UNIQUE INDEX 생성
CREATE UNIQUE INDEX [인덱스명] <br>
ON [테이블명] (필드명1, 필드명2, ...) <br><br><br>


# 제약조건
MySQL에서 사용할 수 있는 제약 조건은 다음과 같습니다. <br><br>

1. NOT NULL <br>
2. UNIQUE <br>
3. PRIMARY KEY <br>
4. FOREIGN KEY <br>
5. DEFAULT <br><br>

## NOT NULL
CREATE 문으로 테이블을 생성할 때 해당 필드의 타입 뒤에 NOT NULL을 명시하면, 해당 필드는 NULL 값을 가질 수 없다. <br><br>

CREATE TABLE 테이블이름 (필드이름 필드타입 NOT NULL, ...) <br><br>

## UNIQUE
UNIQUE 제약 조건을 설정하면, 해당 필드는 서로 다른 값을 가져야 한다. <br>
즉, 이 제약 조건이 설정된 필드는 중복된 값을 저장할 수 없다. <br><br>

1. CREATE TABLE 테이블이름 (필드명 필드타입 UNIQUE, ...) <br><br>

2. CREATE TABLE 테이블이름 (필드이름 필드타입, ..., [CONSTRAINT 제약조건이름] UNIQUE (필드이름)) <br><br><br>


## PRIMARY KEY
PRIMARY KEY 제약 조건을 설정하면, 해당 필드는 NOT NULL과 UNIQUE 제약 조건의 특징을 모두 가진다. <br><br>

1. CREATE TABLE 테이블이름 (필드이름 필드타입 PRIMARY KEY, ...) <br><br>

2. CREATE TABLE 테이블이름 (필드이름 필드타입, ..., [CONSTRAINT 제약조건이름] PRIMARY KEY (필드이름)) <br><br><br>


## FOREIGN KEY
FOREIGN KEY 제약 조건을 설정한 필드는 외래 키라고 부르며, 한 테이블을 다른 테이블과 연결해주는 역할을 한다. <br>
외래 키가 설정된 테이블에 레코드를 입력하면, 기준이 되는 테이블의 내용을 참조해서 레코드가 입력된다. <br>
즉, FOREIGN KEY 제약 조건은 하나의 테이블을 다른 테이블에 의존하게 만든다. <br><br>

CREATE TABLE 테이블이름 (필드이름 필드타입, ..., [CONSTRAINT 제약조건이름] FOREIGN KEY (필드이름) REFERENCES 테이블이름 (필드이름)) <br><br><br>


