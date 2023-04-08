# LESSON 26 메서드란?

## 객체지향 언어

자바는 객체지향 언어이다. **\*\***\*\***\*\***\*\*\*\***\*\***\*\***\*\***객체지향 언어**\*\***\*\***\*\***\*\*\*\***\*\***\*\***\*\***란 ****\*\*\*\*****\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*****\*\*\*\*****하나의 사물을 하나의 클래스로 설명하는 언어****\*\*\*\*****\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*****\*\*\*\*****라는 뜻이다. 사물에 대한 설명은 그 물체의 **\*\***\*\*\*\***\*\***\*\***\*\***\*\*\*\***\*\***상태와 행동**\*\***\*\*\*\***\*\***\*\***\*\***\*\*\*\***\*\***으로 나눌 수 있다.

## 필드와 메서드

물건의 **상태**에 해당하는 구성 요소가 **필드**라면, 물체의 **행동**에 해당하는 구성 요소가 **메서드**이다.

자동차를 생각하면 이름과 번호라는 \***\*\*\*\*\***\*\*\***\*\*\*\*\***상태 속성\***\*\*\*\*\***\*\*\***\*\*\*\*\***도 있지만, 전진하거나 후진하는 **\*\*\*\***행동**\*\*\*\***도 있다. 이때 이름과 번호라는 \***\*\*\*\*\***\*\*\***\*\*\*\*\***\*\*\***\*\*\*\*\***\*\*\***\*\*\*\*\***상태를 필드로 정의\***\*\*\*\*\***\*\*\***\*\*\*\*\***\*\*\***\*\*\*\*\***\*\*\***\*\*\*\*\***하고, ****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****전진하거나 후진하는 행동을 메서드로 정의****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****할 수 있다.

**\*\*\*\***메서드**\*\*\*\***는 **입력값이 있고 그 입력값을 받아서 무언가를 한 다음에 결과를 도출해내는 수학의 함수와 비슷**한 개념이다.

### 입력값: 인자,매개변수 / 리턴값: 결괏값

이때 **\*\***\*\*\*\***\*\***입력값**\*\***\*\*\*\***\*\***을 \***\*인자\*\***라고 하고 \***\*\*\*\*\*\*\***\*\*\***\*\*\*\*\*\*\***결괏값\***\*\*\*\*\*\*\***\*\*\***\*\*\*\*\*\*\***을 **\*\***\*\***\*\***리턴값**\*\***\*\***\*\***이라고 한다. **\*\*\*\***\*\***\*\*\*\***입력값**\*\*\*\***\*\***\*\*\*\***은 매개변수 혹은 인자라고 이야기하기도 한다.

영어로는 **매개변수**를 **\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***파라미터(Paramente)**\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***, **\*\***인자**\*\***를 **\*\***\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***아규먼트(Argument)**\*\***\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***라고 한다. 둘 다 입력값이기는 하나 차이가 조금 있다. ****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****매개변수****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****는 ****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****전달된 인자를 받아들이는 변수****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****를 의미하며, \***\*인자\*\***는 ****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****어떤 함수를 호출할 때 전달되는 값 자체****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****\*\*\*\*****\*\*****를 이야기한다.

다음 코드를 예로 들어보겠다.

```java
public void method(int i, String str) {

}
```

여기서 `i`나 `str`은 **\*\***\*\*\*\***\*\***매개변수**\*\***\*\*\*\***\*\***라고 하고, 이 메서드를 호출해 사용할 때,

```java
method(10, "abc"); // method()라는 메서드에 인자로 10, "abc"를 전달해 호출하고 있다.
```

`10`과 `abc`는 **인자**라고 한다.

## 정리

- **필드**: 객체의 상태 속성
- **메서드**: 객체가 입력값을 받아서 결괏값을 도출해내는 일종의 행동
- **인자**(아규먼트, Argument): 어떤 함수를 호출할 때 전달되는 값 자체
- **매개변수**(파라미터, Parameter): 메서드에 전달된 인자를 받아들이는 변수.

# LESSON 27 메서드 선언

이번 장에서는 메서드를 선언하는 방법을 알아보자.

## 메서드 정의의 기본 형태

\***\*\*\*\*\***메서드\***\*\*\*\*\***란 ****\*\*****\*\*****\*\*****\*\*****\*\*****\*\*****\*\*****클래스가 가진 기능****\*\*****\*\*****\*\*****\*\*****\*\*****\*\*****\*\*****을 의미한다고 배웠다. 따라서 ********\*\*********\*\*\*\*********\*\*********\*\*********\*\*********\*\*\*\*********\*\*********메서드는 클래스 내부에 선언한다.********\*\*********\*\*\*\*********\*\*********\*\*********\*\*********\*\*\*\*********\*\*********

