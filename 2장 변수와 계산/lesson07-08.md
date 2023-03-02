# LESSON 07 기본형

자바에서 변수를 사용하려면 반드시 자료형(data type)을 지정해줘야 한다. 이번 장에서는 `int`와 `double` 외에 **자바에서 제공하는 기본 자료형**에는 무엇이 있는지 알아보자.

| 자료형 | 키워드 | 크기 | 표현 범위 | 용례 |
| --- | --- | --- | --- | --- |
| 논리형 | boolean | 1byte | true or false(0과 1이 아니다) | boolean isFun = true; |
| 문자형 | char | 2byte | 0~65,535 | char c = ‘f’; |
|  | byte | 1byte | -128~127 | byte b = 89; |
| 정 | short | 2byte | -32,768~32,767 | short s = 32760; |
| 수 | char | 2byte | 0~65,535 | char c = 64; |
| 형 | int | 4byte | -2147483648 ~ 2147483647 | int x = 59;
int z = x; |
|  | long | 8byte | … | long big = 3456789L; |
| 실 | float | 4byte | -3.4E038~3.4E038 | float f = 32.5f; |
| 수형 | double | 8byte | -1.7E308~1.7E308 | double d = 23.34; |

리터럴이라는 용어도 사용한다.

## 리터럴

리터럴은 **일종의 값, 어떤 특정한 값 자체**라고 생각하면 된다. 

앞에서 변수에 넣어봤던 5, 10, 20 같은 숫자는 **숫자 리터럴**이다. ‘a’, ‘아’처럼 문자 하나를 넣었다면 **문자 리터럴**이다. ‘안녕하세요’, ‘이름을 입력하세요’와 같이 여러 문자를 넣었다면 **문자열 리터럴**이다. 이러한 **특정 문자나 숫자 표기**를 자바에서는 리터럴이라고 한다. 

이처럼 리터럴은 종류가 다양하다. 정수 리터럴, 실수 리터럴, 문자 리터럴, 논리 리터럴이 있으며, 리터럴을 특정 형의 변수에 대입할 수 있다. 

## 논리형

논리형 자료형을 하나 선언하자. PrimitiveDataTypeExam 클래스를 만들고, 자료형은 boolean, 이름은 isFun, 값은 true로 선언한다. 

논리형은 true 아니면 false 값만 담을 수 있다. 

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		boolean isFun = true;
		System.out.println(isFun);
	}
}

// true
```

값을 false로 바꿔 넣으면 false를 출력한다. 이런 `true`와 `false`도 리터럴이다. 논리형은 이렇게 딱 두 가지 값만 가질 수 있다. 다른 값을 넣으면 에러가 발생한다. 

## 문자형

다음은 문자형을 살펴보자. ****************************************************************************************************문자형에 값을 넣을 때는 반드시 작은따옴표를 사용해야 한다.**************************************************************************************************** 또 ********************************************************************문자 하나만 표현할 수 있다.******************************************************************** 만약 하나가 아니라 여러 개를 넣으면 에러가 발생한다. 

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		**char c = 'f';**
	}
}
```

## 정수형

이번에는 정수형 중 `int`에 변수 `x`를  선언하겠다. 변수 x에 59라는 값을 넣을 수 있다. 59라는 값 자체도 리터럴이다. 

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		int x = 59;
	}
}
```

만약 더 큰 정수를 표현하고 싶다면 `long`이라는 자료형을 사용할 수 있다. long형은 반드시 맨 뒤에 알파벳 L을 붙여야 한다. 대문자, 소문자는 상관없다. long형이라는 의미의 L을 포함해주자.

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		long bing = 34545433L;
	}
}
```

## 실수형

실수를 표현하는 `float`형에도 값을 넣어보자. float형도 마찬가지로 float형이라는 의미로 뒤에 F를 붙여야 한다. 대문자, 소문자는 상관없다.

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		**float f = 32.4F;**
	}
}
```

실수를 표현하는 자료형 중 `double`을 사용하면 더 큰 실수를 표현할 수 있다. 

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		float f = 32.4F;
		double d = 3434343.5;
	}
}
```

