# StringTokenizer
`StringTokenizer` 클래스를 사용하면 문자열을 토큰으로 나눌 수 있다.

<br/>

클래스를 사용할 수 있게 import 한다.
```JAVA
import java.util.StringTokenizer;

```

<br/>

## 1. 생성

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

### 참조
[Android Developers](https://developer.android.com/reference/java/util/StringTokenizer)