```java
package javaStudy;

public class MyClass {
		// public (접근제한자) 리턴형 메서드명 (매개변수들) { 실행될 코드 }
}
```

1.**리턴형**이란 **메서드를 실행한 다음 결괏값을 되돌려줄 때 사용하는 자료형**을 말한다. 다음으로 **2.메서드명**을 적고, 괄호 안에는 3.**매개변수**들을 넣어준다. 마지막으로 중괄호 안에 필요한 기능들을 구현한다.

이것이 메서드를 정의하는 기본 형태이다. 메서드는 리턴형 유무나 매개변수 유무 등에 따라 다양한 형태로 정의할 수 있다. 이번에는 여러 형태로 메서드를 선언하겠다.

## 다양한 형태의 메서드 선언

### 매개변수, 리턴값이 모두 없는 메서드

첫 번째로, 들어오는 매개변수도 없고 돌려줄 값도 없는 메서드이다. 이런 메서드를 정의하는 방법을 알아보자.

그림 속 메서드를 보니 돌려줄 값, 즉 리턴값이 없다.

```java
package javaStudy;

public class MyClass {
	// public 리턴형 메서드명 (매개변수들) { 필요한 기능 구현 }
	**public void method1() {
		System.out.println("method1 has been activated.");
	}**
}
```

1. **리턴값이 없다고 리턴형을 생략할 수는 없다. 반드시 리턴형을 써줘야 한다.**

   이 경우처럼 리턴형이 없을 때는 `void`라는 예약어를 적어준다.

   - `void` : 리턴형이 없는 예약어

2. 다음으로 메서드명을 적어준다. `method1`이라고 정했다.
3. 다음에 나온 부분은 괄호 속 매개변수인데 매개변수도 없기 때문에 비워둔 상태로 메서드를 선언한다.
4. 이후에 오는 중괄호 안에 메서드를 실행했을 때 해야 할 일들을 구현하면 된다.

### 매개변수가 있고, 리턴값이 없는 메서드

두 번째는 정수를 입력받아 뭔가를 수행하고, 리턴은 하지 않는 메서드이다.

```java
package javaStudy;

public class MyClass {
	// public 리턴형 메서드명 (매개변수들) { 필요한 기능 구현 }
	**public void method2(int x) {
		System.out.println("using " + x + "to activate method2.");
	}**
}
```

1. 이 메서드 역시 아무것도 리턴하지 않기 때문에 `void`라고 적는다.
2. 매개변수 부분에는 정수를 입력받으므로 `int`형을 적는다.
3. 그리고 매개변수가 들어왔을 때 그 값을 받아낼 그릇, 즉 변수 `x`를 하나 정의해둔다. 이 경우 입력받은 매개변수를 이용해서 메서드를 실행할 것이다. 실행하고 결괏값은 돌려주지 않을 것이다.

### 매개변수가 없고, 리턴값이 있는 메서드

세 번째는 아무것도 입력되지 않았지만, 뭔가를 수행해서 값을 돌려주는 메서드를 정의하겠다.

```java
package javaStudy;

public class MyClass {
	// public 리턴형 메서드명 (매개변수들) { 필요한 기능 구현 }
	**public int method3() {
		System.out.println("metho3 실행");
		return 10;
	}**
}
```

1. 리턴값이 있으므로 리턴형을 적어준다. 정수를 리턴한다고 하니 `int`를 넣으면 된다.
2. 메서드 이름을 넣고, 입력받을 값은 없으므로 매개변수가 없다고 작성한다.
3. 그런데 이 메서드는 반드시 값을 리턴해야 한다. 즉, 메서드 안에서 리턴할 부분을 반드시 실행해야 한다.
4. 따라서 `method3`을 실행하고, 실행한 후에는 반드시 정숫값을 돌려주도록 작성하겠다.
   값을 돌려주겠다는 예약어로 `return`을 사용하고, `10`이라는 값을 리턴한다. - `return` : 값을 돌려주겠다는 예약어

### 정숫값을 2개 입력받고, 리턴은 하지 않는 메서드

네 번째, 정숫값을 두 개 입력받아 뭔가를 수행하고 리턴은 하지 않는 메서드이다.

```java
package javaStudy;

public class MyClass {
	// public 리턴형 메서드명(매개변수들) { 필요한 기능 구현 }
	**public void method4(int x, int y) {
		System.out.println(x + y + "method4 activated");
	}**
}
```

