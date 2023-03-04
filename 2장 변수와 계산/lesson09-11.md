# LESSON 09 산술 연산자

## 연산, 연산자

여기서는 연산자와 연산식을 알아보자. 

********연산********이란 **데이터를 처리해 결과를 산출**한다는 의미이다. 다음 문장을 읽어보자.

```java
x = y + z;
```

이 문장의 의미는 ‘y와 z를 더한 값을 x에 대입한다’이다. 여기에서 ‘`=`'과 ‘`+`'는 **연산에 사용하는 표시와 기호**라는 의미로 **연산자**라고 한다. 각각 **************************대입 연산자**************************와 ****************************산술 연산자****************************에 해당한다. `y`와 `z`는 **연산 대상이 되는 데이터**라는 의미로 **피연산자**라고 한다. 이렇게 연산자와 피연산자를 이용해 연산 과정을 기술한 ‘`x = y + z`’를 **연산식**이라고 한다. 

❗ **연산**

데이터를 처리해 결과를 산출하는 것

❗ **연산자**

연산에 사용하는 표시와 기호

- 대입연산자
- 산술 연산자

❗ **피연산자**

연산 대상이 되는 데이터

❗ **연산식**

연산 과정을 기술한 식

간단하게 몇 가지 자바 연산자를 알아보자

## 부호 연산자(`+`, `-`)

부호 연산자는 피연산자의 부호를 결정한다.

`OperatorExam` 클래스를 만들고, `int`형 변수 `i1`에 `-5`라는 값을 넣어봊. 

‘`-`'가 ****************************부호 연산자, `5`**는 ******************************피연산자******************************이다. 이처럼 ****************************************************************************************************피연산자가 1개인 연산식의 연산자****************************************************************************************************를 **************************단항 연산자**************************라고 한다.  

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i1 = -5;
		System.out.println(i1);
	}
}
```

부호 연산자는 다음과 같이 변수 앞에도 붙일 수 있다.

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i1 = -5;
		int i2 = +i1;
		int i3 = -i1;
		System.out.println(i1);
		System.out.println(i2);
		System.out.println(i3);
	}
}

// -5
// -5
// 5
```

변수 앞에 붙은 부호 연산자는 플러스 마이너스 부호를 바꿔주는 것이 아니다. 

‘`+`' 는 부호 비트를 그대로 유지시키고, ‘`-`'는 음수를 양수로 바꾸고 양수를 음수로 바꿔준다. ‘`-`' 부호 비트를 붙여서 대입시킨 `i3`을 출력하면 양수 5가 출력된다.

## 증감 연산자(`++` , `--`)

증감 연산자에는 ‘`++`', ‘`--`'가 있으며 피연산자 앞이나 뒤에 붙일 수 있음.

**증감 연산자를 다른 식과 함께 사용하지 않는다면, 증감 연산자가 앞에 오나 뒤에 오나 결과가 같음.**

ex) `++i3`과 `i3++` , `--i3`과 `i3--` 은 같은 의미. `i3`의 값을 1 증가시키고, `i3`의 값을 1 감소시킴.  

하지만 ********************증감 연산자를 다른 식과 함께 사용하면, 증감 연산자가 피연산자 앞에 붙느냐, 뒤에 붙느냐에 따라 연산 결과가 달라진다.********************

먼저 `i4`에 `++i3`을 넣어보자. `i3`에는 이전 실습에서 `5`라는 값을 넣어놓았기 때문에, `**i4`에는 `5`에 `1`을 더한 `6`이 들어가 있다.**

`**i3`도 출력하면 역시 `6`이 들어가 있다!**

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i1 = -5;
		int i2 = +i1;
		int i3 = -i1;
		**int i4 = ++i3; // int i4 = ( i3 = i3+1)
		System.out.println(i4);
		System.out.println(i3);**
	}
}
// 6
**// 6**
```

이번에는 `i5`를 선언하고 `i3` 뒤에 `++`를 붙여보자. 

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i1 = -5; 
		int i2 = +i1; // -5
		int i3 = -i1; // 5
		int i4 = ++i3; // int i4 = ( i3 = i3+1) 
		int i5 = i3++; // int i5 = i3; i3 = i3+1; 
		System.out.println(i5);
		System.out.println(i3);
	}
}
// 6
// 7
```

