# LESSON 30 변수의 스코프와 static

프로그램에 사용하는 변수들은 사용 가능한 범위가 있다. 기본적으로는 변수가 선언된 블록이 그 변수의 사용 범위이다. 이번 장에서는 변수의 사용 범위를 더 자세히 살펴보겠다.

먼저 `VariableScopeExam` 클래스에 변수를 하나 선언하겠다.

```java
package javaStudy;

public class VariableScopeExam {
	**int globalScope = 10;**

	public static void main(String[] args) {

	}
}
```

`int`형으로 `globalScope`라는 변수를 하나 선언했다. `globalScope`라는 변수의 사용 범위는 `VariableScopeExam` 클래스 전체라고 할 수 있다.

여기서 메서드를 하나 만들어 선언한 변수를 사용하겠다.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;

	**public void scopeTest(int value) {
		int localScope = 20;
	}**

	public static void main(String[] args) {

	}
}
```

`scopeTest`라는 메서드를 하나 만들고, 이 메서드의 매개변수로 `int`형 `value`를 하나 선언했다. 그리고 이 메서드에도 변수를 하나 선언했다. 이렇게 선언했을 때 `scopeTest` 메서드에서 어떤 변수까지 사용할 수 있는지 테스트하겠다.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;

	public void scopeTest(int value) {
		int localScope = 20;

		**System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);**
	}

	public static void main(String[] args) {

	}
}

```

처음 선언한 `globalScope` 변수를 사용하겠다고 코드를 작성했는데 이클립스가 어떤 오류도 발생시키지 않았다. 즉, `globalScope`라는 변수를 `scopeTest`라는 메서드 내에서 사용할 수 있다는 의미이다.

`localScope` 변수는 `ScopeTest`라는 메소드 내에서 선언했으니 당연히 사용할 수 있다.

그뿐만 아니라 매개변수로 선언된 `value`라는 값도 사용하는 데 문제가 없다. 매개변수로 사용된 `value`는 블록 바깥쪽에 있지만, 메서드 선언부에 위치하므로 사용 범위는 해당 메서드 블록 내라고 보면 된다.

그러면 이 변수들이 **다른 메서드 내에서도 사용할 수 있는지** 메서드를 하나 더 정의해 테스트하겠다.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	**public void scopeTest2(int value2) {
		System.out.println(globalScope);
		System.out.println(localScope); // 컴파일 오류가 발생한다.
		System.out.println(value); // 컴파일 오류가 발생한다.
	}**
	public static void main(String[] args) {

	}
}
```

→ localScope cannot be resolved to a variable

→ value cannot be resolved to a variable

`scopeTest` 블록 밖에 `scopetTest2`라는 메서드를 하나 더 선언했다. 이 메서드의 매개변수로는 `int`형 `value2`를 사용했다. `ScopeTest` 메서드에서 사용한 변수들을 `scopteTest2` 메서드에서도 사용할 수 있는지 테스트하니, `globalScope`는 에러가 발생하지 않는다. 그런데 `localScope`나 `value` 변수는 사용할 수 없다고 컴파일 에러가 발생한다.

이것이 변수의 사용 범위(`scope`)이다. **변수를 선언한 블록에 포함되지 않았기 때문에 `scopeTest2`에서는 이 변수들을 사용할 수 없는 것이다.**

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		**//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);**
	}
	public static void main(String[] args) {

	}
}
```

물론 `**scopeTest2` 메서드에서 매개변수로 선언한 `value2`는 문제없이 사용\*\*할 수 있다.