1. 리턴하지 않으므로 `void`를 사용한다.
2. 메서드명을 넣는다.
3. 매개변수 두 개를 ‘`,`’를 사용해 나열한다.
   여기서는 `int`형만 넣었지만 \***\*\*\*\*\*\*\***\*\*\***\*\*\*\*\*\*\***기본 자료형\***\*\*\*\*\*\*\***\*\*\***\*\*\*\*\*\*\***뿐만 아니라 **\*\***\*\***\*\***참조형**\*\***\*\***\*\***까지 얼마든지 사용할 수 있다.
   이렇게 입력받은 두 값을 계산해 출력하는 식으로 실행할 수 있다.

### 매개변수가 있고, 리턴값이 있는 메서드(값을 받아서 값을 출력하는 형태)

정수 `y`를 입력받아서, 뭔가를 수행하고,정수를 출력하는 메서드를 정의하자.

```java
package javaStudy;

public class MyClass {
	// public 리턴형 메서드명(매개변수들) { 필요한 기능 구현 }
	**public int method5(int y) {
		System.out.println("using " + y + "to activate method5.");
		return y * 2;
	}**
}
```

1. 정수를 리턴하므로 리턴형은 `int`로 적는다.
2. 메서드명을 넣고, 역시 정수를 입력받으므로 매개변수 부분에도 `int`형을 적어준다.
3. 마지막에 값을 리턴해야 하므로 `return` 키워드를 사용한다. `y`에 2를 곱해서 돌려준다.

![리턴형을 int형으로 지정하기는 했지만 매개변수로 받은 값이 없기 때문에 return을 쓰지 않아도 오류가 발생하지 않는다. ](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2c18a72e-c6f5-47a0-afd8-40b46d5add03/Untitled.png)

리턴형을 int형으로 지정하기는 했지만 매개변수로 받은 값이 없기 때문에 return을 쓰지 않아도 오류가 발생하지 않는다.

![리턴형을 int형으로 지정했고, 매개변수로 받을 값이 있기 때문에 return을 쓰지 않으면 오류가 발생한다. 
→ `This method must return a result type of int`](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1f59308a-c99a-4a24-8856-811b3391835b/Untitled.png)

리턴형을 int형으로 지정했고, 매개변수로 받을 값이 있기 때문에 return을 쓰지 않으면 오류가 발생한다.
→ `This method must return a result type of int`

이렇게 다양한 형태로 메서드를 선언했다. 첫 번째부터 다섯 번째까지 작성한 모든 코드는 다음과 같다.

```java
package javaStudy;

public class MyClass {

	// public 리턴형 메서드명 (매개변수들) { 필요한 기능 구현 }

	public void method1() {
		System.out.println("method1 has been activated.");
	}

	public void method2(int x) {
		System.out.println("using " + x + " to activate method2");
	}

	public int method3() {
		System.out.println("method3 has been activated.");
		return 10;
	}

	public void method4(int x, int y) {
		System.out.println(x + y + "method4 has been activated.");
	}

	public int method5(int y) {
		System.out.println("using " + y + " to activate method5.");
		return y * 2;
	}
}
```

선언한 메서드는 호출해 사용할 수 있다. 사용하는 방법은 다음 장에 살펴보자.

## 메서드 선언 실습

### 문제

`MyClass`에 `myMethod`라는 메서드를 정의해보자. 이 메서드는 정수를 하나 입력받고, 정수를 하나 반환한다.

```java
package javaStudy;

public class MyClass {
	public int myMethod(int i) {
		return i;
	}
}
```

```java
import javaStudy.MyClass;

public class ClassExam {
	public static void main(String[] args) {
		MyClass mc = new MyClass();
		System.out.println(mc.myMethod(10));
		System.out.println(mc.myMethod(20));
	}
}

// 10
// 20
```

# LESSON 28. 메서드 사용하기

메서드를 다양하게 정의하는 방법을 배웠다. 정의하는 방법도 중요하지만, 정의한 메서드를 사용하는 방법도 중요하다. 이번 장에서는 메서드를 사용하는 방법을 살펴보자.

앞 장에서 `MyClass`라는 클래스 안에 메서드 다섯 개를 정의했다. 정의한 메서드 `method1`~`method5`를 차례대로 호출해 사용하겠다.

## method1~method5 만들기 시작

먼저 `MyClassExam`이라는 이름으로 사용할 클래스를 만든다. 여기서 `MyClass`가 가진 메서드를 사용하면 된다.

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {

	}

}
```

메서드를 사용하기 전에 한 가지 명심해야 할 사항이 있다.

```
클래스가 가진 메서드를 사용하려면 먼저 객체로 만들어야 한다.
```

즉, `MyClass`가 가진 메서드를 사용하기 위해서는 반드시 `MyClass`가 객체로 만들어져야 한다. 붕어빵 틀이 있어도 붕어빵을 만들어내지 않는다면 우리가 붕어빵을 먹을 수 없는 것과 같은 이치이다. 따라서 `MyClass`를 생성하겠다.

```java
package javaStudy;

