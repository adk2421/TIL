# DateBase
### 데이터베이스
`데이터베이스(DB: Database)`란 여러 사람에 의해 공유되어 사용될 목적으로 **통합하여 관리되는 데이터의 집합**을 말합니다.<br>
데이터의 **중복을 없애고 구조화하여 저장함**으로써, 데이터 검색과 갱신의 효율을 높입니다.

<br>

> <b>데이터베이스의 특징</b>
- 사용자의 질의에 대하여 **즉각적인 처리와 응답**이 이루어집니다.
- 생성, 수정, 삭제를 통해 항상 **최신의 데이터를 유지**합니다.
- 사용자들이 원하는 **데이터를 동시에 공유**할 수 있습니다.
- 사용자가 원하는 데이터를 주소가 아닌 **내용에 따라 참조**할 수 있습니다.
- 응용프로그램과 데이터베이스는 독립되어 있으므로, 데이터의 논리적 구조와 응용프로그램은 **별개로 동작**됩니다.

<br>

> <b>데이터베이스 용어</b>
- 식별자(Identifier) : 여러 개의 집합체를 담고있는 관계형 데이터베이스에서 각각을 구분할 수 있는 논리적인 개념
```
식별자의 특성
- 유일성 : 하나의 릴레이션에서 모든 행은 서로 다른 키 값을 가져야 합니다.
- 최소성 : 꼭 필요한 최소한의 속성들로만 키를 구성해야 합니다.
```
- **튜플(Tuple)** : 테이블에서 행을 의미하며, 레코드(Record) 혹은 로우(Row)라고 부르기도 합니다. 튜플의 수는 카디널리티(Cardinality)라고 합니다. 
- **어트리뷰트(Attribute)** : 테이블에서 열을 의미하며, 컬럼(Column)이라고 부르기도 합니다. 어트리뷰트 수를 의미하는 단어는 디그리(Degree)입니다.

<br>

# DBMS
데이터베이스는 응용 프로그램과는 다른 별도의 미들웨어에 의해 관리됩니다.<br>
데이터베이스를 관리하는 이러한 미들웨어를 `데이터베이스 관리 시스템(DBMS: Database Management System)`이라고 합니다.<br>

다양한 데이터가 저장되어 있는 데이터베이스는 여러 명의 사용자나 응용 프로그램과 공유하고 동시에 접근이 가능해야 합니다.

<br>

> <b>대표적인 DBMS 종류</b>

|DBMS|제작사|작동 운영체제|특징|
|:--:|:---:|:-----------:|:-:|
|Oracle|Oracle|Unix, Linux, Windows|상용 시장 점유율 1위|
|MySQL|Oracle|Unix, Linux, Windows, Mac|오픈소스(무료), 상용|
|SQL Server|Microsoft|Windows|주로 중/대형급 시장에서 사용|
|MariaDB|MariaDB|Unix, Linux, Windows|오픈소스(무료), MySQL 초기 개발자들이 독립해서 제작|
|PostgreSQL|PostgreSQL|Unix, Linux, Windows, Mac|오픈소스(무료)|
|DB2|IBM|Unix, Linux, Windows|메인프레임 시장 점유율 1위|
|Access|Microsoft|Windows|PC용|
|SQLite|SQLite|Android, iOS|오픈소스(무료), 모바일 전용|

<br>

# SQL
`SQL(Structured Query Language)`은 관계형 데이터베이스 시스템(RDBMS)에서 자료를 관리 및 처리하기 위해 설계된 언어입니다.

<br>

> <b>SQL 문법의 종류</b>

SQL 문법은 크게 3가지 종류로 나누어지며, 종류마다 정의는 아래와 같습니다.

- DDL(Data Definition Language, 데이터 정의 언어)<br>
  각 <b>릴레이션을 정의</b>하기 위해 사용하는 언어입니다. (CREATE, ALTER, DROP 등)
  
- DML(Data Manipulation Language, 데이터 조작 언어)<br>
  데이터를 조회하거나 변경하기 위한, 즉 <b>데이터 관리</b>를 위한 언어입니다. (SELECT, INSERT, UPDATE, DELETE 등)
  
- DCL(Data Control Language, 데이터 제어 언어)<br>
  사용자 관리, 릴레이션 또는 데이터를 관리하고 접근하는 사용자들의 <b>권한 설정</b>을 위한 언어입니다. (GRANT, REVOKE 등)
  
<br>

> <b>SQL의 언어적 특성</b>

- SQL은 **대소문자**를 가리지 않습니다<br>
  (단, 서버 환경이나 DBMS 종류에 따라 데이터베이스 또는 필드명에 대해 대소문자를 구분하기도 합니다.)
  
- SQL 명령은 반드시 <b>세미콜론(&#59;)</b>으로 끝나야 합니다.<br>
- 고유의 값은 <b>따옴표(&#39;)</b>로 감싸줍니다.<br>
  ```SQL
  SELECT * FROM EMP WHERE NAME = 'john';
  ```
  
- SQL에서 객체를 나타낼 때는 <b>백틱(&#96;)</b>으로 감싸줍니다.<br>
  ```SQL
  SELECT `COST`, `TYPE` FROM `INVOICE`;
  ```
- 주석은 일종의 도움말로, <b>주석 처리된 문장은 프로그램에서 동작하지 않습니다.</b> 한 줄 주석: '&#8211;&#8211;', 여러 줄 주석: '&#47;&#42; &#42;&#47;'<br>
  ```SQL
  -- SELECT * FROM EMP; 실행 X
  
  /*
  SELECT * FROM EMP
  SELECT * FROM DEPT
  */
  ```

<br>
<hr>

### 참조

- TCP School - http://www.tcpschool.com/mysql/DB
- 코딩팩토리 - https://coding-factory.tistory.com/77
- 혼공 - https://hongong.hanbit.co.kr/데이터베이스-이해하기-databasedb-dbms-sql의-개념/
- goormedu - https://edu.goorm.io/learn/lecture/15413/한-눈에-끝내는-sql/lesson/767683/sql이란
