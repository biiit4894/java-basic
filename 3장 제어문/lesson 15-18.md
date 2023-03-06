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

- 예시
    
    ![while 조건문에 `value != 1`이라고 되어 있지만 1을 입력해도 여전히 `input value: 1`은 출력된다.](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/767e26ba-bc34-436f-9287-d359bd1cf1fa/Untitled.png)
    
    while 조건문에 `value != 1`이라고 되어 있지만 1을 입력해도 여전히 `input value: 1`은 출력된다.
    

## 객체지향이란?

`do while` 문 코드를 설명하기 전에 잠깐 자바 세상을 둘러보자. 객체지향 프로그램은 현실 세계를 프로그램으로 옮겨 둔 것이다.

일상생활을 예로 들어보자. 집에서 밥을 지어보자. 밥을 지으려면 쌀을 씻어서 물과 함께 밥솥에 넣고, 밥솥 버튼을 누르면 된다. 밥을 먹으려고 밥솥부터 만들지는 않는다. 밥솥은 이미 만들어져 있는 객체이기 때문이다. 하지만 밥솥을 사용하기 위해 그 밥솥을 어디선가 사왔을 것이다.

프로그래밍 안에서 밥을 짓기 위해서는 일단 밥솥을 먼저 사와야 하는데, 이때 사용하는 연산자가 `new`이다. 

```java
밥솥 b = new 밥솥();
```

이런 코드를 이용하면 된다. 자바 세상에 이미 만들어져 있는 모든 객체는 `new` 연산자를 이용하면 다 사용할 수 있다. 

자바에서는 모든 값을 변수에 담아놓고 사용해야 한다. 밥솥 `b`는 밥솥 타입의 변수 `b`를 선언한 코드이다. `int i`와 같다고 생각하면 된다. `i`는 정수를 담을 수 있는 변수이고, `**b`는 밥솥을 담을 수 있는 변수**라고 생각하자. 자바는 **********************강형 언어**********************이므로 모든 변수의 타입을 분명히 선언해야 한다. **이때 `b`는 밥솥을 담는 변수일 뿐 밥솥은 아니다. 진짜 밥솥을 만들기 위해서는 반드시 `new 밥솥();`이라는 코드를 실행해야 한다.** 

이 파트는 Part 5에서 클래스와 객체를 배울 때 더 자세히 알아보고, `new` 연산자를 이용하면 진짜로 밥솥이 만들어진다는 것만 기억하자. 그렇게 만들어진 밥솥을 `=`을 이용해 `b` 변수에 대입하는 코드이다. 

세상에는 똑같은 밥솥이 너무나 많다. 그중 내 밥솥은 `b`가 담고 있는 밥솥이므로 앞으로 내 밥솥을 사용할 때는 `b`라는 변수를 이용해 사용하면 된다. 

하나만 더 설명하겠다. `new 밥솥();` 하면 실제 밥솥을 만들어내야 하는데, 밥솥 회사가 너무 여러 곳이다 보니 들어낼 때 어떤 밥솥을 만들지 헷갈릴 수 있다. 그래서 코드 맨 첫 줄에 `import` 예약어를 이용해 어떤 밥솥인지를 명시해야 한다. 

이제 본격적으로 코드를 보면서 이해해보자. 본문 코드에서는 밥솥 대신 `Scanner`라는 객체를 만들어 사용하자.

## do while문을 사용하는 경우(실습 1)

`DoWhileExam` 클래스를 만들고 변수를 하나 선언한다. 변수는 반복해 뭔가를 수행할 수 있는 값을 담는 용도이다. `do` 블록 밖에 선언하고, 값은 0으로 초기화한다. 

### Scanner 클래스

코드 맨 위의 `Scanner`라는 class는 `java.util`이라는 패키지가 가진 class이다. java가 미리 만들어놓은 class로 외부에서 값을 입력받고 싶을 때 사용한다. `Scanner`라는 객체가 여러 군데 있을 수 있으므로 정확하게 `java.util` 패키지에 있는 `Scanner`를 사용하겠다고 알려주는 코드이다. 

```java
import java.util.Scanner;
public class DoWhileExam {
	public static void main(String[] args) {
		**int value = 0;**
		**Scanner scan = new Scanner(System.in);
		
		do {
			value = scan.nextInt();
			System.out.println("input value:"+value);
		} while(value != 10);
		System.out.println("iteration ended");**
	}
}
```

이번 실습에서는 키보드로 값을 입력받으려 한다. 따라서 키보드를 의미하는 `System.in`을 사용해 키보드로 값을 입력받는 `class Scanner`를 만들었다.

`Scanner scan = new Scanner(System.in);`

밥솥을 만들 때는 `new 밥솥();` 이렇게 괄호 안에 아무것도 없었는데, `new Scanner(System.in);` 이렇게 하니 달라보이나요? 뒤에 `()`는 생성자라는 것이 들어가는 곳이다. 여기에서 모두 이해하기에는 어렵기 때문에 현재는 **************************************************************************************************************************************************************************************************************************키보드로부터 입력받을 수 있는 스캐너라는 객체를 하나 생성했다고 이해하면 좋겠다.**************************************************************************************************************************************************************************************************************************

`value = scan.nextInt()`라는 코드가 보이나요?

