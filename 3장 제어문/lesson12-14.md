# LESSON 12 if문

### 조건문

지금까지 배운 예제는 모두 main 메서드에서 시작해 그 아래 적힌 문장을 한 줄씩 차례대로 수행했다. 그런데 프로그래밍을 하려면 더 복잡한 조건들을 제어할 수 있어야 한다. 어떤 경우 이 문장은 수행하고, 저 문장은 수행하지 않을 수도 있다. 

**조건문**은 이렇게 모든 문장을 차례대로 수행하지 않고, 설정한 조건에 따라 수행 여부를 결정할 때 사용한다. 

### 자바 조건문: if문, switch문

### if문 사용법

if문 뒤 괄호에 적당한 조건을 설정해 해당 조건을 만족하면 if 블록 안 문장을 수행하고, 조건을 만족하지 않으면 수행하지 않는다. 

```java
if(조건) {
   // 액션
} 
```

if문을 사용하는 방법은 세 가지이다.

1. `if` 혼자 사용하는 방법
    
    ```java
    public class IfExam {
    	
    	public static void main(String[] args) {
    		int x = 50;
    		int y = 60;
    		
    		if(x < y) {
    			System.out.println("x is smaller than y");
    		}
    	}
    }
    // x is smaller than y
    ```
    
    조건을 만족하지 않도록 조건만 바꿔서 다시 실행해보면?
    
    ```java
    public class IfExam {
    	
    	public static void main(String[] args) {
    		int x = 50;
    		int y = 60;
    		
    		if(x > y) {
    			System.out.println("x is smaller than y");
    		}
    	}
    }
    
    // 아무 문장도 실행되지 않았음
    ```
    
    이렇게 if 블록은 안에 들어있는 문장을 항상 실행하는 것이 아니라, 조건에 만족했을 때만 실행한다. 
    
    여기서 if 블록을 더 자세히 살펴보자. 만약에 **if문에 블록이 없다면** 어떤 결과가 나올까?
    
    ```java
    public class IfExam {
    
        public static void main(String[] args) {
            int x = 50;
            int y = 60;
                    
            if(x > y) {
                System.out.println("x는 y보다 큽니다.");
                System.out.println("test 1");
            }
    
            **if(x > y) 
                System.out.println("x는 y보다 큽니다.");
                System.out.println("test 2");**
        }
    }
    
    // test 2
    /* .. 라는데 나는 이클립스에서 에러 뜨네.. -> 파일 이름 ifExam.java로 써서 그랬음 ^.^
    	Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
    	at ifExam.main(IfExam.java:3)
    */
    ```
    
    if문 두 개, 조건 두 개를 작성했다. 내용은 ‘x는 y보다 크다’는 조건으로 같다.
    
    ****if문 안에 블록이 있는 경우****는 **블록 안 문장이 여러 개라고 해도 조건에 따라 실행 여부를 결정**한다. 그러나 ********************************************************************if문 안에 블록이 없는 경우********************************************************************에는 **if문 바로 아래에 있는 한 행만 영향을 받는다.** 따라서 그 다음 행인 ‘`System.out.println("test 2");`'는 if문의 조건과 상관없이 출력된 것이다. 
    
2. `if-else`를 사용하는 방법
    
    ```java
    public class IfExam {
    	
    	public static void main(String[] args) {
    		int x = 50;
    		int y = 60;
    		
    		if (x == y) {
    			System.out.println("x is same with y");
    		} else {
    			System.out.println("x is different from y");
    		}
    		
    	}
    }
    
    // x is different from y
    ```
    
3. `if - else if - else`를 사용하는 방법
    
    ```java
    public class IfExam {
    	
    	public static void main(String[] args) {
    		int x = 50;
    		int y = 60;
    		
    		if (x == y) {
    			System.out.println("x is same with y.");
    		} else if (x > y) {
    			System.out.println("x is bigger than y.");
    		} else if (x < y) {
    			System.out.println("x is smaller than y");
    		}
    	}
    }
    
    // x is smaller than y
    ```
    
    ************************************************************************************************************************************************************만약 여러 조건 중에서 맞는 조건이 하나도 없다면 어떻게 될까?************************************************************************************************************************************************************
    
    앞에서와 마찬가지로 콘솔에는 아무 것도 출력되지 않을 것이다. 이럴 때 `if-else` 문을 활용해 마지막에 `else`를 넣으면 맞는 조건이 하나도 없어도 결과를 출력할 수 있다. 
    
    ```java
    public class IfExam {
    	
    	public static void main(String[] args) {
    		int x = 50;
    		int y = 60;
    		
    		if (x == y) {
    			System.out.println("x is same with y.");
    		} else if (x > y) {
    			System.out.println("x is bigger than y.");
    		} **else  {
    			System.out.println("x is different from y");
    		}**
    	}
    }
    
    // x is different from y
    ```
    
    ************************else if 구문은 몇 개든 붙여서 사용할 수 있다. 하지만 구문이 많아질수록 실행 속도가 느려지므로 주의하자.************************
    