public class MyClassExam {

	public static void main(String[] args) {
		**MyClass myclass = new MyClass();
		myclass.**
	}

}
```

클래스명 `MyClass` 뒤에 변수명은 `myclass`라고 넣었다. `new` 키워드를 사용하고, 다시 클래스명인 `MyClass`를 넣어 객체를 생성한다.

이렇게 생성한 `myclass`라는 객체 옆에 마침표를 넣어보면 앞에서 설명한 것처럼 **이 참조 변수가 가리키는 클래스의 메서**드나 **이 객체가 가진 필드**에 접근할 수 있다.

- equals(Object obj)
- getClass()
- hashCode()
- method1()
- method2(int x)
- method3()
- method4(int x, int y)
- method5(int y)
- notify()
- notifyAll()
- toString()
- wait()

## `method1` 사용하기

`MyClass`에 만들어놓은 메서드를 확인했으니, 그중 `method1`부터 사용하자.

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {
		MyClass myclass = new MyClass();
		**myclass.method1();**
	}

}
// method1 has been activated.
```

`변수명.method1`을 사용해 코드를 작성한다. 이 경우 `MyClass` 클래스가 가진 `method1`을 호출하고, 앞서 작성한 `MyClass` 클래스의 `method1` 부분을 실행한다.

## `method2` 사용하기

두 번째, `method2`도 실행하자. `method2`를 정의한 부분을 다시 한번 살펴보니…

```java
...
public void method2(int x) {
		System.out.println("using " + x + " to activate method2");
}
...
```

매개변수로 반드시 `int` 값을 받기를 원한다. 그 값을 넣어줘야 해당 메서드를 사용할 수 있다.

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {
		MyClass myclass = new MyClass();
		myclass.method1();
		**myclass.method2(10);**
	}

}
```

`int` 값이므로 10이라고 넣어줬다. 그 후 실행해보니…

```java
/*
method1 has been activated.
using 10 to activate method2
*/
```

작성한 대로 출력됐다. 출력 과정을 간단히 살펴보자면, `MyClass`가 가진 `method2`를 실행한다는 것은 중괄호 부분을 실행한다는 의미이다. 넣어준 값 `10`을 변수 `x`가 받고, 이 `x`를 출력하므로 `10`이라는 값을 출력한다.

```java
...
public void method2(int x) {
		**System.out.println("using " + x + " to activate method2");**
}
...
```

## `method3` 사용하기

세 번째, `method3`이다. 매개변수는 아무것도 받지 않으므로 다음과 같이 작성하고 실행하겠다.

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {
		MyClass myclass = new MyClass();
		myclass.method1();
		myclass.method2(10);
		**myclass.method3();**
	}

}

/*
method1 has been activated.
using 10 to activate method2
method3 has been activated.
*/
```

그런데 한 가지 주의할 사항이 있다. `method3`에서 선언한 내용을 다시 보겠다. `int` 값을 리턴한다. ‘method3 has been activated’이라는 결과만으로는 `10`이라는 값을 리턴했는지 안 했는지 알 수가 없다.

```java
...
public int method3() {
		System.out.println("method3 has been activated.");
		**return 10;
	}**
...
```

따라서 `method3`과 같이 **값을 리턴하는 메서드**를 실행할 때는 **리턴값을 받아낼 변수가 필요하다.**

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {
		MyClass myclass = new MyClass();
		myclass.method1();
		myclass.method2(10);
		**int value = myclass.method3();
		System.out.println("what method3 returned: " + value);**
	}

}
```

`int` 값을 받을 `int`형 변수 `value`를 하나 선언하겠다. 메서드를 실행한 후에 리턴해준 `int` 값을 `value`가 받아줄 것이다. 받은 값을 한번 출력해보자. ‘what method3 has returned.’ 라고 출력한다.

```
method1 has been activated.
using 10 to activate method2
method3 has been activated.
what method3 returned: 10
```

원하는 결과가 나왔다.

## `method4` 사용하기

네 번째, `method4`를 보겠다. `method4`의 선언 내용을 보면 아무것도 돌려주지 않지만, 이 메서드를 사용하기 위해서는 반드시 정수값을 두 개 넣어줘야 한다.

```java
...
public void method4(**int x, int y**) {
		System.out.println(x + y + "method4 has been activated.");
}
...
```

따라서, 5와 10, 두 값을 넣어 작성하겠다.

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {
		MyClass myclass = new MyClass();
		myclass.method1();
		myclass.method2(10);
		int value = myclass.method3();
		System.out.println("what method3 returned: " + value);
		**myclass.method4(5, 10);**
	}

}

/*
method1 has been activated.
using 10 to activate method2
method3 has been activated.
what method3 returned: 10
15method4 has been activated.
*/
```