그렇다면 이 변수들을 `main` 메서드에서 한번 사용해보자.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);
	}
	public **static** void main(String[] args) {
		**System.out.println(globalScope); // 컴파일 오류가 발생한다.
		System.out.println(localScope);  // 컴파일 오류가 발생한다.
		System.out.println(value);       // 컴파일 오류가 발생한다.**
	}
}
```

분명히 클래스 내에 있는데도 `globalScope`부터 모두 컴파일 에러가 발생한다. 이 변수들은 왜 `main` 메서드에서 사용할 수 없을까? 답은 `**static**`이라는 키워드에 있다.

클래스는 붕어빵 틀이다. 모든 클래스는 인스턴스화하지 않은 채로 사용할 수 없다. 붕어빵 틀이 붕어빵은 아닌 것과 같은 이치이다.

`main` 메서드에는 `static`이라는 키워드가 붙어있다. 이 키워드가 지금까지 `main` 메서드를 정의할 때 `new`를 사용하지 않았는데도 실행된 비밀이다. `static`이라는 키워드를 붙여주면 클래스를 인스턴스화하지 않아도 `static`한 메서드나 `static`한 변수를 사용할 수 있다.

- NOTE: 클래스를 인스턴스화하지 않았다.
  클래스를 인스턴스화하지 않는다는 의미를 보충 설명하겠다. 다음은 `main` 메서드의 기본 형식이다.
  ```java
  public static void main(String[] args) {
  }
  ```
  **지금까지 정의한 모든 메서드는 메서드를 실행하기 위해**,
  1. **클래스의 인스턴스를 생성하고**
  2. **인스턴스를 통해 클래스를 호출했다.**
  `main`도 메서드인데, `main` 메서드는 이런 과정을 거치지 않았다.
  ```java
  class CodeRunner {
  		// 직접 정의한 메서드 myPrint
  		public void myPrint() {
  				System.out.println("안녕!");
  		}

  		public static void main(String[] args) {
  				/*myPrint 메서드를 호출하기 위해서는
  				CodeRunner 클래스에 인스턴스를 생성하고,
  				인스턴스에 점을 찍어 myPrint에 접근한다. */
  				CodeRunner codeRunner = new CodeRunner(); // 인스턴스 생성
  				codeRunner.myPrint(); // 메서드 호출

  				**/* 그런데 메인 메서드는 메인 메서드를 위해 따로 인스턴스를 생성한 적이 없고,
  				또 codeRunner.main()과 같이 메서드를 호출한 적도 없다. */**
  		}
  }
  ```
  즉, 클래스를 인스턴스화하지 않고 사용해왔다.

`**static`한 메서드는 객체를 생성하지 않아도 `static`한 메서드나 `static`한 변수(클래스 변수)를 사용할 수 있지만, `static`하지 않은 변수(인스턴스 변수)는 사용할 수 없다. `static`한 메서드가 사용하는 시점에 해당 클래스가 인스턴스화되지 않았을 수도 있기 때문이다.\*\*

`**static`하지 않은 변수를 사용하겠다는 것은 객체를 생성하지도 않았는데 객체의 속성을 사용하겠다고 하는 것이므로 당연히 안된다.\*\* 이후 예제들을 수행하면서 조금씩 이해해보자.

그럼 `static`한 변수를 하나 선언하겠다. `**static`한 변수**란 `**static` 키워드를 이용해 선언한 변수\*\*를 말한다. 물론 변수를 선언하는 방법은 다 똑같다.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;
	**static int staticVal = 7;**

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);
	}
	public static void main(String[] args) {
		**System.out.println(staticVal);**
	}
}

// 7
```

`static` 키워드를 사용하고 `int`형 변수 `staticVal`을 하나 선언했다. 그리고 `static`한 메서드인 `main` 메서드에서 이 변수를 사용해보자.

이번에는 컴파일 에러가 발생하지 않는다. `**static`한 변수는 `static`하지 않은 메서드 내에서 사용해도 문제가 되지 않는다.\*\* 그렇다면 `main` 메서드, 즉 `static`한 메서드에서 `static`하지 않은 변수를 사용하려면 어떻게 해야 할까?

지금까지 작성한 대로 객체를 생성하고 사용하면 된다. 객체를 생성하는 방법은 이미 알고 있으니, 생성해보자.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;
	static int staticVal = 7;

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);
	}
	public static void main(String[] args) {
		System.out.println(staticVal);

		**VariableScopeExam v1 = new VariableScopeExam();
		System.out.println(v1.globalScope);**
	}
}

// 7
// 10
```

`VariableScopeExam` 클래스와 참조 변수 `v1`, 그리고 `new` 키워드와 클래스명을 넣어 객체를 생성했다. 사용할 때는 반드시 참조 변수와 필드명을 사용해야만 접근할 수 있다.

이때 반드시 기억해야 할 부분이 있다. 참조변수 `v1`은 `VariableScopeExam`이라는 인스턴스가 생성될 때 `globalScope` 값을 저장하는 공간을 별개로 하나 가진다.

만약 `VariableScopeExam`을 가리키는 참조 변수 `v2`를 하나 더 생성한다면 어떻게 될까? `v2` 객체 안에 `globalScope` 값을 저장할 수 있는 공간이 별도로 생길 것이다.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;
	static int staticVal = 7;

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);
	}
	public static void main(String[] args) {
		System.out.println(staticVal);

		VariableScopeExam v1 = new VariableScopeExam();
		System.out.println(v1.globalScope);
		**VariableScopeExam v2 = new VariableScopeExam();**
	}
}

// 7
// 10
```

