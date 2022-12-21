# 데이터 정의어
`DDL(Data Definition Language)` 은 데이터베이스를 정의하는 언어를 말하며 데이터를 생성하거나 수정, 삭제 등 데이터의 전체 골격을 결정하는 역할의 언어를 말합니다.

<br>

> ### 명령어 종류
- **CREATE** : 데이터베이스, 테이블 등을 생성하는 역할
- **ALTER** : 테이블을 수정하는 역할
- **DROP** : 데이터베이스, 테이블을 삭제하는 역할
- **TRUNCATE** : 테이블을 초기화 시키는 역할

<br>

# CREATE
### 데이터베이스 생성
```sql
CREATE DATABASE [database];

CREATE DATABASE Korea;
```
> 생성된 데이터베이스 목록은 ```SHOW DATABASES``` 구문을 통해 확인할 수 있습니다.
<br>

### 데이터베이스 선택
- 데이터베이스 생성 후, 데이터베이스를 사용하기 위해서는 데이터베이스를 선택해야 합니다.
```sql
USE [database];

USE Korea;
```
> MySQL은 **Windows** 환경에서 데이터베이스 이름에 대해 대소문자를 구분하지 않고, **UNIX** 환경에서는 대소문자를 구분합니다.
<br>

### 테이블 생성
- 데이터베이스는 하나 이상의 테이블로 구성되며, 이러한 테이블에 데이터를 저장하고 관리할 수 있습니다.
```sql
CREATE TABLE (
    [column_name1] [column_type1],
    [column_name2] [column_type2],
    ...
)

CREATE TABLE (
    Name VARCHAR(30),
    Age INT
)
```
> 위의 문법처럼 하나의 쿼리를 여러 줄에 걸쳐 입력할 수 있습니다.
<br>

### 제약 조건
<b>제약 조건(constraint)</b>이란 데이터의 무결성을 지키기 위해서 데이터를 입력받을 때 실행되는 검사 규칙을 의미합니다.<br>
이러한 제약 조건은 `CREATE` 문으로 테이블을 생성할 때나, `ALTER` 문으로 필드를 추가할 때도 설정할 수 있습니다.

<br>

> #### 제약 조건 종류
- **NOT NULL** : 해당 필드는 `NULL` 값을 저장할 수 없게 됩니다.
- **UNIQUE** : 해당 필드는 서로 다른 값을 가져야만 합니다.
- **PRIMARY KEY** : 해당 필드가 NOT NULL과UNIQUE 제약 조건의 특징을 모두 가지게 됩니다.
- **FOREIGN KEY** : 하나의 테이블을 다른 테이블에 의존하게 만듭니다.
- **DEFAULT** : 해당 필드의 기본값을 설정합니다.

```sql
CREATE TABLE (
    ID VARCHAR(20) PRIMARY KEY,
    NO INT UNIQUE,
    Name VARCHAR(30) NOT NULL,
    Age INT DEFAULT 20
)
```
> MySQL은 
<br>
<hr>

### 참조
TCP School - http://www.tcpschool.com/mysql/mysql_intro_intro <br>
슬기로운 개발생활 - https://dev-coco.tistory.com/55