실행결과로 ‘15method4 실행’이라고 출력됐다. 중괄호에 있던 ‘`x + y + "method4 has been activated."`’ 부분이 잘 실행됐다.

## `method5` 실행

다섯 번째, 마지막 메서드인 `method5`를 실행하자. `method5`는 정수인 `y` 값을 받아서 리턴한다.

```java
...
public int method5(**int y**) {
		System.out.println("using " + y + " to activate method5.");
		**return y * 2;**
	}
...
```

앞에서 사용한 대로 리턴한 값을 `int`형 변수에 받아서 출력해 보겠다.

`int` 값을 받을 `int`형 변수 `value2`를 선언하고, ‘what method5 returned’ 라고 출력한다.

```java
package javaStudy;

public class MyClassExam {
	public static void main(String[] args) {

		MyClass myclass = new MyClass();

		myclass.method1();

		myclass.method2(10);

		int value = myclass.method3();
		System.out.println("what method3 returned: " + value);

		myclass.method4(5, 10);

		**int value2 = myclass.method5(55);
		System.out.println("what method5 returned: " + value2);**
	}

}

/*
method1 has been activated.
using 10 to activate method2
method3 has been activated.
what method3 returned: 10
15method4 has been activated.
**using 55 to activate method5.
what method5 returned: 110**
*/
```

실행하면 `55`라는 값을 입력했기 때문에 `55`를 이용해 `m5`를 실행했고, ‘`return y*2`' 를 실행해 110이라는 값을 리턴했다.

지금까지 만든 메서드를 사용하는 방법을 알아봤다. 자바는 내가 만든 객체뿐만 아니라 이미 만들어져 있는 객체도 굉장히 많다. 따라서 각 객체가 제공하는 메서드를 사용하는 방법도 굉장히 중요하다. 메서드를 사용하는 방법을 잘 기억했다가 유용하게 사용해보자.

## 메서드 사용하기 실습

### 문제 1

참조형과 참조형이 아닌 경우의 가장 큰 차이는 ****\*\*****\*\*\*\*****\*\*****메서드 호출****\*\*****\*\*\*\*****\*\*****에서 찾아볼 수 있다. 다음 코드는 **기본형 변수 `value`**와 **참조형 변수 `ar**r`을 `**addOne`이라는 메서드에 전달**한다. **두 메서드 모두 전달받은 값에 1씩 더해주는데, 메서드를 실행한 후 전달한 값을 출력하면 서로 결과가 다르다.** 코드를 실행해 참조형과 기본형이 어떻게 다른지 확인해보자.

```java
package javaStudy;

public class ReferenceTypeExam {
	public static void main(String [] args) {
		ReferenceTypeExam exam = new ReferenceTypeExam();

		// 기본형 변수 value1을 addOne에 전달합니다.
		int value = 10;
		exam.addOne(value);
		System.out.println("value of a primitive type variable changed: " + value);

		// 참조형 변수 arr을 addOne에 전달합니다.
		int []arr = {10};
		exam.addOne(arr);
		System.out.println("value of a reference type variable changed: " + arr[0]);
	}

	public void addOne(int value) {
		value++;
	}

	public void addOne(int[] arr) {
		for(int i = 0; i<arr.length; i++) {
			arr[i]++;
		}
	}
}

/*
value of a primitive type variable changed: 10
value of a reference type variable changed: 11
*/
```

### ⭐해설⭐

**기본형 변수**가 메서드에 전달될 때는 **값의 복사본을 전달**한다. 그렇게 전달된 값은 **메서드에 선언된 매개변수에 저장**된다. **원본 변수에도 값이 들어있고, 메서드에 선언된 변수에도 값이 들어있으므로, 메서드를 실행하면서 해당 값이 바뀐다고 하더라도, 원본 변수의 값은 바뀌지 않는다.** 그러므로 해당 결과는 그대로 10을 출력한다.

**참조형 변수**(기본형을 제외한 모든 형)는 **변수에 값이 아닌 주소**가 들어있으므로 메서드에 전달될 때 **주소의 복사본을 전달**한다. 따라서 **메서드에 선언된 매개변수에도 주소값**이 들어가게 된다. **원본 변수**와 **메서드에 선언된 변수**에도 **값이 저장된 메모리의 주소**가 들어있으므로, **결국 두 변수는 같은 곳을 가리키게 된다.** 그러므로 **메서드를 실행하면서 해당 값이 바뀌면 원본 변수가 가리키는 곳의 값이 바뀌었으므로 같이 바뀌게 되는 것**이다. 그러므로 결과는 11을 출력한다.

예를 들자면…

`main` 메서드 입장에서 생각하면 `add`에 매개변수로 전달하는 숫자가 `10`이라고 했을 때

