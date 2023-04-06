# LESSON 24 참조형

이번에 배울 내용은 참조형이다. **자바는 변수를 선언하려면 반드시 변수의 자료형을 정해줘야 한다.** 변수의 자료형에는 **기본형**과 **참조형**이 있다. **기본형**은 앞서 배운 **논리형, 문자형, 정수형, 실수형**, 총 여덟 개이다. 이 기본형들은 **클래스가 아니다.**

********************\*\*\*\*********************자바 변수의 자료형********************\*\*\*\*********************

- 기본형
- 참조형

**************************\*\*\*\***************************자바 변수 중 기본형 (!== 클래스)**************************\*\*\*\***************************

- 논리형: `boolean`
- 문자형: `char`
- 정수형: `byte`, `short`, `int`, `long`
- 실수형: `float`, `double`

## 참조형이란?

그렇다면 자바에서 참조형이란 무엇일까? ****************************************************************************************************************\*\*****************************************************************************************************************기본형을 제외한 모든 형을 말한다. 앞서 배운 배열도 참조형이고, 클래스도 참조형이다.\*\*

참조형 변수를 선언하면서 더 자세히 알아보자. 우선 기본형 변수를 하나, ‘`int i = 4`’라고 선언한다. 이 코드는 `i`라는 4바이트 크기의 정수형 변수에 숫자 4를 저장한다는 의미이다.

---

```java
package javaStudy;

public class RefereceDataType {

	public static void main(String[] args) {
		**int i = 4;**
	}

}
```

이번에는 참조형 변수를 하나 선언하겠다. `String`이라는 클래스를 이용해 참조형 변수 `str`을 선언했다.

```java
package javaStudy;

public class RefereceDataType {

	public static void main(String[] args) {
		int i = 4;

		**String str = new String("hello");**
	}

}
```

코드를 보면 변수 앞에 기본형이 아닌 `String`이라는 클래스가 적혀있다. 대입 연산자(=) 뒤에는 `new` 다음에 생성자가 있다. 생성자에 대해서는 다음 장에서 자세히 살펴볼 테니 여기서는 ‘생성자가 있구나.’라고만 생각하자.

`new`라는 키워드는 클래스를 메모리에 올리라는 뜻이다. 이렇게 메모리에 올라간 클래스를 ********\*\*********인스턴스********\*\*********라고 한다. 메모리에 올라간 인스턴스를 가리키는 변수, 참조하는 변수, 레퍼런스 하는 변수가 `str`이라는 변수이다. ****************************************************************************************************************************\*\*****************************************************************************************************************************참조한다, 레퍼런스한다는 것은 변수가 인스턴스를 가지는 것이 아니라 말 그대로 가리킨다는 의미이다.****************************************************************************************************************************\*\*****************************************************************************************************************************

그림으로 보면 다음과 같다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c940abf4-4b09-4ec0-bd82-8b6d28182497/Untitled.png)

즉, `str`이라는 변수에는 **메모리의 위치(주소) 값**이 저장된다. 메모리에 위치 값을 저장한다 하더라도 어떤 메모리에 저장하는지 그 정보를 아는 방법은 없다. 그러므로 `str` 변수는 `String` 인스턴스를 참조한다고만 알아두면 된다. 앞으로 배울 **********\*\*\*\***********클래스는 모두 이와 같은 참조형임을 기억하자.**********\*\*\*\***********

## 참조형 정리

참조형 변수에 대해 짧게 정리하겠다.

```java
String str = new String("hello");
```

- `str` 변수 앞에 기본 자료형이 아닌 `String` 클래스가 적혀있다.
- `(=)` 뒤에는 `new` 다음에 생성자라는 것이 있다.
- `new`라는 키워드는 클래스를 메모리에 올려준다.이렇게 메모리에 올라간 클래스를 ********\*\*********인스턴스********\*\*********라고 한다.
- 메모리에 올라간 인스턴스를 가리키는 변수, 참조하는 변수, 레퍼런스하는 변수가 `str`이다. 변수가 인스턴스를 가지는 것이 아니라 말 그대로 가리킨다는 의미다.
- `str`이라는 변수에는 메모리의 위치 값을 저장한다. 어떤 메모리에 저장하는지 알 수 있는 방법은 없기 때문에 `str` 변수는 `String` 인스턴스를 참조한다고만 기억한다.
- 앞으로 배울 클래스들은 모두 참조형이다.