정말 각 변수마다 별도로 값을 저장할 수 있는지 테스트하자.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10; // 1번
	static int staticVal = 7; // 2번

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);
	}
	public static void main(String[] args) {
		System.out.println(staticVal); // 3번

		VariableScopeExam v1 = new VariableScopeExam();
		System.out.println(v1.globalScope); // 4번
		VariableScopeExam v2 = new VariableScopeExam();
		**v1.globalScope = 10;
		v2.globalScope = 20;
		System.out.println(v1.globalScope); // 5번
		System.out.println(v2.globalScope); // 6번**
	}
}

// 7
// 10
// 10
// 20
```

3번~6번까지 출력됐다.

3번. 2번에서 선언한 `static`한 `int`형 변수 `staticVal`을 실행했다.

4번. 1번을 보면 `globalScope`에 원래 10이 들어있었기 때문에 10을 출력했다.

5번. `v1`의 `globalScope`에 10이란 값을 넣었기 때문에 10을 출력했다.

6번. `v2`의 `globalScope`에 20이란 값을 넣었기 때문에 20을 출력했다.

그럼 `static`한 변수에도 값을 부여해보자.

```java
package javaStudy;

public class VariableScopeExam {
	int globalScope = 10;
	static int staticVal = 7;

	public void scopeTest(int value) {
		int localScope = 20;

		System.out.println(globalScope);
		System.out.println(localScope);
		System.out.println(value);
	}

	public void scopeTest2(int value2) {
		System.out.println(globalScope);
		//System.out.println(localScope);
		//System.out.println(value);
		System.out.println(value2);
	}
	public static void main(String[] args) {
		System.out.println(staticVal);

		VariableScopeExam v1 = new VariableScopeExam();
		System.out.println(v1.globalScope);
		VariableScopeExam v2 = new VariableScopeExam();
		v1.globalScope = 10;
		v2.globalScope = 20;
		System.out.println(v1.globalScope);
		System.out.println(v2.globalScope);
		**v1.staticVal = 50;
		v2.staticVal = 100;
		System.out.println(v1.staticVal);
		System.out.println(v2.staticVal);**
	}
}

// 7
// 10
// 10
// 20
// 100
// 100
```

`v1.staticVal`에는 50을 넣고, `v2.staticVal`에는 100을 넣었다. 그리고 각각을 출력한다. 50과 100이 나오리라 기대가 되지만, 100과 100이 출력된다.

`**static`한 필드는 인스턴스를 생성할 때 만들어지는 것이 아니다. 값을 저장할 수 있는 공간도 하나밖에 없다. 즉, 값을 공유한다.** 그래서 이런 변수를 **********\*\*************클래스 변수**********\*\*\*\***********라고 한다. `globalScope` 같은 변수는 인스턴스를 생성할 때 생성되기 때문에 **********\*\*\*\***********인스턴스 변수**********\*\*\*\***********라고 한다.

**클래스 변수**는 인스턴스를 선언하지 않아도 사용할 수 있으므로 지금 사용한 것처럼 ‘`참조변수.변수명`’이라고 사용하기보다는 **클래스명을 직접 사용**한다. 그러므로 ‘`클래스명.클래스 변수명`’이렇게 사용하는 것이 바람직하다.

- NOTE
  변수의 생성 및 소멸 시점은 언제일까? 클래스에서 사용하는 변수의 종류는 클래스 변수, 인스턴스 변수, 지역 변수로 구분할 수 있다.
  **********\*\*\*\***********클래스 변수**********\*\*\*\***********는 `static` 키워드가 붙은 변수를 의미한다. 클래스를 생성하지 않아도 실행파일이 메모리에 로드될 때 생성한다. 즉, 프로그램을 시작할 때 생성했다가 프로그램을 종료할 때 소멸한다.
  **************\*\***************인스턴스 변수**************\*\***************는 클래스의 멤버로 설정하는 변수를 의미한다. 클래스를 이용해 인스턴스화할 때 메모리에 할당된다. 즉, `new` 연산자를 이용해 객체를 생성할 때 생성했다가 객체가 소멸할 때 소멸한다.
  ********\*\*********지역 변수********\*\*********는 클래스에 포함된 메서드에서 사용하는 변수이다. 메서드를 사용할 때 메모리에 생성했다가 메서드를 종료하는 시점에 소멸한다. .

## 변수의 스코프와 `static` 실습

### 문제 1

`main`메서드는 `static`한 메서드이다. 코드가 정상적으로 동작하도록 `value`가 선언되는 줄을 수정하라.

```java
package javaStudy;