- `int value`로 전달할 때는 그냥 10이라고 새로운 종이에 적어서 전달하는 것이다. 그 종이를 돌려주지 않으면 가져간 다음에 뭘 하건 나랑은 상관이 없다.
- `int[] arr`로 전달할 때는 “저기 1958번 강의실에 있는 화이트보드에 값을 써놨어.”라고 값이 적힌 주소를 전달한다. 거기에 가보면 10이라는 값이 써 있다.

`add` 메서드는 값을 변경할 때 그 강의실에 가서 그걸 지우고 다시 `11`을 적어버린다. 나중에 `main`이 그 값을 사용할 때도 강의실에 가서 값을 보고 확인해야 사용한다. 그러면 `11`이 적혀있을 것이다.

### 문제 2

`CarExam`의 `main`에서 `Car` 클래스의 인스턴스를 만들고 `run` 메서드를 호출해보자. `Car` 클래스는 다음과 같이 정의했다.

```java
package javaStudy;

public class Car{
	public void run() {
		System.out.println("Car is running.");
	}
}
```

```java
package javaStudy;

public class CarExam{
	public static void main(String[] args) {
		**Car car = new Car();
		car.run();**
	}
}
```

### 해설

클래스는 틀이다. 실체가 아니다.

예를 들어 붕어빵을 만들기 위해서는 붕어빵 틀이 필요하다. 붕어빵 틀을 이용해서 붕어빵을 만든다. 이때 붕어빵 틀이 클래스고, 붕어빵은 인스턴스이다. 붕어빵을 먹는 것이지 붕어빵 틀을 먹는 것은 아니다. 즉, **클래스를 사용하기 위해서는 반드시 인스턴스화해야 한다**.
인스턴스를 생성하기 위해 `new` 키워드를 이용한다.
`new` 키워드를 이용하면 같은 인스턴스를 얼마든지 만들어낼 수 있다.
`Car`의 인스턴스도 얼마든지 만들어낼 수 있으므로, `Car`가 가진 필드나 메서드를 사용하기 위해서는 어떤 차를 이용할 것인지 명확하게 알려줘야 한다.
그렇기에 `run`이라는 메서드를 사용할 때는 `**인스턴스를 가리키는 변수명.메서드명()`\*\* 형태로 사용해야 한다.

# LESSON 29 String 클래스의 메서드

일상 생활에는 많은 물건이 필요하지만, 필요한 모든 물건을 본인이 직접 만들어 사용하지는 않는다. 청소기가 필요하다고 해서 청소기를 직접 만드는 사람은 없다. 가게에서 청소기를 하나 사서 사용법을 익힌 다음 사용하면 될 것이다.

자바 세상에도 이미 많은 클래스가 만들어져 있다. 대표적인 것이 문자열을 다루는 `String` 클래스이다.

```
String str = new String();
```

청소기를 사용하는 이유는 편하고 깨끗하게 집을 청소하는 데 청소기의 기능이 유용하기 때문이다. 이와 마찬가지로 자바에서 객체를 사용하는 이유 중 하나도 그 객체가 가진 기능이 유용하기 때문이다.

이번 장에서는 `String` 클래스가 제공하는 몇 가지 중요한 메서드의 사용법을 알아보겠다. `String` 클래스를 사용하려면 가정 먼저 무엇을 해야 할까? `String` 객체를 선언해야 한다.

```java
package javaStudy;

public class StringMethodExam {

	public static void main(String[] args) {
		**String str = new String("hello");**
	}
}
```

일반 객체를 생성하는 방법 그대로 `new`라는 키워드를 사용해 객체를 생성했다. 그런데 25장에서 배웠듯이 `String` 클래스는 자바에서 굉장히 자주 사용하는 유용한 클래스다 보니 약간 특별하게 생성할 수도 있다.

```java
package javaStudy;

public class StringMethodExam {

	public static void main(String[] args) {
		//String str = new String("hello");
		String str = "hello";
	}
}
```

이렇게 `new`라는 키워드 없이 `String` 타입 변수 `str`을 선언했다. `str`은 `hello`라는 문자열을 가리킨다.

우리가 청소기를 사용할 때 청소기의 모든 기능을 완벽하게 숙지해야 사용할 수 있는 것은 아니다. 많은 기능 중 한 번도 사용하지 않는 기능도 있고, 자주 사용하는 기능도 있기 마련이다. 자바 세상에 존재하는 많은 객체도 마찬가지이다. 수없이 많은 객체를 한 번에 다 알아야 할 필요도 없고, 특정 객체가 가진 모든 기능을 완벽하게 다 알아야만 객체를 사용할 수 있는 것도 아니다. 현실에서처럼 자주 사용하는 기능만 사용하는 경우가 많다.