## 정리

### if문

- 조건식이 true일 경우에만 실행문을 실행한다.
    - 조건식 안에는 결괏값이 `true`나 `false`인 문장만 넣을 수 있다.
- if(조건식) 다음의 {}를 생략할 수 있다. 하지만 생략할 경우 if 문에 포함되는 실행문은 단 한 줄만 포함된다.
    
    ```java
    if(조건식) {
    		실행문;
    }
    ```
    

### if-else 문

- 조건식이 true일 경우 if 블록의 실행문을 실행하고, false일 경우 else 블록의 실행문을 실행한다.
    
    ```java
    if(조건식) {
    	실행문;
    } else {
    	실행문;
    }
    ```
    

### if-else if-else문

- 처음 if문의 조건식이 true일 경우 처음 if 문의 블록을 실행하고, false일 경우 다음 조건식의 결과에 따라 실행 블록이 달라진다.
- else if 문의 수는 제한이 없다. 그러나 else if 문이 너무 많으면 실행 속도가 느려진다.
- 마지막 else 블록은 생략해도 상관없다.

```java
if(조건식) {
	실행문;
} else if(조건식) {
	실행문;
} else {
	실행문;
}
```

## if문 실습 1

```java
public class IfExam {
	
	public static void main(String[] args) {
		int value = 6;
		
		if(**value % 3 == 0**) {
			System.out.println(value+" is a multiple of 3.");
		}
	}
}

// value의 값이 6일 경우 : 6 is a multiple of 3
// value의 값이 5일 경우 : 아무것도 출력되지 않음.
```

## if문 실습 2

다음 코드는 변수 `value`가 3인지를 검사해 3의 배수라면 `ret`에 3을 저장한다. `if`문 이후(8행)에 `else if` 구문을 추가해 `value`가 4의 배수인지를 검사하고, 4의 배수라면 `ret`에 4를 저장하도록 만들어보세요.

```java
public class IfExam{
	public int IfTest(int value) {
		// 변수 value가 선언됐다고 가정하고 코드를 작성하라.
		int ret = 0;
		if(value % 3 == 0) {
			ret = 3;
		} **else if(value % 4 == 0) {
			ret = 4;
		}**
		return ret; // 결과 체크를 위한 코드입니다.
	}
	// 아래는 실행을 위한 코드입니다. 수정하지 마세요.
	public static void main(String[] args) {
		IfExam exam = new IfExam();
		System.out.println(exam. IfTest(6));
		System.out.println(exam. IfTest(8));
	}
	
}

// 3
// 4
```

문제에서 제시한 `IfTest`라는 메서드는 인자로 들어오는 값에 따라서 실행결과가 달라진다. `main` 메서드에서 `exam.IfTest(6)`이라고 호출하면 6이라는 값을 매개변수로 전달한다. 

`public int IfTest(int value)` 이렇게 정의된 메서드를 실행하는데 이때 메서드의 매개변수로 선언한 `int value`에 인자로 보낸 6이라는 값을 저장한다.


# LESSON 13 논리 연산자

논리 연산자나 삼항 연산자는 앞에서 배운 산술 연산자나 비교 연산자에 비해 약간 더 어렵다.

알아볼 논리 연산자는 모두 네 가지이다. 

첫 번째 A와 B는 피연산자이고, 그 옆에 나온 네 가지 연산자가 논리 연산자이다.

| A | B | A && B | A || B | !A |  A ^ B |
| --- | --- | --- | --- | --- | --- |
| true | true | true | true | false | false |
| true | false | false | true | false | true |
| false | true | false | true | true | true |
| false  | false | false | false | true | false |

