# REST API
<b>REST(REpresentational State Transfer) API</b>는 두 컴퓨터 시스템이 인터넷을 통해 <b>정보를 안전하게 교환</b>하기 위해 사용하는 인터페이스다.

<br/>

>### REST 구성
- 자원(Resource) : URI

- 행위(Verb) : HTTP Method

- 표현(Representations)

<br/>

>### REST 특징
- <b>Uniform(유니폼 인터페이스)</b>

  - 유니폼 인터페이스는 URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일을 말한다.

- <b>Stateless(무상태성)</b>

  - REST는 무상태성 성격을 가진다. 다시 말해, 작업을 위한 상태 정보를 따로 저장하고 관리하지 않는다.

  - 세션이나 쿠키를 별도로 저장, 관리하지 않아 API 서버는 단순히 들어오는 요청만을 처리하면 되기 때문에 자유도가 높아지고 구현이 단순해진다.

- <b>Cacheable(캐시 가능)</b>
  - HTTP 기존 웹표준을 그대로 사용하기 때문에 웹에서 사용하는 기존 인프라를 그대로 활용 가능하다.

  - 따라서 HTTP가 가진 캐싱 기능을 적용할 수 있다.