```java
do{
	value = scan.nextInt();
	System.out.println("입력받은 값:"+value);
}
```

밥솥을 설명할 때 내 밥솥은 `b`가 가리키므로 내 밥솥을 사용할 때는 `b`라는 변수를 이용해야 한다고 했다. 마찬가지로 내가 사용할 스캐너는 변수 `scan`이 담고 있으므로 `scan`이라는 변수를 이용한다. `nextInt()` 는 `Scanner` 객체가 가진 메서드이다. 

밥솥의 기능도 여러 가지인 것처럼, ************************************************************************************************************************************************************************************************************************자바의 객체도 여러 기능을 가질 수 있고, 그런 기능을 메서드라는 형식으로 표현한다.************************************************************************************************************************************************************************************************************************ 

또한, 밥솥을 사용할 때 모든 기능을 다 알아야 사용할 수 있는 건 아니듯이, 어떤 객체의 기능을 모두 (알면 더 좋지만) 알지 못해도 사용하는 데 큰 문제는 없다. 

### nextInt()

`nextInt()`는 정수를 입력받아서 반환해주는 기능을 한다.  우리가 지금 만든 `Scanner` 객체는 키보드부터 입력받는 객체이므로 키보드로 정수를 입력해주면 `nextInt()`가 정숫값을 반환해주고, 반환한 값을 변수 `value`에 담아준다. 그럼 우리는 프로그램 안에서 `value`에 담긴 값을 사용할 것이다.

객체를 생성하고, 사용하는 부분이 설명된 것이다. 이 부분은 자바 프로그램의 핵심이므로 뒤에서도 계속 나온다. 지금 완벽히 이해되지 않더라도 계속 사용하다 보면 자연스럽게 이해될 테니 너무 걱정하지 말자!

```java
do {
			value = scan.nextInt();
			System.out.println("input value:"+value);
} **while(value != 10);
System.out.println("iteration ended");**
```

`do while`문과 `while`문의 차이점은 `**do while`문은 조건에 상관없이 무조건 한 번은 실행**해준다는 점이다. `**while`문은 일단 조건부터 비교하고 실행하는 반면에 `do while` 문은 일단 `do`  블록 안 문장을 실행부터 하고, 조건을 비교한다.** 그 외 나머지 실행은 똑같다. 

이번 실습에서는 숫자 10이 입력될 때까지 값을 반복해 입력받는다. 입력받은 값은 `value`에 넣는다. `Scanner`를 `scan`이란 변수가 가리키므로 이 변수가 가리키는 객체 `Scanner`가 가진 기능(메서드) 중에 `nextInt` 메서드를 이용한다. 이 메서드는 정숫값을 입력받아 `value`에 넣어준다. 현재 `scan`이 가리키는 `Scanner` 객체는 키보드로부터 값을 입력받도록 생성됐으므로, 이 메서드는 키보드로부터 정수를 입력받는다. 그리고 입력받은 값은 콘솔에 출력한다.

조건은 `while` 문의 괄호에 넣어준다. `value`가 10이 아니라면 반복문을 계속 수행하라는 의미이다. `value`가 10이라면 반복문을 종료하는데, 알기 쉽게 “반복문 종료!!”라는 문장을 출력하겠다. 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/16dc74c0-3779-4194-a719-6981c13f3197/Untitled.png)

아무 반응이 없나 싶었는데 `Terminate` 사각형에 빨갛게 불이 들어와있다. 실행 중이라는 표시이다. 키보드로 값을 입력받도록 코드를 작성했으니 입력받는 부분에서 기다리고 있는 것이다. 콘솔에 1이라고 입력하겠다. 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/787c8ce7-d539-4bd1-ae32-c951f894498e/Untitled.png)

입력받은 값이 `value`에 들어와 출력된다. `value` 값이 10이 아니기 때문에 다시 `do`로 올라가서 입력받는 부분에서 기다리고 있는 상태이다. 다시 2라고 입력하니 1과 같은 결과가 나온다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/72e3b5b0-952c-4302-be31-ff3dd7708e41/Untitled.png)

입력된 숫자가 10이 아니라면 이 과정을 반복해 수행한다. 이번에는 10을 넣어보자.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/21f03fb8-4c3f-434a-bf72-81f5dc6cf7e1/Untitled.png)

10을 입력하면 마찬가지로 10을 출력하고, `while`문의 조건을 만족시키므로 반복문을 종료한다. 지금까지 `do while`문이라는 반복문을 알아봤다. 

## do while문 실습

`do while` 문을 이용해 스캐너 객체의 `nextInt()` 메서드로 값을 반복적으로 입력받아서 입력받은 모든 값을 더해서 `sum` 변수에 누적해주세요. 단, 입력받은 값이 100보다 크다면 반복문을 종료하도록 조건을 부여해주세요. 반복문을 종료하면 `sum` 값을 출력해주세요.

```java
import java.util.Scanner;
public class DoWhileExam{
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		int value = 0;
		int sum = 0;
		**do {
			value = scan.nextInt();
			sum += value;
		} while(value <= 100);**
		System.out.println("sum: "+sum);
	}
}
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9dad46a1-f80e-4991-ba1a-3a254693445d/Untitled.png)