## 기본형 사용 방법 정리

```java
boolean isFun = true; 
char c = 'f';           // 작은따옴표를 사용해야 한다.
int x = 59;
long big = 3456789**L**;    // 뒤에 **소문자 l이나 대문자 L**을 붙여야 한다. 
float f = 32.5**f**;        // 뒤에 **소문자 f나 대문자 F**를 붙여야 한다.
double d = 23.34;       
```

## 기본형 실습

```java
public class PrimitiveDataTypeExam {
	
	public static void main(String[] args) {
		boolean isFun = false;
		char charValue = 'a';
		int intValue = 20;
		long longValue = 2147483648L;
		System.out.println(isFun);
		System.out.println(charValue);
		System.out.println(intValue);
		System.out.println(longValue);
	}
	
	// false
	// a
	// 20
	// 2147483648
}
```

# LESSON 08 기본형 형변환

## 기본형 포함관계

자바는 정수형, 실수형을 기본형으로 제공하고 형마다 크기가 다르다.

`short - 2byte`

`character - 2byte`

`int - 4byte`

`float - 4byte`

`long - 8byte`

그런데 정수형 `long`과 실수형 `float` 중에서는 `float`형이 더 크다.

데이터를 담을 수 있는 크기는 `long`이 큰 것 같지만, 실수는 소수점 뒤까지 자릿수가 필요하기 때문에 실수를 더 큰 형으로 인식한다. 

자연수 < 정수 

정수 + 분수 < 유리수

유리수 + 무리수 < 실수 < 허수

이 관계처럼 **정수는 실수에 포함**된다.

→ `byte < short`, `char < int < long < **float < double**`


## 형변환의 필요성

가령 크기가 다른 컵 두 개가 있다고 해보자. 큰 컵에는 `long` , 작은 컵에는 `int`라고 적혀있다. 친구가 `long` 컵에 있는 물을 `int` 컵에 담아 달라고 한다면 어떻게 해야 할까?


우리는 `long` 컵에 물이 얼마나 들어있는지 모른다. 모르는 상태에서 그냥 옮겨 담았다가는 물이 넘칠 수도 있다. 이럴 때는 옮겨 담아도 좋을지 판단할 수 없을 것이다. 컴파일러도 마찬가지다. ****************************************큰 자료형에 들어있는 것을 작은 자료형에 넣으려고 하면 컴파일러는 일단 에러를 발생시킨다.**************************************** 

반대 상황도 생각해보자. 친구가 `int` 컵 안에 들어있는 물을 `long` 컵에 담아 달라고 한다. 이번에는 컵에 물이 얼마나 있는지 생각하지 않고 그냥 담아도 될 것이다. **컴파일러도 마찬가지로 작은 자료형에 들어있는 값을 큰 자료형에 담을 때는 자연스럽게 담을 수 있다.** 지금까지 설명한 것이 **자료형의 형변환(casting)**이다. 

## 묵시적 형변환

한 가지 상황을 더 생각해보자. 사실 `long` 컵 안에는 물이 가득 차 있지 않았다. 굉장히 조금 들어있었다. `int` 컵 안에 옮겨 담아도 문제가 없을 정도로 적은 양이었다. 그렇다면 큰 컵보다 작은 컵에 담는 것이 효율적일 것이다. 이럴 경우에는 어떻게 담아야 하는지 자바 코드로 확인해보자.

`TypeCastingExam` 클래스를 만들어 `int`형 변수 `x`를 선언하고, `x`에 50000이라는 값을 넣는다. 다음으로 `int`보다 더 큰 자료형인 `long`형 변수 `y`를 선언하고, `y`에 `x`의 값, 즉 작은 컵에 들어있는 물을 담아보자.