이번에는 `i5`를 선언하고 `i3` 뒤에 `++`를 붙여보자. 앞의 코드와 마찬가지로 `i3`에 1을 더하라는 의미.`i5`와 `i3`을 출력하면 둘 다 6에서 1을 더한 값인 7이 나올까?

`i5`를 출력하니 7 대신 6이라는 결과가 나온다.

**‘`++`'가 앞에 붙어있을 때**는 **먼저 `i3`에 1을 더한 다음, 더한 결괏값을 해당 변수에 넣어준다.** 그런데 **‘`++`'가 뒤에 붙어있을 때는 해당 변수에 먼저 값을 넣은 다음 `i3`에 1을 더한다.** 

즉, `i3`에 들어있던 6을 먼저 `i5`에 대입한 다음 `i3`에 1을 더한 것이다. 따라서 `i3`을 출력하면 `i3`은 늘어난 7을 출력한다. 이 과정은 ‘`--`'의 경우에도 똑같이 수행한다.

 

이렇게 단항 연산을 해봤다. 증감 연산자도 단항 연산자다. 

## 산술 연산자(`+`, `-`, `*`, `/`, `%`)

산술 연산자는 피연산자 하나로는 연산할 수 없다. 이런 연산자를 ****************************************************이항 연산자****************************************************라고 한다. 

### 기본

산술 연산을 하기 위해서 i라는 변수에 5라는 값을 j라는 변수에 2라는 값을 넣어 초기화하자. 이렇게 변수 두 개를 선언한 후에 산술 연산을 실행한다. 

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i = 5;
		int j = 2;
		System.out.println(i + j);
		System.out.println(i - j);
		System.out.println(i * j);
		System.out.println(i / j);
	}
}

// 7
// 3
// 10
// 2
```

`+`

`-`

`*`

`/` : ‘왼쪽에 있는 피연산자를 오른쪽 피연산자로 나누어서 그 **몫**을 구해주세요.’ 라는 의미. 

5를 2로 나누면 2.5인데 왜 2가 나왔을까?

**********************************************변수가 정수와 정수(`int x,` `int y`)로 선언**했기 때문에 **피연산자 역시 정수**이기 때문이다. **정수끼리의 연산은 정숫값으로만 반환**된다.

### 캐스팅 연산자

두번째 문제~

만약 나눈 결과로 2.5라는 값을 얻고 싶다면? 답은 ************************************************************************************************************************피연산자 둘 중에 최소한 하나가 실수여야 한다.************************************************************************************************************************ 

앞에서 공부한 ******************형변환******************을 사용해서 `j`를 `double`형으로 형변환한다. 이런 것을 ********************************캐스팅 연산자********************************라고도 한다. 단항 연산자이다. `j`를 실수형으로 바꾸고 난 다음 다시 연산하면 `2.5`라는 실숫값을 얻을 수 있다. 

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i = 5;
		int j = 2;
		System.out.println(i / **(double) j**);
	}
}

// 2.5 
```

### 모듈러 연산자

나눈 나머지 값을 출력한다. 

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i = 5;
		int j = 2;
		**System.out.println(i % j);**
	}
}

// 1
```

```java
public class OperatorExam {
	
	public static void main(String[] args) {
		int i = 5;
		int j = 2;
		**System.out.println(i % (double)j);**
	}
}

// 1.0
```

# 산술 연산자 실습

```java
public class OperatorExam {
	
	public void calculate() {
		int a = 7;
		int b = 3;
		**int c = a + b;
		int d = a - b;
		int e = a * b;
		int f = a / b;**
		
		System.out.println("a와 b의 합 : "+ c);
		System.out.println("a와 b의 차 : "+ d);
		System.out.println("a와 b의 곱 : "+ e);
		System.out.println("a를 b로 나눈 나머지 : "+ f);
	}
	
	public static void main(String []args) {
		new OperatorExam().calculate();
	}
}
```

# LESSON 10 비교 연산자

이번 장에서는 비교 연산자와 대입 연산자를 살펴본다. 

`==` : 같다

`!=` : 다르다

`>` : 크다

`<` : 작다

`>=` : 크거나 같다

`<=` : 작거나 같다

비교 연산자는 항상 실행결과로 `boolean` 값인 `true` 또는 `false`를 반환한다.

## 비교 연산자

`OperatorExam2` 클래스를 만들어 `int`형 변수 `i`와 `j`에 10을 넣는다. 그리고 `j`와 `j`, 두 변수에 비교 연산자를 사용한 뒤 결과를 출력한다. 첫 번째로 `i`와 `j`가 같은지를 물어본다. 

```java
public class OperatorExam2 {
	