public class VariableScopeExam{
	**static int value = 10;**
	public static void main(String []args) {
		System.out.println(value);
	}
}

// 10
```

### 해설

`static` 메서드에서는 `static`한 필드만 사용할 수 있다. 즉, `value` 변수를 선언할 때 `static` 키워드를 붙여줘야 한다. 모든 클래스는 틀이고, 클래스를 사용하기 위해서는 객체를 생성해야 한다고 했다. 객체를 생성하는 과정을 인스턴스화라고 한다. 인스턴스화 하지 않으면 실체는 생기지 않는다. 다시 말해 인스턴스화한다는 말은 하드디스크에 저장된 클래스를 사용할 수 있도록 메모리에 올려주는 것을 의미한다. 이렇게 메모리에 올라와 있는 자원만 사용이 가능하다.

`static`이라는 키워드는 해당 요소를 인스턴스화하지 않고, 메모리에 올려주는 역할을 한다. 이때 객체의 모든 요소를 메모리에 올리는 것은 아니고, `static`으로 선언한 요소만 메모리에 따로 올려준다. 그래서 `main` 메서드는 그 메서드를 감싸는 객체를 인스턴스화하지 않았는데도 사용할 수 있었다. 다시 생각하면 `static`한 요소만 메모리에 올라와 있고, 나머지는 메모리가 없기 때문에 `static`한 메서드에서는 `static`한 필드만 사용할 수 있는 것이다.

`main` 메서드는 `static`하고, `value`는 `static`하지 않기 때문에 `value`라는 변수를 그냥 사용하려고 하면 에러가 발생한다. 따라서 `main`에서 `value` 변수를 사용하기 위해 변수 선언 앞에 `static` 키워드를 붙여준다.

### 문제 2

`static`한 변수는 여러 인스턴스에서 숫자를 변경해도 값이 모두 공유된다. 다음 코드에서 `taxi`의 `wheelCount`와 `suv`의 `wheelCount`를 서로 다르게 지정한 것처럼 보이지만, `taxi`와 `suv`의 `wheelCount`는 둘 다 마지막에 지정한 4라는 값을 가진다. `Car` 클래스의 `wheelCount`는 `static`하기 때문이다. 코드를 작성한 뒤 결과를 확인해보자.

```java
package javaStudy;
public class Car{
	static int wheelCount;
	int speed;
}
```

```java
package javaStudy;

public class StaticExam{
	public static void main(String[] args) {
		Car taxi = new Car();
		Car suv = new Car();

		taxi.wheelCount = 10;
		suv.wheelCount = 4;

		System.out.println("taxi의 바퀴 수:" + taxi.wheelCount);
		System.out.println("suv의 바퀴 수:" + suv.wheelCount);
	}
}

/*
taxi�� ���� ��:4
suv�� ���� ��:4
*/
```

### 해설

`static` 키워드가 붙은 요소들은 메모리에 미리 올라와 있다고 설명했다.

`**static` 키워드가 붙은 필드**는 **객체를 생성하기 전에 메모리 공간을 확보**하므로, 객체를 생성할 때마다 각각 메모리 공간을 확보하는 다른 필드와 다르게 **값을 저장하는 메모리 공간을 하나만 가지므로 모두 공유\*\*한다.

# LESSON 31 열거형

이번 장에서는 열거형(`enum`)을 알아보자. 

열거형은 서로 관련 있는 상수들을 모아서 집합으로 정의한 것이다. 자바는 열거형을 이용해 변수를 선언할 수 있다. 그리고 열거형을 변수형으로 사용한다. 열거형은 JDK 5에서 추가된 문법이다.

열거형이 등장하기 전에는 `public`과 `static final`을 이용해 상수를 열거형 대신 사용했다. 그렇게 사용하면서 생길 수 있는 오류나 불편함을 해결하기 위해 추가된 것으로 생각하면 조금 쉬울 것 같다. 어떻게 사용했는지 한번 살펴보자. 먼저 `javaStudy` 패키지에 `EnumExam`이란 이름으로 클래스를 생성한다. 이 클래스에 상수를 이용해 코드를 작성하겠다.

```java
package javaStudy;

