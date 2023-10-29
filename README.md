# MySQL
## MySQL과 Oracle의 차이점
MySQL은 오픈 소스이며 무료로 사용 가능하지만 Oracle은 상용 제품으로 라이센스 비용이 발생한다. <br><br>

## create
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
1. 가변형 캐릭터 데이터타입 [VARCHAR2 vs VARCHAR] <br><br>

가변형 캐릭터타입인 VARCHAR에 대해 오라클은 VARCHAR 뒤에 숫자2를 사용하는 반면, <br>
MySQL은 숫자없이 VARCHAR로 사용. <br><br>

2. 숫자형 데이터타입 [NUMBER vs INT]<br><br>

숫자형 데이터타입에 대해 오라클은 NUMBER를 사용하는 반면, MySQL은 INT로 사용.<br><br>

3. 날짜형 데이터타입 [SYSDATE vs DATETIME]<br><br>

숫자형 데이터타입에 대해 오라클은 SYSDATE를 사용하는 반면, MySQL은 DATETIME으로 사용.<br><br><br>

## alter
# 컬럼 추가 (Add) <br>
ALTER TABLE table_name ADD COLUMN ex_column varchar(32) NOT NULL; <br><br>

컬럼 변경 (Modify) <br>
ALTER TABLE table_name MODIFY COLUMN ex_column varchar(16) NULL; <br><br>

컬럼 이름까지 변경 (Change) <br>
ALTER TABLE table_name CHANGE COLUMN ex_column ex_column2 varchar(16) NULL; <br><br>

컬럼 삭제 (Drop) <br>
ALTER TABLE table_name DROP COLUMN ex_column; <br><br>

테이블 이름 변경 (RENAME) <br>
ALTER TABLE table_name1 RENAME table_name2; <br><br><br>


## Drop
``` MySQL
DROP TABLE mytable;
```
