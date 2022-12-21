# MySQL
`MySQL`은 가장 널리 사용되고 있는 관계형 데이터베이스 관리 시스템(RDBMS: Relational DBMS)입니다.

다중 사용자와 다중 스레드를 지원하며, 오픈 소스이기 때문에 무료로 사용 가능하지만,<br>
상업적으로 사용할 때는 상업용 라이센스를 구입해야 합니다.

<br>

> <b>MySQL의 특징</b>
- 다양한 운영체제에서 사용할 수 있으며, 여러 가지의의 프로그래밍 언어를 지원합니다.
- 크기가 큰 데이터 집합도 아주 빠르고 효과적으로 처리할 수 있습니다.
- 널리 알려진 표준 SQL 형식을 사용합니다.
- MySQL 응용 프로그램을 사용자의 용도에 맞게 수정할 수 있습니다.

<br>

# 기본 문법
### MySQL 구문
- 데이터베이스에 대한 작업 명령은 SQL 구문을 이용합니다.
```sql
SELECT [column] FROM [table];

SELECT [column] FROM [table] WHERE [condition];
```
> 세미콜론(;)은 SQL 구문을 구분하는 기준이 됩니다.
<br>

- 키워드와 구문은 대소문자 구분을 하지 않습니다. (컬럼명과 테이블명은 대소문자를 구분하므로, 주의해야 합니다.)
```sql
1. SELECT SON FROM KOREA;

2. select SON from KOREA;

3. sElEcT SON fRoM KOREA;
```
> 모두 같은 결과가 나오지만, 되도록 1번이나 2번처럼 대소문자를 일관되게 사용하는 것이 좋습니다.
<br>

### MySQL 주석
- 코드에 대한 설명이나 디버깅을 위해 작성하는 일종의 메모입니다.
```sql
1. # 한 줄 주석

2. -- 한 줄 주석

3. /* 두 줄
      이상의
      주석 */
```
> MySQL 서버는 주석을 무시하므로, 실제 실행 결과에는 아무런 영향을 주지 않습니다.

<br>
<hr>
참조 : TCP School - http://www.tcpschool.com/mysql/mysql_intro_intro
