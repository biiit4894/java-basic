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