이번 장에서는 자주 사용하는 기능 중 몇 가지만 알아보겠다.

## `length` 메서드

첫 번째, `length`라는 메서드이다. `length`는 문자열의 길이를 구해서 리턴하는 메서드이다. 그러면 `str`이 가리키는 문자열의 길이를 구해서 출력하겠다.

```java
package javaStudy;

public class StringMethodExam {
		public static void main(String[] args) {
				String str = "hello";
				System.out.println(str.length());
		}
}

// 5
```

물론, 이클립스에서 참조 변수 `str` 옆에 마침표를 넣으면 이 객체가 사용할 수 있는 필드와 메서드를 보여준다. 그중 원하는 것을 선택해서 사용하면 된다. `String`이란 클래스는 문자열을 나타내는 클래스이므로 문자열을 바꿔주거나 원하는 값을 추출하는 기능이 다양하게 있다.

실행결과 5가 출력됐다. `hello`라는 문자열을 가리키므로 문자열의 길이는 5라는 의미이다. 만약 `hello world`였다면 길이는 어떻게 나올까? 답은 11이다. **************\*\*\*\***************공백도 하나의 문자로 생각한다는 것을 잊지 말자.**************\*\*\*\***************

## `concat` 메서드

두 번째, `concat`이라는 메서드도 자주 사용한다. `concat`은 문자열과 문자열을 결합하는 메서드이다. 자, 앞에서 말한 대로 `world`를 결합해 출력해볼까?

```java
package javaStudy;

public class StringMethodExam {

	public static void main(String[] args) {
		String str = "hello";
		System.out.println(str.length());
		System.out.println(str.concat(" world"));
	}
}

// 5
// hello world
```

이렇게 `hello world`라는 문자열이 출력된다. 그런데 이때 `str`을 다시 한 번 출력하면 무엇이 출력될까? `hello`일까? `hello world`일까?

```java
package javaStudy;

public class StringMethodExam {

	public static void main(String[] args) {
		String str = "hello";
		System.out.println(str.length());
		System.out.println(str.concat(" world"));
		System.out.println(str);
	}
}

// 5
// hello world
// hello
```

문자열을 붙였다고 생각했는데 `str`을 다시 출력하니 `hello`란 문자열만 출력된다. 어떻게 된 일일까?

아래의 그림에서 보는 것처럼 `String str = "hello";` 라고 코드를 작성하면 `hello`라는 객체가 하나 만들어지고, `str`은 그 객체를 참조한다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a119c891-c123-4b09-b25a-ff7b2bbc3a1c/Untitled.png)

두 번째로 `String str2 = "hello";` 라고 코드를 작성하면 앞에서 배웠듯이 `hello`라는 새로운 `String` 객체를 만들어내지 않고, `str2`도 기존에 만들어놓은 `hello`를 가리킨다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9898e61d-e5cf-422e-9148-003b16cd3792/Untitled.png)

`str`이 `concat` 메서드를 수행했을 때 `String` 객체 자체를 바꿔버리면 참조하는 다른 변수들에 문제가 생길 수 있다. 따라서 `String` 클래스는 한 번 만들어진 객체를 바꾸지 않는다. 이를 **********\*\*\*\***********불변 클래스**********\*\*\*\***********라고 한다.

`str.concat(" world");`라는 메서드를 수행했을 때를 살펴보겠다. `concat` 메서드는 `" world"`를 받아들인 후 `str`이 참조하는 문자열 “`hello`"와 “ `world`"를 붙여서 새로운 “`hello world`” 문자열을 만들고, 새롭게 만든 문자열을 리턴한다. 이렇게 리턴한 문자열이 곧바로 `System.out.println()`으로 전달돼 출력된다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8b73beaa-4109-4f13-813d-df31aa03f04a/Untitled.png)

이때도 `str`이 참조하는 레퍼런스는 바뀌지 않는다. `str`은 그대로 “`hello`”를 가리킨다. 이 상황에서 `str`이 “`hello world`”를 참조하게 하려면 반드시 앞에 `str =`이라고 써줘야 참조하는 부분이 바뀐다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b43187ef-1a93-42b2-b286-66055618dd91/Untitled.png)

지금까지 설명한 내용을 코드에서 다시 한번 실행해보자.

```java
package javaStudy;

public class StringMethodExam {

	public static void main(String[] args) {
		String str = "hello";
		System.out.println(str.length());
		System.out.println(str.concat(" world"));
		System.out.println(str);

		**str = str.concat(" world");
		System.out.println(str);**
	}
}

// 5
// hello world
// hello
// hello world
```

`str`이 `hello world`를 가리키도록 코드를 작성했다. `concat` 메서드를 사용해 문자열을 붙여줘야 `str`이 `hello world`를 가리킨다.