	public static void main(String[] args) {
		int i = 10;
		int j = 10;
		
		**System.out.println(i == j);**
	}
}
// true
```

지금까지 사용한 ‘`=`'은 변수에 값을 넣는다는 의미였다. ‘`==`'는 왼쪽 피연산자와 오른쪽 피연산자가 서로 같은지를 물어보는 것이다. 

두 번째로 `i`와 `j`가 다른지를 물어보자. 

```java
public class OperatorExam2 {
	
	public static void main(String[] args) {
		int i = 10;
		int j = 10;
		
		System.out.println(i == j);
		**System.out.println(i != j);**
	}
}

// true
// false
```

i와 j의 값은 같기 때문에 false를 출력한다. 

앞에서 봤던 비교 연산자들을 차례대로 실행하자.

```java
public class OperatorExam2 {
	
	public static void main(String[] args) {
		int i = 10;
		int j = 10;
		
		System.out.println(i == j);
		System.out.println(i != j);
		System.out.println(i < j);
		System.out.println(i <= j);
		System.out.println(i > j);
		System.out.println(i >= j);
	}
}

// true
// false
// false
// true
// false
// true
```

## 대입 연산자

### 단순 대입 연산자

‘ `=` ’ : 왼쪽에 있는 피연산자인 변수에 오른쪽에 있는 피연산자의 값을 저장해주세요.

### 복합 대입 연산자

복합 대입 연산자를 이용하면 연산식을 간단하게 쓸 수 있다.

‘ `+=` ’, ‘ `-=` ’ : 정해진 연산을 수행한 후에 결과를 변수에 저장한다. 

```java
public class OperatorExam2 {
	
	public static void main(String[] args) {
		int i = 10;
		int j = 10;
		
		i += 10; // i = i + 10
		System.out.println(i);
	}
}

// 20
```

```java
public class OperatorExam2 {
	
	public static void main(String[] args) {
		int i = 10;
		int j = 10;
		
		**i += 10;**
		System.out.println(i);
		System.out.println(i **-=** 5); // i = i - 5
	}
}
```

## 비교 연산자 실습

```java
public class OperatorExam2 {
	
	public void calculate(int a, int b) {
		
		// a가 b보다 큰지 비교한 결과(true 또는 false)를 c에 저장하세요.
		**boolean c = a > b;**
		
		// a와 b가 같은지 비교한 결과를 d에 저장하세요.
		**boolean d = a == b;**
		
		// a와 b가 다른지 비교한 결과를 e에 저장하세요.
		**boolean e = a != b;**
		
		System.out.println(a + "은(는) " + b + "보다 큽니까?" + c);
		System.out.println(a + "은(는) " + b + "와(과) 같습니까?" + d);
		System.out.println(a + "은(는) " + b + "와(과) 다릅니까?" + e);
	}
	
	public static void main(String[] args) {
		// 0~10 사이 값을 랜덤하게 변수 a와 b에 넣어준다.
		int a = (int)(Math.random()*10);
		int b = (int)(Math.random()*10);
		new OperatorExam2().calculate(a, b);
	}
}
```

`int a = (int)(Math.random()*10);`

`Math.random()`은 0.0 이상에서 1.0 미만의 랜덤한 `double`형의 실숫값을 반환한다.

`Math.random()*10`은 0.0에서 10.0 미만의 랜덤한 값을 반환한다.

`(int)(Math.random()*10)` : 이렇게 `int`형으로 형변환을 하면 **소수점 뒤의 값은 없어진다.** 즉 0~9 사이의 값을 변수 `a`와 변수 `b`에 담아주겠다는 이야기다.


# LESSON 11 연산자 우선순위

연산자 우선순위랑 연산자가 여러 개 나왔을 때 어떤 연산자를 먼저 계산하느냐 하는 문제이다.

## 연산자 우선순위

자바에서 사용하는 연산자의 우선순위는 다음 표와 같다. 위에서 아래로 내려갈수록 연산자 우선순위가 낮아진다. 

| 0 | 최우선 연산자 | . [] () |
| --- | --- | --- |
| 1 | 단항 연산자 | ++ -- ! ~ +/- : 부정, bit변환 > 부호 > 증감 |
| 2 | 산술 연산자 | * / % + - |
| 3 | 시프트 연산자 | >> << >>> |
| 4 | 비교 연산자 | > < >= <= == != |
| 5 | 비트 연산자 | & | ^ ~ |
| 6 | 논리 연산자 | && || ! |
| 7 | 삼항 연산자 | 조건식 ? |
| 8 | 대입 연산자 | = *= /= %= += -= |
- ‘`&&`’ : 논리곱, and 연산자.
    - 양쪽이 모두 true일 때만 true를 반환.
- ‘`||`’ : 논리합, or 연산자
    - 한쪽만 true여도 true를 반환한다.
- ‘`!`’ : 부정의 의미, not 연산자.
    - `boolean`의 값을 역전시킨다.

먼저 `OperatorExam3` 클래스를 만들어 `int`형 변수 세 개를 선언하고 각각 5, 10, 15라는 값을 넣는다. 그리고 세 변수를 연산해 값을 출력한다. 

‘`a - b * c` ’라는 계산식을 출력한다. 곱하기가 빼기보다 우선순위가 높기 때문에 ‘`b * c`‘를 먼저 연산한다. 

```java
public class OperatorExam3 {
	