- 이쯤에서 **************************\*\***************************객체, 클래스, 인스턴스**************************\*\*************************** 등 용어 정리~!
  **\*\***객체**\*\***는 우리가 소프트웨어 세계에 구현해야 할 대상이다. 객체를 구현하기 위한 설계도가 ****\*\*\*\*****클래스****\*\*\*\*****이다. 클래스라는 설계도에 따라 소프트웨어 세상에 구현된 실체가 ********\*\*********인스턴스********\*\*********이다.
  클래스를 메모리에 올려 인스턴스를 만드는 과정을 ************\*\*************인스턴스화************\*\*************라고 한다. 실체화된 인스턴스는 메모리에 할당된다. **********************************************************************************\*\***********************************************************************************인스턴스를 객체라고 불러도 무방하다. 개념적으로 인스턴스는 객체에 포함된다고 볼 수 있기 때문이다.**********************************************************************************\*\***********************************************************************************

## String 클래스

이번에는 자바 언어에서 가장 많이 사용하는 클래스인 ****************\*\*\*\*****************String 클래스****************\*\*\*\*****************를 알아보자. 이 책에서도 처음부터 알게 모르게 String 클래스를 사용했다. 예를 들어 `main` 메소드에서도 `String` 클래스를 볼 수 있다.

```java
package javaStudy;

public class StringExam {

		public static void main(**String**[] args) {

		}

}
```

String 클래스는 가장 많이 사용하는 클래스인 만큼 자바에서도 특별하게 취급한다.

먼저, `**String` 클래스는 `new`라는 연산자를 이용하지 않고도 인스턴스를 만들어낼 수 있다.\*\* 모든 클래스는 `new` 연산자를 이용해야 하는데 말이다… 한번 인스턴스를 만들어보자.

```java
package javaStudy;

public class StringExam {

	public static void main(String[] args) {
		**String str1 = "hello";
		String str2 = "hello";

		String str3 = new String("hello");
		String str4 = new String("hello");**

	}

}
```

이처럼 `str1`과 `str2`라는 변수 옆에 기본 자료형에서 했던 것처럼 바로 값을 넣어도 인스턴스가 생성된다. 물론 `str3`와 `str4`처럼 일반 클래스와 똑같이 `new`를 이용해도 된다. `new`를 사용하지 않으면 똑같은 문자열일 겨웅 같은 메모리 공간을 사용한다. `str1`과 `str2`는 같은 문자열을 참조하게 된다. `new`를 사용하면 같은 문자열이어도 매번 메모리에 새롭게 할당된다. `String` 클래스는 다른 클래스와 다르게 `new`를 사용하지 않고 사용할 수 있으므로 메모리를 아끼려면 `new`를 사용하지 않고 사용하는 것이 좋다.

두 가지 방법을 이용해 `String` 문자열 객체를 생성했다. 그런데 사용하는 방법에 따라 메모리에 올라가는 방법이 달라진다. 어떻게 다른지 더 자세히 알아보자.

방금 작성한 코드는 모두 `'hello'`라는 문자열을 생성한다.

```java
String str1 = "hello";
String str2 = "hello";
```

첫번째 ‘`hello`'를 생성하면 이 ‘`hello`’라는 문자열은 **메모리 중에 상수들을 저장하는 영역**에 저장된다. 상수는 앞서 배웠듯이 **변하지 않는 값**을 말한다. 변하지 않는다는 것을 잘 생각하면 **같은 상수가 두 개 생성될 필요가 없다는 의미**이다. 그런데 첫 번째와 두 번째, 모두 ‘`hello`'를 생성한다.

자, 흐름을 따라가 보자. 첫 번째 ‘`hello`’라는 인스턴스가 상수 영역에 하나 만들어졌고, 그 ‘`hello`’를 `str1`이 가리킨다. 그런데 다음 줄에서 `str2`도 `hello`를 가리키라고 한다. 그럼 일단 `str2`는 상수 영역에 똑같은 `hello`가 있는지 살펴본다. 있으면 새로 만들지 않고, 기존에 있는 ‘`hello`’를 가리킨다. 따라서,

```java
str1와 str2는 같은 인스턴스를 가리킨다. 같은 인스턴스를 참조한다.
```

이렇게 이해하고 기억하면 된다.

