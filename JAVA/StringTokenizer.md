# StringTokenizer
`StringTokenizer` 클래스를 사용하면 문자열을 토큰으로 나눌 수 있다.

<br/>

클래스를 사용할 수 있게 import 한다.
```JAVA
import java.util.StringTokenizer;

```

<br/>

## 1. 생성
- 기본
```JAVA
StringTokenizer(String str, String delim, boolean returnDelims) /* str(문자열), delim(구분문자), returnDelims(구분문자포함) */
```

<br/>

- 객체 생성 시에 문자열만 입력했을 경우, 공백을 구분문자로 사용한다.
```JAVA
StringTokenizer st = new StringTokenizer("java util StringTokenizer");

while (st.hasMoreTokens()) {
    System.out.println(st.nextToken());
}
```
```JAVA
java
util
StringTokenizer
```

<br/>

- 구분문자를 직접 지정할 수 있다.
```JAVA
StringTokenizer st = new StringTokenizer("java.util.StringTokenizer stringTokenizer", ".");

while (st.hasMoreTokens()) {
    System.out.println(st.nextToken());
}
```
```JAVA
java
util
StringTokenizer stringTokenizer
```

<br/>

- 구분문자를 토큰에 포함시킬 수 있다. <b>(값이 없을 때 기본값: false)</b>
```JAVA
StringTokenizer st = new StringTokenizer("java.util.StringTokenizer stringTokenizer", ".", true);

while (st.hasMoreTokens()) {
    System.out.println(st.nextToken());
}
```
```JAVA
java
.
util
.
StringTokenizer stringTokenizer
```

<br/>

## 2. 메소드
- 기본

|메소드명|반환타입|설명|
|-------|-------|----|
|countTokens()|int|nextToken() 메소드 **호출 가능 횟수**를 반환|
|hasMoreTokens()|boolean|사용 가능한 토큰이 남아있는지 확인|
|hasMoreElements()|boolean|hasMoreTokens()와 동일|
|nextToken()|String|다음 토큰을 반환|
|nextToken(String delim)|String|구분문자를 포함하여 문자열을 재조합한 후, 입력한 구분문자로 다시 나눔|
|nextElement()|Object|nextToken()과 동일|

<br/>

### 참조
[Android Developers](https://developer.android.com/reference/java/util/StringTokenizer)