	public static void main(String[] args) {
		int a = 5;
		int b = 10;
		int c = 15;
		
		System.out.println(a - b * c);
	}
}

// -145
```

두 번째 식은 ‘`a - b`’를 먼저 계산하고 그다음에 `c`를 곱하므로 첫 번째 식과는 결과가 다르게 나온다.

```java
public class OperatorExam3 {
	
	public static void main(String[] args) {
		int a = 5;
		int b = 10;
		int c = 15;
		
		System.out.println(a - b * c);
		**System.out.println((a - b) * c);**
	}
}

// -145
// -75
```

이번에는 “a가 5보다 크거나, and 연산자, b가 5보다 큽니까?” 라고 물어보는 연산식이다. 비교 연산자가 논리 연산자보다 우위이기 때문에 `false && true`를 연산해야 한다. 

```java
public class OperatorExam3 {
	
	public static void main(String[] args) {
		int a = 5;
		int b = 10;
		int c = 15;
		
		**System.out.println(a > 5 && b > 5);**
	}
}

// false
```

```java
public class OperatorExam3 {
	
	public static void main(String[] args) {
		int a = 5;
		int b = 10;
		int c = 15;
		
		System.out.println(a > 5 && b > 5);
		System.out.println(a > 5 || b > 5);
	}
}

// false
// true
```

### 증감 연산자 조심!

이번에는 증감 연산자를 살펴보자.

먼저 **전위 연산자**이다. ‘`++a - 5`’ 라는 연산식에서 연산자 우선순위를 생각해보면.. 증감연산자는 단항 연산자이므로 산술 연산자보다 우선순위가 높다. 즉, 증감 연산자를 먼저 실행하고 그 다음에 5를 뺀다. 

증감 연산자인 ‘`++a`’는 ‘`a = a + 1`’과 같으므로 연산 결과는 6이다. 6에서 5를 빼면 결과는 1이므로 결과는 1을 출력한다.

이때 a에는 어떤 값이 들어있을까? ‘`a = a + 1`’이므로 6이 들어있다. 

```java
public class OperatorExam3 {
	
	public static void main(String[] args) {
		int a = 5;
		int b = 10;
		int c = 15;
		
		**System.out.println(++a - 5);**
		System.out.println(a);
	}
}

// 1
// 6
```

만약 **후위 연산자**라면 어떻게 될까?

증가시키기 전에 연산하고 출력하기 때문에 0을 출력한다. 출력한 후에 ‘`a++`’, 즉 ‘`a = a + 1`’을 수행하므로 a에는 6이라는 값이 들어있다. 

```java
public class OperatorExam3 {
	
	public static void main(String[] args) {
		int a = 5;
		int b = 10;
		int c = 15;
		
		**System.out.println(a++ - 5);
		System.out.println(a);**
	}
}

// 0
// 6
```

### 전위 연산자, 후위 연산자 비교

`**System.out.println(++a - 5)` 의 연산 순서**

1. ++a 수행 → 5 + 1 → a는 6
2. a - 5 수행 → 6 - 5 → 결과는 1
3. System.out.println()에 값 1 전달

`**System.out.println(a++ - 5)`의 연산 순서**

1. a - 5 수행 → 5 - 5 → 결과는 0
2. System.out.println()에 1의 값 0을 전달
3. a++ 수행 → 5 + 1 → a는 6