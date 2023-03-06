# LESSON 15 switch 문

switch 문도 if 문처럼 조건에 따라서 처리를 제어할 수 있는 문법이다.

switch 문에서는 `switch`, `case`, `default`, `break`라는 키워드를 사용한다. 

`SwitchExam` 클래스를 만들어 `int`형 변수 `value`를 하나 선언하고, 일단 1로 초기화한다. 이어서 `switch`를 입력하고 뒤의 괄호에 식을 넣어주면 `switch`가 이 식을 판단한다. 이번 실습에서는 변수 `value`를 넣겠다. `switch` 역시 `{}`로 블록을 만든다. 

```java
public class SwitchExam {
	public static void main(String[] args) {
		int value = 1;
		
		switch(value) {
		
		}
	}
}
```

`if` 문은 괄호에 조건문을 주고 그 조건을 만족시켰을 때 `if` 블록 안에 들어있는 문장을 수행했다. 

`switch` 문은 블록 안에 `case` 구문을 넣는다. 그리고 `value` 변수에 값이 들어왔을 때 `value` 변수의 값과 `case` 뒤의 값이 일치하는 `case` 구문부터 수행한다.

## case 구문

그럼 블록 안에 `case` 구문을 작성해보자. `if` 문에서 `else if`를 여러 개 사용했듯이 `case` 구문도 여러 개 사용할 수 있다.

```java
public class SwitchExam {
	public static void main(String[] args) {
		int value = 1;
		
		switch(value) {
			case 1:
				System.out.println("1");
			case 2:
				System.out.println("2");
			case 3:
				System.out.println("3");
			default: // value 값이 1, 2, 3 중 아무것도 아니라면 (default는 생략 가능)
				System.out.println("other number");
		}
	}
}
// 1
// 2
// 3
// other number
```

value 값이 1이니까 “1”만 출력할 줄 알았는데 1을 출력하고 2, 3, other number까지 모두 출력했다.

이번에는 `value` 값만 2로 바꾼 뒤 실행하자.

```java
public class SwitchExam {
	public static void main(String[] args) {
		**int value = 2;**
		
		switch(value) {
			case 1:
				System.out.println("1");
			case 2:
				System.out.println("2");
			case 3:
				System.out.println("3");
			default:
				System.out.println("other number");
		}
	}
}

// 2
// 3
// other number
```

1은 출력되지 않았다. `value` 값이 2이므로 값이 같은 `case 2`부터 `default`까지 출력했다. 

**********이처럼 `case`문은 값이 같은 case부터 나머지를 모두 출력하는 것이 특징이다.** 만약 `if else`처럼 그 값 하나만 출력하고 싶다면 어떻게 해야 할까? 

## break

이때 사용하는 키워드가 `break`이다. 각 case마다 `break`를 넣어보겠다. 그런 다음 `value` 값에 1을 넣고 실행해보겠다.

```java
public class SwitchExam {
	public static void main(String[] args) {
		int value = 1;
		
		switch(value) {
			case 1:
				System.out.println("1");
			**break;**
			case 2:
				System.out.println("2");
			**break;**
			case 3:
				System.out.println("3");
			**break;**
			default:
				System.out.println("other number");
		}
	}
}

// 1
```

`value` 값이 1일 때 실행하니 값이 1인 `case 1`에서 “1”을 출력하고, `break`를 만나 `switch` 문 밖으로 빠져나왔다. `case 2, 3, default`까지 계속 수행하지 않는다. 

`value` 값을 2로 바꿔 실행해보자.

```java
public class SwitchExam {
	public static void main(String[] args) {
		**int value = 2;**
		
		switch(value) {
			case 1:
				System.out.println("1");
			break;	
			case 2:
				System.out.println("2");
			break;
			case 3:
				System.out.println("3");
			break;
			default:
				System.out.println("other number");
		}
	}
}

// 2
```

이번에는 `value` 값이 2이기 때문에 값이 같은 `case 2` 구문을 실행한 다음, `break`를 만나 `switch` 문을 바로 빠져나온다. 이처럼 해당하는 `case`만 실행하고 싶을 때는 `break`문을 반드시 사용해야 한다. 만약 어떤 `case`부터 시작해 순차적으로 모두 실행하고 싶을 때는 `break` 구문을 빼면 된다. 

`switch` 문에는 정수 말고 ********문자열********도 넣을 수 있다. (JDK 7부터)

문자열은 `String`형을 이용한다. 

`String`형 변수 `str`에 A를 선언하고, switch 괄호 안에는 변수 `str`을 넣어준다. 그리고 `case` 값이 A일 때, `case` 값이 C일 때를 작성하고 실행하면 결과로 “A”를 출력한다. 

```java
public class SwitchExam {
	public static void main(String[] args) {
		**String str = "A";**
		
		switch(**str**) {
			**case "A":
				System.out.println("A");**
			break;	
			**case "B":
				System.out.println("B");**
			break;
			**case "C":
				System.out.println("C");**
			break;
			default:
				System.out.println("other string");
		}
	}
}

// A
```