public class EnumExam {
	**public static final String MALE="MALE";
	public static final String FEMALE="FEMALE";**
	public static void main(String[] args) {
		
	}
}
```

`static`이란 키워드를 배운 것 기억하나요? `static`하게 선언하면 객체 생성 없이 사용이 가능할 것이다. `final`은 상수를 선언할 때 사용하는 키워드이다. 문자열을 넣을 수 있도록 자료형은 `String`형을 넣어준다. 변수명은 상수를 선언할 경우 이름 전체를 대문자로 쓰는 것이 관례였으므로 모두 대문자로 써준다. 이렇게 `'MALE'`과 `'FEMALE'`이라는 상수 두 개를 선언했다.

이제 `main` 메서드에서 실제로 사용해보자.

```java
package javaStudy;

public class EnumExam {
	public static final String MALE="MALE";
	public static final String FEMALE="FEMALE";
	public static void main(String[] args) {
		**String gender1;**
	}
}
```

우선 `String`형의 `gender1`이라는 변수를 하나 선언했다. 이 `gender1`이라는 변수가 `MALE` 혹은 `FEMALE`이라는 값 중 하나만 가지게 하고 싶다. 이 경우 어떻게 해야 할까?

아까 상수로 선언한 값을 이용하면 된다. `gender1`에 값을 넣어보겠다.

```java
package javaStudy;

public class EnumExam {
	public static final String MALE="MALE";
	public static final String FEMALE="FEMALE";
	public static void main(String[] args) {
		String gender1;
		**gender1 = EnumExam.MALE;
		gender1 = EnumExam.FEMALE;**
	}
}
```

선언한 `static`한 필드의 값을 가져다 사용한다. `static`한 필드는 객체를 생성하지 않고도 사용할 수 있었다. 그래서 클래스명 다음에 바로 접근할 수 있었다. 

```java
'gender1 = 클래스명 + 마침표 + 상수로 선언해놓은 MALE 혹은 FEMALE'.
```

`gender`가 두 가지 값만 대응하도록 이렇게 두 가지 값을 부여한다. 

그런데 이때 한 가지 문제가 발생할 수 있다. `gender1`이라는 변수에 아무 문자열이나 넣어보자.

```java
package javaStudy;

public class EnumExam {
	public static final String MALE="MALE";
	public static final String FEMALE="FEMALE";
	public static void main(String[] args) {
		String gender1;
		gender1 = EnumExam.MALE;
		gender1 = EnumExam.FEMALE;
		
		**gender1 = "boy";**
	}
}
```

처음 의도한 것은 `gender1`에 `MALE` 혹은 `FEMALE` 두 값 중 하나만 넣는 것이었다. 그런데 `body`라는 값을 넣어도 이클립스느 에러를 발생시키지 않는다. `gender1`이라는 변수가 `string` 형이고, `MALE`, `FEMALE` 외 `boy` 같은 다른 값도 `string` 값이기 때문에 컴파일상에서 문제를 일으키지 않는 것이다. 즉, 이렇게 코드를 작성하고 실행해도 컴파일할 때 아무런 문제가 발생하지 않는다. 하지만 정작 코드를 실행시켰을 때는 원했던 값이 아니라 다른 값이 나오므로 문제가 된다. 

이런 문제가 발생하지 않도록 열거형을 사용한다. 열거형을 사용하는 방법은 다음과 같다.

```java
enum 열거형 이름 { 값1, 값2 }
```

이 형식으로 클래스 아래에 열거형을 하나 선언하겠다.

```java
package javaStudy;

public class EnumExam {
	public static final String MALE="MALE";
	public static final String FEMALE="FEMALE";
	public static void main(String[] args) {
		String gender1;
		gender1 = EnumExam.MALE;
		gender1 = EnumExam.FEMALE;
	}
}