## `substring` 메서드

세 번째, `substring` 메서드는 원하는 부분까지 문자열을 잘라낼 수 있는 메서드이다. `substring`은 두 가지 방법으로 사용할 수 있다.

1. `str.substring(beginIndex)`;
2. `str.substring(beginIndex, endIndex);`

1번 방법은 시작하는 인덱스만 넣는다. 시작 인덱스부터 마지막 글자까지 해당하는 문자열을 생성해서 리턴한다.

2번 방법은 시작하는 인덱스와 끝나는 인덱스 두 개를 넣는다. `(3, 6)` 이라고 넣으면 3번 인덱스부터 6번 인덱스까지 해당하는 문자열을 생성해서 리턴한다.

`String`이 가진 메서드 중 `String`을 리턴하는 메서드는 `String` 자체의 값을 변화시키지 않고, 새로운 `String`을 생성해서 리턴한다.

두 가지 방법을 코드로 작성해 출력하겠다.

```java
package javaStudy;

public class StringMethodExam {

	public static void main(String[] args) {
		String str = "hello";
		System.out.println(str.length());
		System.out.println(str.concat(" world"));
		System.out.println(str);

		str = str.concat(" world");
		System.out.println(str);
		**System.out.println(str.substring(3));
		System.out.println(str.substring(3, 6));**
	}
}

/*
5
hello world
hello
hello world
lo world
lo
*/
```

실행결과를 살펴보자. 인덱스는 0번부터 시작하기 때문에 `h`가 0번, `e`가 1번, `l`이 2,3번 인덱스이다.

1번 방법은 3번째 인덱스부터 마지막 인덱스까지 해당하는 문자열을 리턴한다. 이 리턴한 문자열을 `System.out.println()` 메서드가 출력한다.

2번 방법은 3번부터 6번 인덱스까지이다. 인덱스는 공백까지 포함한다.

문자열을 자르고 포함할 때는 규칙이 하나 있다. ****************************\*\*\*\*****************************시작하는 인덱스의 문자는 범위에 포함되지만, 끝나는 인덱스의 문자는 포함되지 않는다.****************************\*\*\*\***************************** (`begin` ≤ x ≤ `end`)

이렇게 `String`이 가진 메서드를 몇 개 살펴봤다. 어떤 물건이 가진 기능을 다른 사람보다 더 많이 안다면 그 물건을 더 잘 사용할 수 있을 것이다. 자바가 가진 객체도 그렇다. 이번 장에서 사용하지 않은 기능들도 스스로 공부하면서 사용해보자.

객체지향 프로그램은 모든 기능을 스스로 구현하기보다 ****************************************************************************************************\*\*****************************************************************************************************어떤 객체가 어떤 일을 잘하는지 파악해 해당 객체를 적절하게 사용하는 것이 핵심이다.****************************************************************************************************\*\***************************************************************************************************** 즉, 객체를 잘 사용한다는 것은 그 객체가 가진 기능을 잘 사용하는 것이므로, 메서드를 잘 사용하는 것이 객체지향 프로그래밍의 핵심이라고 봐도 좋을 것이다.

## `String` 클래스의 메서드 실습

### 문제

변수 `str1`과 변수 `str2`에 저장된 문자열을 붙여서 변수 `concatResult`에 저장하세요. 변수 `str1`이 참조하는 문자열을 2번째 인덱스부터 잘라서 `subStringResult` 변수에 저장하세요.

```java
package javaStudy;

public class StringExam{
	public static void main(String[] args) {
		String str1 = "hello. ";
		String str2 = "ab cdef ghij. klm nop!!";

		String concatResult;
		String substringResult;

		// 아래쪽에 코드를 작성하세요.
		**concatResult = str1.concat(str2);
		substringResult = str1.substring(2);**

		// 이 아래는 정답 확인을 위한 코드입니다. 수정하지 마세요.
		System.out.println(concatResult);
		System.out.println(substringResult);

		// hello. ab cdef ghij. klm nop!!
		// llo.
	}
}

/*
hello. ab cdef ghij. klm nop!!
llo.
*/
```

### 해설

`concat()` 메서드는 문자열 두 개를 붙여준다. `String` 객체가 가진 메서드이므로 `str.concat(str2)`라고 수행하면 `str`이 가리키는 문자열에 `str2`를 붙여서 리턴한다. 리턴한 값을 `concatResult` 변수에 대입해준다.

`substring()` 메서드는 문자열을 잘라준다. 메서드의 인자로 인덱스 값을 넣으면 해당 인덱스부터 마지막까지 문자열을 잘라 보여준다. 문자열의 인덱스는 0번부터 시작한다는 것을 잊지 말자.