```java
public class TypeCastingExam {
	
	public static void main(String[] args) {
		int x = 50000;
		long y = x;
		System.out.println(y);
	}
}

// 50000
```

`x`에 들어있는 물을 `y`에 담으라는 코드를 작성했지만, 컴파일러는 오류를 보여주지 않는다. 작은 컵에서 큰 컵으로 물을 담을 때, 즉 작은 자료형의 값을 큰 자료형에 넣을 때는 자연스럽게 형변환이 **일어난다.** 

이런 경우를 ************************************************묵시적(암묵적) 형변환************************************************이라고 한다. 

## 명시적(강제) 형변환

이번에는 반대 경우를 한번 살펴보자. `long`형에 `x2`라는 변수를 선언하고, `5`라는 값을 넣는다. 다음으로 `int`형 변수 `y2`를 선언하고, `y2`에 `x2`의 값을 넣어보자. 

```java
public class TypeCastingExam {
	
	public static void main(String[] args) {
		int x = 50000;
		long y = x;
		
		**long x2 = 5;
		int y2 = x2;
		System.out.println(y2);**
	}
}

/*
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
	Type mismatch: cannot convert from long to int

	at TypeCastingExam.main(TypeCastingExam.java:9)
*/
```

이번에는 컴파일러가 ******************************형변환 에러******************************를 발생시킨다. `long`형의 값을 `int`형에 담을 때는 문제가 발생할 수도 있기 때문이다. 실제로 변수 `x2`에는 `5`라는 작은 값이 들어있고 `int`형 변수 `y2`는 `5`라는 작은 값이 들어있고 `int`형 변수 `y2`는 `5`라는 값을 충분히 담을 수 있지만, ********************************************************************************************컴파일러는 이러한 내용을 모르기 때문에 결정을 내릴 수 없다.******************************************************************************************** 따라서 프로그래머가 형변환해줘야 한다. 프로그래머가 “이 값을 `int`형에 담아도 좋다,” 라고 알려주면 문제없이 형변환할 수 있다. 

형변환하려면 값을 넣기 전에 해당 형을 괄호 안에 넣어준다. 

```java
public class TypeCastingExam {
	
	public static void main(String[] args) {
		int x = 50000;
		long y = x;
		
		long x2 = 5;
		int y2 = **(int)** x2;
		System.out.println(y2);
	}
}

// 5
```

이렇게 하는 것을 ********************************************************명시적(강제) 형변환********************************************************이라고 한다. 

## 정리

### 형변환이란?

변수 또는 리터럴의 형을 다른 형으로 변환하는 것.

묵시적 형변환과 명시적 형변환이 있다.

### 묵시적(암묵적) 형변환

작은 자료형을 더 큰 자료형으로 바꿀 떄는 묵시적으로 형이 바뀐다.

```java
int x = 50000;
long y = x;
```

### 명시적(강제) 형변환

큰 자료형을 더 작은 자료형으로 바꿀 때는 명시적으로 형을 바꿔준다.

```java
long x = 50000;
// int y = x; --이렇게 묵시적으로 수행하면 컴파일러는 에러를 발생시킨다.
int y = (int) x; // 반드시 명시적으로 형을 바꿔줘야 한다. 
```

## 기본형 변환 실습

### 문제 1

```java
public class TypeCastingExam {
	public static void main(String[] args) {
		int intValue = 200;
		**long longValue = intValue;**
		System.out.println(longValue);
	}
}
// 200
```

### 문제 2

```java
public class TypeCastingExam {
	public static void main(String[] args) {
		long longValue = 20;
		**int intValue = (int) longValue;**
		System.out.println(intValue);
	}
}

// 20
```

이번에는 크기가 큰 형의 변숫값을 더 작은 형으로 옮겨 담으니 컴파일러에 형변환을 명시적으로 알려줘야 한다. 변수 앞에 (형)을 적어 알려준다.