## 논리곱 &&(and 연산자)

- 피연산자가 모두 `true`일 때만 `true`를 반환한다.

```java
public class LogicalOperatorExam {
	public static void main(String[] args) {
		boolean b1 = true;
		boolean b2 = false;
		boolean b3 = true;
		
		System.out.println(b1 && b2);
		System.out.println(b1 && b3);
	}
}

// false
// true
```

## 논리합 || (or 연산자)

- 피연산자가 둘 중 하나만 `true`값을 가져도 `true`를 반환한다.

```java
public class LogicalOperatorExam {
	public static void main(String[] args) {
		boolean b1 = true;
		boolean b2 = false;
		boolean b3 = true;
		
		System.out.println(b1 || b2);
		System.out.println(b1 || b3);
		System.out.println(b2 || b2);
	}
}

// true
// true
// false
```

## 논리부정 ! (not 연산자)

- 단항 연산자이므로 피연산자 중 A만 보면 된다.
- A 앞에 붙어서 결과를 반대로 바꿔준다.

```java
public class LogicalOperatorExam {
	public static void main(String[] args) {
		boolean b1 = true;
		boolean b2 = false;
		
		System.out.println(!b1);
		System.out.println(!b2);
	}
}

// false
// true
```

이런 논리 연산자는 언제 사용할까?

먼저 `int`형 변수 `score`를 선언하고, 88이라는 값을 넣는다. 그리고 `if문`을 사용해 원하는 조건을 작성한다. 즉, 70~100의 값은 70보다 크거나 같고, 100보다 작거나 같아야 한다. 

```java
public class LogicalOperatorExam {
	public static void main(String[] args) {
		int score = 88;
		**if(score >= 70 && score <= 100) {
			System.out.println("성공");
		} else {
			System.out.println("실패");
		}**
	}
}

// 성공
```

이런 조건을 처리할 때 간혹 조건 하나로 문제를 해결하려고 하지만, 자바는 이를 조건 하나로 처리할 문법은 없으므로, 조건을 나누어 생각해야 한다. 

변수 `score`의 값을 범위 밖 값으로 바꿔서 실행하면 ‘`실패`’라고 뜬다.

```java
public class LogicalOperatorExam {
	
	public static void main(String[] args) {
		**int score = 65;**
		if(score >= 70 && score <= 100) {
			System.out.println("success");
		} else {
			System.out.println("fail");
		}
	}
}

// fail
```

## 배타적 논리합 ^

- 피연산자가 하나는 `true`이고, 하나는 `false`일 때만 `true`를 반환한다.
- ******************************************두 개가 달라야만 `true`를 반환한다.**

```java
public class LogicalOperatorExam {
	public static void main(String[] args) {
		boolean b1 = true;
		boolean b2 = false;
		boolean b3 = true;
		
		System.out.println(b1 ^ b3);
		System.out.println(b1 ^ b2);
	}
}

// false
// true
```

→ 배타적 논리합은 두 식이 다를 때 `true`를 반환한다. 

## 논리 연산자 실습 1

나이가 19세 이하이거나 60세 이상이면 할인해주려고 한다. 

`int`형 변수 `age`의 값을 검사해 할인 대상인지 알아보겠다. 할인 대상이라면 `isDiscount`에 `true`를, 그렇지 않으면 `isDiscount`에 `false`를 저장하도록 만들어보자. 

```java
public class LogicalOperatorExam {
	
	public boolean isAgeDiscountable(int age) {
		boolean isDiscount = false;
		if(**age <= 19 || age >= 60**) {
			isDiscount = true;
		} else {
			isDiscount = false;
		}
	
		return isDiscount; // 결과 테스트를 위한 코드
	}

	// 실행을 위한 코드. 수정하지 말 것.
	public static void main(String[] args) {
		LogicalOperatorExam exam = new LogicalOperatorExam();
		System.out.println(exam.isAgeDiscountable(15));
		System.out.println(exam.isAgeDiscountable(27));
		System.out.println(exam.isAgeDiscountable(61));
	}
}

// true
// false
// true
```

## 논리 연산자 실습 2

`int`형 변수 `age`의 값을 검사해 `age`가 20대인지 검사하려고 한다.  20대라면 `isTwenties`에 `true`를, 그렇지 않으면 `false`를 저장하도록 만들어라.