## 정리

switch 문에서 사용하는 키워드는 `switch`, `case`, `default`, `break`이다. 

키워드를 사용해 switch 문을 작성하면 다음과 같다.

```java
switch(변수) {
	case 값:
		실행문;
		break;
	case 값:
		실행문;
		break;
	default:
		실행문;	
}
```

## switch 문 실습

`month`에는 지금이 몇 월인지 나타내는 숫자가 들어있다. `switch` 문을 이용해 `season`이 12~2월이면 “겨울”, 3~5월이면 “봄”, 6~8월이면 “여름”, 9~11월이면 “가을”을 값으로 가지도록 만듶ㄹ자. 

```java
import java.util.Calendar;
public class SwitchExam{
	public static void main(String[] args) {
		// month에는 현재 월이 들어있음
		int month = Calendar.getInstance().get(Calendar.MONTH) + 1;
		String season = "";
		// switch 문을 이용해 season이 봄/여름/가을/겨울 중 
		// 하나의 값을 가지도록 만들자. 
		switch(month) {
		case 3 : case 4 : case 5 :
			season = "spring";
			break;
		case 6 : case 7 : case 8 :
			season = "summer";
			break;
		case 9 : case 10 : case 11 :
			season = "autumn";
			break;
		case 12 : case 1 : case 2 :
			season = "winter";
			break;
		}
		
		
		// 이 위에서 switch 문을 완료해야 한다.
		System.out.println("It is "+month+", and the season is "+season+".");
	}
}

// it is 3, and the season is spring.
```

### 해설

이 예제에서 판단해야 할 변수는 `month`이다. 따라서 `switch`문 괄호에는 `month`를 넣어준다.

12~2월까지는 `season = "겨울"` 문장을 실행하면 된다. 구현할 때,

```java
case 12 : season = "겨울" break;
case 1 : season = "겨울" break;
case 2 : season = "겨울" break;
```

이렇게 구현할 수도 있지만 이렇게 구현하면 `season = "겨울" break;` 이라는 문장을 똑같이 세 번 넣어야 한다. 같은 코드가 중복되면 해당 코드를 수정할 때 중복 코드를 모두 수정해야 하므로 바람직하지 않다. 

### switch문 요약

switch 문을 요약하면, 입력된 값이 어떤 `case`에 해당하는지 찾고 그 `case`부터 `switch` 문이 끝날 때까지 실행한다. 단, `break`를 만나면 `switch` 문을 빠져나온다. 

즉, `case` 문 다음에 `break`가 없다면 문제의 코드를 계속 수행할 것이므로 다음과 같이 써도 똑같이 수행한다.

```java
**case 12 : case 1 : case 2 :
	season = "겨울";
	break;**
```

이처럼 같은 동작을 하는 여러 `case`를 묶어서 한 번에 처리하고, 그 뒤에 `break`를 한 번만 적어주면 더 편리하게 `switch`문을 이용할 수 있다. 

`season`에 값을 넣어줄 때는 대입 연산자 ‘`=`’을 사용하고 문자열의 경우 `""`(쌍따옴표)를 필수로 사용해야 함을 잊지 말자.


# LESSON 17 do while문

앞에서 배운 `while`문은 조건이 참일 경우에만 블록 안 문장을 실행했다. 만약 조건을 만족하지 않는다면 반복문 안 문장을 한 번도 실행하지 않을 수도 있다. `do while`문은 이와 다르게 무조건 한 번은 실행하게 하는 구문이다. 

## do while문 기본 구조

```java
do {
	반복할 문장들 
} while()
```

`do` 키워드를 먼저 써주고 블록을 만들어준다. 이 블록 안에 반복할 문장들을 넣어준다. **무조건 `do`부터 시작하기 때문에 `do` 블록 안에 있는 ‘반복할 문장들’을 한 번은 수행한다**. 이후에는 `while`문처럼 `while` 조건을 넣어준다. 

`while` 키워드 뒤에는 `i가 10보다 작을 때까지` 등 여러 조건을 넣을 수 있다. `do ~ while` 부분을 한 번 수행하고, 이후에는 `while` 문의 조건을 만족할 때만 다시 `do`까지 올라가서 문장을 수행한다. 이를 반복하는 것이다. 

## 객체지향이란?

`do while` 문 코드를 설명하기 전에 잠깐 자바 세상을 둘러보자. 객체지향 프로그램은 현실 세계를 프로그램으로 옮겨 둔 것이다.

일상생활을 예로 들어보자. 집에서 밥을 지어보자. 밥을 지으려면 쌀을 씻어서 물과 함께 밥솥에 넣고, 밥솥 버튼을 누르면 된다. 밥을 먹으려고 밥솥부터 만들지는 않는다. 밥솥은 이미 만들어져 있는 객체이기 때문이다.