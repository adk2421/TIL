# REST API
<b>REST(REpresentational State Transfer) API</b>는 두 컴퓨터 시스템이 인터넷을 통해 <b>정보를 안전하게 교환</b>하기 위해 사용하는 인터페이스다.

<br/>

>## 1. REST 구성
- 자원(Resource) : URI

- 행위(Verb) : HTTP Method

- 표현(Representations)

<br/>
<br/>

>## 2. REST 특징
- <b>Uniform(유니폼 인터페이스)</b>

  - 유니폼 인터페이스는 URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일을 말한다.

- <b>Stateless(무상태성)</b>

  - REST는 무상태성 성격을 가진다. 다시 말해, 작업을 위한 상태 정보를 따로 저장하고 관리하지 않는다.

  - 세션이나 쿠키를 별도로 저장, 관리하지 않아 API 서버는 단순히 들어오는 요청만을 처리하면 되기 때문에 자유도가 높아지고 구현이 단순해진다.

- <b>Cacheable(캐시 가능)</b>
  - HTTP 기존 웹표준을 그대로 사용하기 때문에 웹에서 사용하는 기존 인프라를 그대로 활용 가능하다.

  - 따라서 HTTP가 가진 캐싱 기능을 적용할 수 있다.

- <b>Self-descriptiveness(자체 표현 구조)</b>
  - REST API 메시지만 보고도 이를 쉽게 이해할 수 있는 자체 표현 구조로 되어있다.

- <b>Client - Server 구조</b>
  - 서버는 API 제공, 클라이언트는 사용자 인증이나 컨텍스트(세션, 로그인 정보) 등을 직접 관리하는 구조로 되어있다.

  - 각각의 역할이 확실하게 구분되어 있어 서버와 클라이언트에서 개발해야 할 내용이 명확해지고 서로간 의존성이 줄어들게 된다.

- <b>계층형 구조</b>
  - REST 서버는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있고 PROXY, Gateway 같은 네트워크 기반의 중간매체를 사용할 수 있게 해준다.

<br/>
<br/>

>## 3. REST API 디자인 가이드
REST API 설계 시, 중요한 항목 2가지를 요약해보면 -
1. <b>URI는 정보의 자원을 표현해야 한다.</b>
2. <b>자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE)로 표현한다.</b>

<br/>

>### 3-1. REST API 중심 규칙

<b>URI는 정보의 자원을 표현해야 한다. (리소스명은 동사보다는 명사를 사용)</b>

- URI에 delete와 같은 행위에 대한 표현을 빼고 자원을 표현하는데 중점을 두어야 한다.
```java
GET /members/delete/1   (x)

DELETE /members/1       (o)
```
<br/>

- 회원 정보를 가져오는 URI
```java
GET /members/show/1     (x)

GET /members/1          (o)
```
<br/>

- 회원을 추가할 때
```java
GET /members/insert/2   (x)  - GET 메서드는 리소스 생성에 맞지 않습니다.

POST /members/2         (o)
```

### [참고] HTTP METHOD의 역할

POST, GET, PUT, DELETE 이 4가지의 Method를 가지고 CRUD를 할 수 있습니다.

|METHOD|역할|
|------|----|
|POST|POST를 통해 해당 URI를 요청하면 리소스를 생성합니다.|
|GET|GET를 통해 해당 리소스를 조회합니다. 리소스를 조회하고 해당 도큐먼트에 대한 자세한 정보를 가져온다.|
|PUT|PUT를 통해 해당 리소스를 수정합니다.|
|DELETE|DELETE를 통해 리소스를 삭제합니다.|

<br/>
<br/>

>### 3-2. URI 설계 시 주의할 점
- <b>슬래시 구분자(/)는 계층 관계를 나타내는 데 사용한다.</b>
```
http://restapi.example.com/houses/apartments

http://restapi.example.com/animals/mammals/whales
```
<br/>

- <b>URI 마지막 문자로 슬래시(/)를 포함하지 않는다.</b>
```
http://restapi.example.com/houses/apartments/ (x)

http://restapi.example.com/houses/apartments  (o)
```

- <b>하이픈(-)은 URI 가독성을 높이는데 사용한다.</b>

  - 불가피하게 긴 URI 경로를 사용하게 된다면 하이픈을 사용해 가독성을 높일 수 있다. (URI를 쉽게 이해 가능)

- <b>밑줄(\_)은 URI에 사용하지 않는다.</b>

  - 밑줄이 안보이거나 밑줄에 문자가 가려지는 경우가 있기 때문에 밑줄 대신 하이픈(-) 사용 권장 (가독성)

- <b>URI 경로에는 소문자가 적합하다.</b>
  
  - RFC 3986(URI 문법 형식)은 URI 스키마와 호스트를 제외하고는 대소문자를 구별하도록 규정하기 때문에 소문자 사용 권장

- <b>파일 확장자는 URI에 포함시키지 않는다.</b>

  - EST API에서는 메시지 바디 내용의 포맷을 나타내기 위한 파일 확장자를 URI 안에 포함시키지 않기 때문에 Accept header를 사용
```java
http://restapi.example.com/members/soccer/345/photo.jpg                              (x)

GET /members/soccer/345/photo HTTP/1.1  Host: restapi.example.com  Accept: image/jpg (o)
```
<br/>