다음으로 str3와 str4는 `new` 키워드를 이용해 만들었다.

```java
String str3 = new String("hello");
String str4 = new String("hello");
```

`new` 키워드로 인스턴스를 만들면 상수 영역을 참조하지 않는다. `new`라고 나오는 순간 인스턴스를 무조건 힙(heap) 메모리 영역에 새로 만든다.그래서 `str3`와 `str4`는 각각 인스턴스를 하나씩 생성한다. 그리고 각각 만든 `hello`라는 문자열을 가리킨다.

- NOTE
  힙(heap) 메모리 영역이란 할당해야 할 메모리의 크기를 프로그램을 실행하는 동안 결정해야 하는 경우(런타임 때) 유용하게 사용되는 공간이다. 기본 데이터 타입은 항상 크기가 동일하지만, 객체들은 생성 시에 크기가 다를 수 있으므로 힙에 생성한다.

정말인지 확인해보자. 각 변수가 가리키는 주소가 같은지, 다른지를 비교하겠다.

```java
package javaStudy;

public class StringExam {

	public static void main(String[] args) {
		String str1 = "hello";
		String str2 = "hello";

		String str3 = new String("hello");
		String str4 = new String("hello");

		**if(str1 == str2)
			System.out.println("str1 and str2 are the same reference");**

	}

}

// str1 and str2 are the same reference
```

기본형인 경우 비교 연산자 ‘`==`'은 두 값이 같은지를 비교했다. 그런데 참조형인 경우에는 값을 비교하지 않는다. 그 대신 가리키는 주소가 같은지, 즉 가리키는 메모리 영역의 주소가 같은지를 비교한다.

`str1`과 `str2`가 같은 영역을 가리키는지 확인하기 위해 두 변수를 비교하는 코드를 `if`문으로 작성했다. `if`문을 블록으로 감싸지 않으면 한 문장만 실행된다. 따라서 `if`문 괄호 속 조건이 맞으면 우리가 원하는 문장이 출력될 것이다.

출력이 잘 됐다. 즉, `str1`과 `str2`는 같은 레퍼런스이다.

다른 부분도 비교하자. `str1`과 `str3`은 같은 레퍼런스일까? `str3`과 `str4`는 같은 레퍼런스일까?

```java
package javaStudy;

public class StringExam {

	public static void main(String[] args) {
		String str1 = "hello";
		String str2 = "hello";

		String str3 = new String("hello");
		String str4 = new String("hello");

		**if(str1 == str3)
			System.out.println("str1 and str3 are the same reference");

		if(str3 == str4)
			System.out.println("str3 and str4 are the same reference");**

	}

}

//
```

실행결과 아무것도 출력되지 않는다. `str1`과 `str3`, 그리고 `str3`과 `str4`는 서로 다른 인스턴스를 가리킨다는 의미이다.

String 클래스의 또다른 특징 중 하나가 **\*\*\*\***한 번 실행한 클래스는 변하지 않는다는 것이다.**\*\*\*\*** 다른 클래스는 그렇지 않는다. String 클래스만 독특한 것이라고 생각하면 된다.

이것이 어떤 의미인지 살펴보자. 먼저, 앞에서 작성한 코드에서 `str1`을 출력하자.

```java
package javaStudy;

public class StringExam {

	public static void main(String[] args) {
		String str1 = "hello";
		String str2 = "hello";

		String str3 = new String("hello");
		String str4 = new String("hello");

		System.out.println(str1);

	}

}
// hello
```

이클립스에서 `str1` 옆에 `.(마침표)`를 넣으면 `String` 클래스가 가진 메서드들을 볼 수 있다.

`String` 클래스는 자주 사용하는 클래스인 만큼 메서드도 굉장히 많다. 그중에서 `substring`이라는 메서드를 수행하겠다. 이 메서드는 “잘라주세요.”라는 뜻이다. 옆의 괄호에 `'3'`이라고 넣어준다. 즉, 이 코드의 의미는 **“인덱스가 3번인 것부터 잘라서 보여주세요.”**라는 뜻이다. 실행해보자.

```java
package javaStudy;

public class StringExam {

	public static void main(String[] args) {
		String str1 = "hello";
		String str2 = "hello";

		String str3 = new String("hello");
		String str4 = new String("hello");

		System.out.println(str1);
		**System.out.println(str1.substring(3));**

	}

}

// hello
// lo
```