**enum Gender{
	MALE, FEMALE;
}**
```

`enum`이라고 선언하고, 열거형 이름을 `Gender`라고 붙였다. 이렇게 선언하고 중괄호 안에 넣고 싶은 값을 나열한다. `Gender`라는 열거형에는 `MALE, FEMALE` 값만 넣고 싶으므로 두 값을 넣었다. 

- NOTE
    
    `Enum` 이름은 클래스 명명 규칙을 따르며, 세부 항목의 이름은 모두 대문자를 사용한다. 
    

선언을 마치고, 이제 코드에서 사용하자.

```java
package javaStudy;

public class EnumExam {
	public static final String MALE="MALE";
	public static final String FEMALE="FEMALE";
	public static void main(String[] args) {
		String gender1;
		gender1 = EnumExam.MALE;
		gender1 = EnumExam.FEMALE;
		
		**Gender gender2;
		gender2 = Gender.MALE;
		gender2 = Gender.FEMALE;**
	}
}

enum Gender{
	MALE, FEMALE;
}
```

상수로 정의할 때는 `string`형의 `gender1`이라고 선언했는데, 열거형으로 정의할 때는 `enum`인 `Gender` 자체가 자료형이 되기 때문에 `Gender`형으로 선언할 수 있다. `Gender`형의 변수를 `gender2`라는 이름으로 선언했다. 선언한 후 값을 부여할 때는 `gender2`에 `gender.MALE`, `gender.FEMALE` 값만 들어갈 수 있다. 앞에서처럼 전혀 다른 값인 `boy`를 넣으려고 한다면, 컴파일할 때부터 에러가 난다. 직접 입력하면 이클립스도 에러를 표시한다.

`Gender`형의 변수에 `MALE`과 `FEMALE`만 대입할 수 있고 다른 값은 저장할 수 없듯이 이처럼 특정 값만 사용해야 한다면 열거형을 사용하는 것이 좋다. 

- NOTE
    
    Q. 열거형은 `String`이라고 선언하지 않아도 되나요?
    
    A. 자바의 자료형은 크게 기본 자료형(`int`, `float`, `char`, …)과 참조 자료형(`class`, …)으로 나뉜다. `enum`은 참조 자료형에 속하며 `enum`형을 가진 형태의 클래스이다.
    
    ```java
    enum Gender {
    	MALE, FEMALE;
    }
    public class EnumExam {
    	public static void main(String[] args) {
    			Gender gender;
    
    			gender = Gender.MALE;
    			gender = 1; // 오류 발생
    			gender = "MALE"; // 오류 발생
    	}
    }
    ```
    
    이 코드에서 `enum`형인 `Gender` 클래스로 선언된 `gender`에 기본 자료형인 `int`형은 당연히 들어가지 못하고, 문자열도 들어가지 못한다.
    
    `enum`형으로 선언된 값만 가질 수 있기 때문에 `enum`형인 `Gender.MALE`, `Gender.FEMALE`만 들어갈 수 있다.
    
    ```java
    String gender1
    Gender gender2
    ```
    
    `gender1`은 `String`으로 선언했고, `gender2`는 `Gender` 클래스로 선언된 것으로 자료형이 다르다. 즉, `Gender` 내부에 선언된 `MALE`, `FEMALE`은 문자열이 아니라 `enum`형으로 인식해야 한다. 
    
- NOTE
    
    Q: `enum Gender` 내부에 `MALE`, `FEMALE` 값을 나열했는데 `MALE`과 `FEMALE`은 `EnumExam class` 내부에 선언한 `static` 상수이지 않나요? `enum`을 `EnumExam class` 밖에 선언했는데도 내부의 `static` 상수는 가져다 쓸 수 있는 건가요?
    
    A: `enum`으로 선언한 내용과 `EnumExam class`에 선언한 상수는 다른 것이다. `enum`은 열거형이라는 아예 다른 데이터 타입이다. 예제를 잘 보면 두 차이를 보여주기 위해 상수로 사용했을 때와 `enum`으로 사용했을 때를 설명했다. 상수로 쓰던 것의 부족한 점을 해결하기 위해서 만들어진 것이 `enum`이라고 이해하면 좋다. 
    
    두 번째 질문도 처음 내용이 헷갈려서 나온 질문인듯 하다. `enum`은 `EnumExam class`에 종속적인 타입이 아니므로 얼마든지 다른 클래스에서 사용할 수 있다.