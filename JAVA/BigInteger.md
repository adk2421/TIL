# BigInteger

`int`나 `long` 타입의 표현 범위를 넘어서는 정수가 있을 때 사용

**BigInteger**는 다른 정수 자료형과 달리 문자열 형태로 숫자를 처리하므로 무한한 범위를 갖는다.

<br/>

| 타입 | 범위 | 메모리 크기 | 기본/참조형 | 저장된 위치 |
| --- | --- | --- | --- | --- |
| int | -2,147,483,648 ~ 2,147,483,647 | 4 Byte | 기본형 | Stack |
| long | 9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 | 8 Byte | 기본형 | Stack |
| BigInteger | 무한 | 70 Byte (최소) | 참조형 | Heap |

> **BigInteger**는 “5”와 같이 한 자리 수를 사용할 때, 최소 메모리 크기인 **70Byte**를 사용한다.
다른 정수 타입과 비교하면 많은 메모리 공간을 차지하며, **표현하고자 하는 자릿수에 비례**하여 사용하는 메모리 크기가 늘어나기에 사용할 때 주의가 필요하다.

<br/>

## 선언 및 생성

```java
import java.math.BigInteger;

BigInteger bigNum1 = new BigInteger("1234567890");

BigInteger bigNum2 = new BigInteger("FFFF", 16); // n진수 형태로 생성하여도 10진수로 자동변환되어 표현

BigInteger bigNum3 = BigInteger.valueOf(1234567890); // int -> BigInteger
```

<br/>

## 메소드

- **변수**

BigInteger는 기본 변수 3개가 있다.

```java
BigInteger bigNum1 = BigInteger.ZERO;    // 0
BigInteger bigNum2 = BigInteger.ONE;     // 1
BigInteger bigNum3 = BigInteger.TEN;     // 10
```

<br/>

- **연산**

BigInteger는 문자열이기에 연산이 안되므로, 연산을 하기 위해서는 클래스 내부에 있는 메소드를 사용해야 한다.

```java
BigInteger bigNum1 = new BigInteger("100");
BigInteger bigNum2 = new BigInteger("30");

System.out.println(" + : " + bigNum1.add(bigNum2));
System.out.println(" - : " + bigNum1.subtract(bigNum2));
System.out.println(" * : " + bigNum1.multiply(bigNum2));
System.out.println(" / : " + bigNum1.divide(bigNum2));
System.out.println(" % : " + bigNum1.remainder(bigNum2));

/*
    + : 130
    - : 70
    * : 3000
    / : 3
    % : 10
*/
```

<br/>

- **형 변환**

```java
BigInteger bigNum = BigInteger.valueOf(300);  // int -> BigInteger

int intNum = bigNum.intValue();               // BigInteger -> int
long longNum = bigNum.longValue();            // BigInteger -> long
float floatNum = bigNum.floatValue();         // BigInteger -> float
double doubleNum = bigNum.doubleValue();      // BigInteger -> double
String strNum = bigNum.toString();            // BigInteger -> String
```

<br/>

- **비교**

두 수를 비교했을 때, 기준 변수가 더 크면 1, 같으면 0, 작으면 -1을 리턴한다.

```java
BigInteger bigNum1 = new BigInteger("300");
BigInteger bigNum2 = new BigInteger("200");
BigInteger bigNum3 = new BigInteger("300");

int compare1 = bigNum1.compareTo(bigNum2);     // 1
int compare2 = bigNum1.compareTo(bigNum3);     // 0
int compare3 = bigNum2.compareTo(bigNum3);     // -1
```

<br/>

---

**참조**

[learn more - Java에서 큰 수 다루기 (BigInteger)](https://lsmman.tistory.com/47)

[Tecoble - BigInteger_BigDecimal](https://tecoble.techcourse.co.kr/post/2021-04-26-BigInteger_BigDecimal/)