```java
public class LogicalOperatorExam {
	
	public boolean isAgeTwenties(int age) {
		boolean isTwenties = false;
		if(**age >= 20 && age <= 29**) {
			isTwenties = true;
		} else {
			isTwenties = false;
		}
		
		return isTwenties; // 결과 테스트를 위한 코드입니다.
	}

	// 실행을 위한 코드. 수정하지 말 것.
	public static void main(String[] args) {
		LogicalOperatorExam exam = new LogicalOperatorExam();
		System.out.println(exam.isAgeTwenties(19));
		System.out.println(exam.isAgeTwenties(25));
		System.out.println(exam.isAgeTwenties(30));
	}
}

// false
// true
// false
```


# LESSON 14 삼항 연산자

if문과 살짝 비슷한 삼항 연산자를 알아보자.

우선 `TernaryExam` 클래스를 만들고 값을 담을 변수를 하나 선언한다. `int`형 변수 `b1`를 선언한 뒤에 나오는 부분이 바로 삼항 연산자이다.

```java
public class TernaryExam {
	
	public static void main(String[] args) {
		int b1 = (5 > 4) ? 50 : 40;
		
		System.out.println(b1);
	}
}

// 50
```

삼항 연산자 부분을 자세히 살펴보면, 먼저 괄호 안을 수행한다. 

‘괄호 안 식이 참이라면 50을, 거짓이라면 40을 `b1`에 넣어주세요.’ 라는 의미.

실행결과를 예상하면 5는 4부다 크기 때문에 참이다. 따라서 `b1`에는 50이라는 값이 들어있다. 

부등호를 반대로 바꾸면 ‘5가 4보다 작다면 b1에 50을, 아니라면 b1에 40을 넣어달라’ 는 의미.

```java
public class TernaryExam {
	
	public static void main(String[] args) {
		int b1 = (5 < 4) ? 50 : 40;
		
		System.out.println(b1);
	}
}

// 40
```

삼항 연산자의 처리 흐름은 `if`문과 비슷하다. 예를 들어 앞에서 실습한 삼항 연산자 코드를 `if`문으로 바꿔보자. 

똑같이 값을 담을 변수를 하나 선언한다. `int`형 변수 `b2`를 선언하고 일단 0으로 초기화한다. 그리고 `if`문을 사용한다. 조건도 똑같이 ‘5가 4보다 크다’로 작성한다. 이 조건이 참이라면 `b2`에 50을 넣고, 거짓이라면 `b2`에 40을 넣는다. 

```java
public class TernaryExam {
	
	public static void main(String[] args) {
		
		**int b2 = 0;
		if(5 > 4) {
			b2 = 50;
		} else {
			b2 = 40;
		}**
		
		System.out.println(b2);
	}
}
```

## 정리

삼항 연산자의 괄호 안에는 다양한 조건식이 들어올 수 있다. 

5나 4처럼 정해진 숫자가 아니라 어떤 값이 들어올 지 모르는 변수가 들어올 수도 있다.

- `(**조건식) ? 피연산자1 : 피연산자2**`
    - 조건식의 연산 결과가 참이면 결과는 피연산자 1
    - 조건식의 연산 결과가 거짓이면 결과는 피연산자 2

## 삼항 연산자 실습

`hour`에는 현재 시간이 들어있다. 삼항연산자를 이용해 `hour`가 12보다 작으면 “오전”, 그렇지 않으면 “오후”라는 값을 `ampm`이 가지도록 수정하라. 

- `Calendar` 객체는 내 컴퓨터의 현재 시간을 이용해 객체를 생성한다.
- `Calendar`를 사용하면 현재 시스템상 시간을 구할 수 있다.
    - 시간은 24시간 단위 (ex. 오후 1시일 경우 13시)로 나온다.

```java
import java.util.Calendar;

public class TernaryExam {
	public static void main(String[] args) {
		// hour에는 현재 시간이 24시간 단위로 들어있다.
		int hour = Calendar.getInstance().get(Calendar.HOUR_OF_DAY);
		String ampm;
		// 삼항 연산자를 이용해 ampm에 오전 또는 오후의 값을 가지도록 만들어보세요.
		**ampm = (hour < 12) ? "AM" : "PM";**
		System.out.println("It is "+hour+" o'clock, "+ampm+".");
	}
}

// It is 20 o'clock, PM. (테스트 당시 시간 20:33)
```