실행하면 `hello`의 3번 인덱스부터 나머지 부분만 출력된다. 인덱스는 0번부터 시작한다. 자, 이 때 `str1`을 다시 출력하겠다.

```java
package javaStudy;

public class StringExam {

	public static void main(String[] args) {
		String str1 = "hello";
		String str2 = "hello";

		String str3 = new String("hello");
		String str4 = new String("hello");

		System.out.println(str1);
		System.out.println(str1.substring(3));
		System.out.println(str1);
	}

}

// hello
// lo
// hello
```

그러면 `str1` 자체는 전혀 바뀌지 않고 그대로 출력된다. 이렇게 한번 만들어진 `String` 클래스의 값은 변하지 않는다. `String` 클래스가 가진 메서드들은 모두 `String` 값을 반환한다.

## String 클래스 정리

이번 장에서 배운 String 클래스를 정리하자.

### 자바 인스턴스 생성 방법

1. `new` 키워드 없이 인스턴스를 만드는 경우

   ```java
   String str1 = "hello";
   String str2 = "hello";
   ```

   - `"hello"` 라는 문자열이 메모리 중 상수를 저장하는 영역에 저장된다.
   - 두 번째 문장이 실행될 때 `hello`라는 문자열 상수가 이미 만들어졌으므로 `str1`이 참조하는 인스턴스를 `str2`도 참조한다.

2. `new` 키워드로 인스턴스를 만드는 경우

   ```java
   String str3 = new String("hello");
   String str4 = new String("hello");
   ```

   - 인스턴스는 무조건 새로 만들어진다.
   - 두 번째 문장이 실행될 때도 새로 만들고, `str3`와 `str4`는 서로 다른 인스턴스를 참조한다.

   ```java
   String str5 = "hello world";
   String str6 = str5.substring(3);
   ```

   - String은 불변 클래스다. 인스턴스가 될 때 가진 값을 나중에 수정할 수 없다.
   - 문자열과 관련한 다양한 메서드가 있다. 메서드를 호출해도 내부의 값이 변하지 않는다.
   - String을 반환하는 메서드는 모두 새로운 `String`을 생성해 반환한다.

## String 클래스 실습

### 문제 1

다음 코드를 실행해 `str1`과 `str2`가 들어있는 값은 같지만 서로 다른 인스턴스임을 확인해보세요.

```java
package javaStudy;
public class StringExam {
	public static void main(String[] args) {
		String str1 = new String("Hello world");
		String str2 = new String("Hello world");

		if(str1 == str2) {
			System.out.println("str1 and str2 have the same reference.");
		} else {
			System.out.println("str1 and str2 have the different reference.");
		}
	}
}

// str1 and str2 have the different reference.
```

### 해설

`String` 변수 `str1`은 참조형 변수이다. **참조형 변수는 변수를 저장하는 공간에 객체를 저장할 수 없기 때문에 다른 영역에 저장**하고, **그 위치의 주소 값을 변수에 담는다. `==` 연산자는 변수를 저장하는 공간의 값만 비교**하므로 **두 `String` 객체는 똑같이 생겼지만, 다른 영역에 객체가 저장됐고, 그 객체의 저장 위치는 다르**므로 `==` 연산자로 비교했을 때 다르다고 결과가 나오는 것이다.

### 문제

`==` 연산자를 이용해 `String`을 비교하면 레퍼런스를 비교하기 때문에 같은 값인지 확인할 수 없다. 같은 값인지 확인하고 싶을 때는 `equals` 메서드를 사용하면 된다. 다음 코드를 실행해 `equals` 메서드의 동작을 확인해보자.

```java
package javaStudy;

public class StringExam{
	public static void main(String[] args) {
		String str1 = new String("Hello world");
		String str2 = new String("Hello world");
		if(str1.equals(str2)) {
			System.out.println("str1 and str2 have the same value.");
		} else {
			System.out.println("str1 and str2 have different values.");
		}
	}
}

// str1 and str2 have the same value.
```

### 해설

`equals` 메서드는 `==` 연산자와는 다르게 메서드에서 **구현한 내용을 판단**한다. **객체의 주소를 비교하지 않고, 객체의 내용을 비교한다.** 그래서 예제를 실행했을 때 두 객체가 같다는 결과를 얻는다.
