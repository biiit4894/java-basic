# LESSON 19 배열 만들기

Part 4에서는 배열(array)를 배워보자. 배열이란 무엇일까? 배열은 어떤 상황에서 사용할까?

## 배열이란?

프로그래밍을 하다 보면 변수가 여러 개 필요할 때가 있다. 예를 들어 학생 1,000명의 점수를 저장해야 한다. 학생이 1,000명이니 점수도 1,000개, 이를 저장할 변수도 1,000개가 필요하다. 이렇게 변수가 많아지면 변수를 선언하는 것만으로도 힘들 것이다. 이럴 때 배열을 사용한다.

즉, ************************************************************************\*\*************************************************************************배열은 데이터형이 같은 변수가 여러 개 필요할 때 사용한다.\*\* 변수는 하나인데 값은 여러 개 들어간다.

## 다양한 배열 생성 방식

자, 배열을 실습해보자. 정수 100개를 저장할 수 있는 배열을 만들어보자. 정수를 저장하므로 `int`형 변수여야 한다. `int`형 변수를 선언하는 형식이 앞에서 선언해본 `int`형 변수와는 조금 다르다. 지금 선언하는 것은 배열이므로 자료형 `int` 다음에 배열을 나타내는 대괄호를 넣고 배열명을 `array1`로 넣어 선언한다.

다음으로 배열을 생성한다. 이때 반드시 `new`라는 키워드를 사용해야 한다. `int`형을 담을 것이고, 100개를 담는다고 지정한다. 배열은 처음 선언할 때 만든 크기가 변하지 않는다. 이것으로 정숫값 100개를 저장할 수 있는 `int`형 배열 `array1`을 생성했다.

```java
public class ArrayExam {
	public static void main(String[] args) {
		int[] array1 = new int[100];
	}
}
```

배열에 값을 넣어줄 때는 배열의 이름과 배열 표시인 대괄호 안에 인덱스(index)를 적어줘야 한다.

### 인덱스

******\*\*******인덱스******\*\*******가 뭘까? 인덱스를 잠시 설명하고 넘어가자. **배열은 저장 공간이 여러 개인데 변수는 배열 전체를 가리키기 때문에 배열 안 값을 하나씩 가리킬 방법이 필요하다.** 그래서 **배열의 여러 공간에 번호를 붙여놓았다.** 그것이 바로 인덱스이다. 인덱스를 이용하면 배열의 몇 번째 값을 가리키는지 알 수 있다.

자바는 인덱스를 0번부터 사용하므로 100개라면 인덱스느 0~99까지 사용할 수 있다. 즉, 다음과 같은 형식으로 배열 `array1`의 0번 인덱스에 50이라는 값을 담는다. 배열 `array1`의 10번 인덱스에 100이라는 값을 담는다.

```java
public class ArrayExam {
	public static void main(String[] args) {
		int[] array1 = new int[100];

		array1[0] = 50;    // 배열 array1의 0번 인덱스에 50이라는 값을 담는다.
		array1[10] = 100;  // 배열 array1의 10번 인덱스에 100이라는 값을 담는다.
	}
}
```

지금까지 설명한 내용을 그림으로 다시 살펴보자. `int`형의 `array1`이라는 이름으로 배열을 선언한다. 그림과 같이 정수 네 개를 담을 수 있는 배열이다.

```java
int[] array1 = new int[4];
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/de8172ad-0551-41ab-b80d-47d4d348749f/Untitled.png)

사용할 때는 배열명과 인덱스를 넣어준다. 사용할 수 있는 인덱스는 0~3까지이다. 0번 인덱스에는 1, 1번 인덱스에는 2, … … 이렇게 값을 담았다면 이 배열에는 값이 1, 2, 3, 4 이렇게 담길 것이다.

즉, 배열은 메모리 공간 하나에 정숫값 네 개를 가지는 것이 아니라, 그림처럼 메모리 네 칸에 각각 정숫값을 담은 것이라고 기억하면 된다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8460bb79-32e0-45fd-82a9-4fffcc971a71/Untitled.png)

배열을 사용하는 방법은 다양하다. 배열을 선언하고 동시에 값까지 초기화할 수 있다. `int`형 배열 `array2`를 선언하겠다. 앞에서는 처음부터 배열 크기를 결정했다. (`int[] array1 = new int[100]`) 이번에는 크기를 넣지 않고 곧바로 값을 담아준다. 즉, 다음 코드는 정숫값 네 개를 담는 배열을 생성하고, 그 배열에 각각 1, 2, 3, 4라는 값을 넣는다는 의미이다.

```java
public class ArrayExam {
	public static void main(String[] args) {
		**int[] array2 = new int[]{1,2,3,4};**
	}
}
```

이렇게 선언하고 초기화하는 방법을 더 간단하게 바꿀 수도 있다. `new`라는 코드 없이 `{1, 2, 3, 4}` 처럼 값을 넣어서 사용할 수 있다. 이 방법은 앞 예제에서 `new int[]{1,2,3,4}`와 똑같은 의미로 파악돼 실행된다. 사용자 편의를 위해서 `new int[]`가 없지만 마치 있는 것 처럼 해석해 실행시키는 것이다.

```java
public class ArrayExam {
	public static void main(String[] args) {
		int[] array2 = new int[]{1,2,3,4};
		**int[] array3 = {1,2,3,4};**
	}
}
```

지금까지 배열을 생성하고, 생성한 배열에 값을 넣어봤다. 넣은 값을 꺼내서 사용할 수도 있을 것이다. 이제 배열에 들어있는 값을 꺼내서 사용하겠다. 꺼내서 사용할 때는 배열명과 몇 번째 값을 꺼낼 것인지 인덱스를 적어주면 된다. 단순히 꺼내기만 하면 배열은 별다른 작업을 하지 않기 때문에 `println`으로 콘솔에 출력하겠다.

```java
public class ArrayExam {
	public static void main(String[] args) {
		int[] array2 = new int[]{1,2,3,4};
		int[] array3 = {1,2,3,4};

		**System.out.println(array3[3]);**
	}
}

// 4
```

실행결과 4라고 출력한다. `array3`이 가리키는 0, 1, 2, 3번 중에 3번 인덱스에 들어있는 값이 4이기 때문에 4라는 값이 나왔다.

다른 곳에서 사용하고 싶다면 값을 꺼내온다. `int`형 배열에 들어있는 값을 꺼내오므로 똑같이 `int`형 변수 `value`를 하나 마련하고, 변수 `value`에 배열 `array3`의 0번 인덱스에 있는 값을 꺼내서 담는다.

```java
public class ArrayExam {
	public static void main(String[] args) {
		int[] array2 = new int[]{1,2,3,4};
		int[] array3 = {1,2,3,4};

		**int value = array3[0];
		System.out.println(value);**
	}
}

// 1
```

이렇게 배열에 넣어둔 값을 변수 `value` 안에 넣고, `value`를 이용해서 이 값을 사용할 수 있겠다. 이뿐 아니라 반복문인 `for` 문과 인덱스를 이용해 배열 값을 차례대로 꺼내거나, 넣을 수도 있다. 이 방법은 다음 장에서 더 자세히 알아보자.

지금까지 배열의 기초와 ************\*\*************1차원 배열************\*\*************을 살펴봤다. 배열은 기본 자료형이 아니라 이 부분을 참조하는 참조형이라는 것을 기억하자. 기본 자료형과 참조형의 차이는 Part 5에서 더 자세히 설명하겠다.

## 배열 만들기 실습

변수 `array`에 길이가 5인 `int[]` 배열을 만들고, 값으로 1, 2, 3, 4, 5를 넣어보세요.

```java
public class ArrayExam{
	public int[] makeArray() {
		// array가 1부터 5까지 값을 가지는, 길이가 5인 int 배열을 만들어보세요.
		**int[] array = new int[]{1,2,3,4,5};

		// int[] array = {1,2,3,4,5};**
		// 아래는 결과 평가를 위한 코드입니다. 수정하지 마세요.
		return array;
	}

	// 아래는 실행을 위한 코드입니다. 수정하지 마세요.
	public static void main(String[] args) {
		ArrayExam exam = new ArrayExam();
		int [] array = exam.makeArray();
		if(array.length==5 &&
				array[0] == 1 &&
				array[1] == 2 &&
				array[2] == 3 &&
				array[3] == 4 &&
				array[4] == 5) {
				System.out.println("Correct.");
		}
		else {
			System.out.println("Wrong.");
		}
	}
}

// Correct
```

배열은 선언과 함께 생성할 때 초기화할 수 있다. 정답 코드는 배열을 생성하면서 초기화한 코드이다.

```java
int[] array = {1,2,3,4,5};
```

이 코드는,

```java
int[] array = new int[]{1,2,3,4,5};
```

이 코드와 같은 의미이다.

또한, 다음 코드와 같다.

```java
// int를 담을 수 있는 다섯 칸짜리 배열을 만들고, 그 배열을 array 변수가 가리킨다.
int[] array = new int[5];

// array 변수가 가리키는 배열의 0번 인덱스에 1이라는 값을 담아준다.
// 배열의 인덱스는 0번부터 시작한다.
array[0] = 1;
array[1] = 2;
array[2] = 3;
array[3] = 4;
array[4] = 5;

// array가 가리키는 배열의 인덱스는 4번까지이므로
// array[5]라고 사용하면 오류를 발생시킬테니 주의하자.
```

# LESSON 20 배열 사용하기

1차원 배열을 선언하고, 사용하는 방법을 배웠다. 배열에 접근할 때는 인덱스를 통해서 접근했다. 배운 부분을 복습해보자.

`int`형 배열을 하나 정의한다. `iarray`라는 이름으로 정숫값 100개를 담을 수 있는 배열을 하나 선언했다. 이 배열에 값을 담을 때는 어떻게 했을까? 다음 코드처럼 배열의 0번 인덱스에 1이라는 값을 담고, 1번 인덱스에 2라는 값을 담았다.

```java
public class ArrayWithFor {
	public static void main(String[] args) {
		**int[] iarray = new int[100];
		iarray[0] = 1;
		iarray[1] = 2;**
	}
}
```

그런데 100개짜리 배열 안에 1~100까지 값을 차례대로 담으려면 어떻게 해야 할까? 반복적으로 값을 넣어줘야 한다. 이렇게 같은 작업을 반복하는 경우 하나씩 손으로 넣을 필요 없이 앞에서 배운 반복문을 사용하면 된다.

`for`문을 사용해 1~100까지 값을 배열 안에 넣는 코드를 작성한다. `for`라고 선언하고, 첫 번째 부분에 `int i`를 0으로 초기화한다. 여기서 초깃값으로 선언한 `i`는 인덱스로 사용할 것이다. 배열은 0번 인덱스부터 시작하니까 0으로 초기화한다.

```java
for(int i = 0; 조건식; 증감식)
```

두 번째 부분에는 `for` 문을 언제까지 실행할지 조건을 넣어준다. 앞에서 선언한 배열이 100개짜리이므로 99번 인덱스까지 실행한다. ‘`i < 100`’ 이라고 넣어주면 `for`문이 99번까지 실행할 것이다.

```java
for(int i = 0; i < 100; 증감식)
```

## `array.length`

여기서 100이라는 숫자는 배열 크기이다. 만약 배열 크기가 달라지면 이 숫자도 수정해야 한다. 매번 수정하지 않으려면 어떻게 하면 좋을까? 프로그램이 배열 크기를 알아내서 넣으면 될 것이다. 이럴 때 배열의 길이를 가리키는 `length`라는 속성을 사용한다. 100이라고 적는 대신에 `배열명.length`라고 적으면 배열 크기를 출력한다. 여기서는 `iarray`라는 배열이므로 `iarray.length`라고 적는다. `배열명.length`는 자주 사용하므로 꼭 기억해두자.

```java
for(int i = 0; **i < iarray.length**; 증감식)
```

세 번째 부분에는 0번부터 차례대로 1씩 증가하도록 넣어준다.

```java
for(int i = 0; i < iarray.length; **i++**)
```

이렇게 `for`문을 작성했다. `for` 블록 안에는 `iarray[]` 괄호 안에 인덱스를 넣어 값을 넣는다. 앞서 1차원 배열에서 사용한 코드처럼 0번, 1번, 2번 … 으로 들어가야 하는데 그 부분을 `i`라는 인덱스로 넣는다. `for`문이 동작하면 `i`가 바뀌므로 인덱스 역시 자동으로 바뀔 것이다. 그리고 각 인덱스에 해당하는 배열에 값을 넣을 때 1부터 넣을 예정이므로 `i`에 1씩 더해서 넣겠다. 그러면 인덱스가 0번일 때 1이 된다. 이제 1~100까지 해당 배열에 값을 채워 넣을 수 있다.

```java
public class ArrayWithFor {
	public static void main(String[] args) {
		int[] iarray = new int[100];

		**for(int i = 0; i < iarray.length; i++) {
			iarray[i] = i + 1;
		}**
	}
}
```

자, 이렇게 100개짜리 배열 안에 1~100까지 값을 차례대로 넣었다. 이번에는 배열에 들어있는 값을 모두 꺼내서 더하는 코드를 작성하자.

0번 인덱스부터 99번 인덱스까지 접근해야 하므로 아까 만들었던 `for` 문과 똑같이 만들면 된다.

```java
for(int i = 0; i < iarray.length; i++)
```

다음으로 `for` 블록 안 내용을 작성한다. `iarray.length`까지 증가하면서 전에는 값을 넣었다면 이번에는 값을 꺼낸다. 그리고 꺼낸 값은 계속 더해준다. 이 경우 계속 더하면서 그 값을 가져야 할 변수가 필요하다.

이때 변수를 어디에 선언해야 할까? 변수는 선언하는 지점이 어디냐에 따라서 그 변수를 사용할 수 있는 범위가 달라진다. 이를 변수의 **************\*\***************스코프(scope)**************\*\***************라고 한다. 기본적으로 변수를 선언한 지점을 감싼 괄호 안이 변수의 스코프이다. 변수는 선언할 때 생성했다가 해당 블록이 끝날 때 소멸한다.

다음 코드를 보자. 앞에서 작성한 1~100까지 값을 넣은 `for` 문이 있고, 지금 작성한 값을 꺼내려는 `for`문이 있다. 두 `for` 문에서 똑같이 변수 `i`를 사용한다. 같은 이름으로 선언해도 아무런 문제가 일어나지 않은 이유가 바로 변수의 스코프 때문이다. `i`라는 변수는 `for` 문이 시작할 때 생성했다가 `for`문이 끝날 때 없어진다. 그러므로 또다시 `i`를 선언해도 문제없던 것이다.

```java
public class ArrayWithFor {
	public static void main(String[] args) {
		int[] iarray = new int[100];

		for(int i = 0; i < iarray.length; i++) {
			iarray[i] = i + 1;
		}

		**for(int i = 0; i < iarray.length; i++) {

		}**
	}
}
```

그렇다면 계속 값을 더해줘야 하는 변수를 선언할 때는 이 변수를 어디에 선언해야 할 지 생각해보자. `for` 블록 안에서 선언한 변수는 `for`블록 안에서만 사용할 수 있다. 블록 안에 포함되지는 않지만, `for` 구문에 포함된 `int i`도 `for` 블록 안에서만 사용된다.

변수의 스코프는 **그 변수가 선언된 블록**이라고 생각하면 된다. 그러므로 값을 더한 결괏값을 저장할 변수를 `for` 블록 안에 선언하면 `for` 블록 바깥에서는 사용하지못한다. 또한, `for` 블록을 실행하고 다시 반복하는 시점에 변수를 매번 새롭게 선언하므로 값을 지속적으로 저장할 수가 없다. 따라서 `for` 블록 안에 값을 저장할 변수를 선언하면 안 된다. **값을 더할 변수 `sum`은 `for` 블록 밖에 선언**하고, `for` 블록 안에서는 배열 안에 들어있는 값을 차례대로 꺼내 이 변수에 계속 더해준다. 출력은 `for` 문이 모두 끝나고 한 번만 한다.

```java
public class ArrayWithFor {
	public static void main(String[] args) {
		int[] iarray = new int[100];

		for(int i = 0; i < iarray.length; i++) {
			iarray[i] = i + 1;
		}

		**int sum = 0;
		for(int i = 0; i < iarray.length; i++) {
			sum = iarray[i];
		}

		System.out.println(sum);**
	}
}

// 100
```

`for` 블록이 끝나면 1~100까지 더한 값, `sum`을 출력해야 하는데, 실행결과 1~100까지 합계가 나오지 않았다. 원하는 결과가 나오지 않았을 때는 코드를 다시 살펴본다. 무엇이 빠졌을까?

`for` 블록 안 코드는 인덱스에 있는 값을 `sum`에 순서대로 반복해 넣어주는 코드이다. 마지막에 100이라는 값이 들어있었기 때문에 100을 출력한 것이다. 값들을 더하려면 쭉 누적돼야 한다. `sum`에 0번 인덱스의 값인 1을 넣고, 1에 1번 인덱스 값 2를 더하고, 더한 값을 `sum`에 넣는 과정을 반복하며 쭉 누적시킨다.

```java
public class ArrayWithFor {
	public static void main(String[] args) {
		int[] iarray = new int[100];

		for(int i = 0; i < iarray.length; i++) {
			iarray[i] = i + 1;
		}

		int sum = 0;
		for(int i = 0; i < iarray.length; i++) {
			sum = sum + iarray[i];
		}

		System.out.println(sum);
	}
}

// 5050
```

코드를 수정하고 다시 실행시키니 이번에는 제대로 1~100까지 더한 값인 5050을 출력한다. 이러한 방법으로 배열을 이용하면 더 다양한 코드를 작성할 수 있다.

지금까지 실습한 코드를 한 줄씩 자세히 살펴보고 넘어가겠다.

## 배열에 1~100까지 값 넣기

```java
// 배열에 값을 반복해 넣어야 하므로 for 반복문을 이용한다.
for(int i = 0; i < iarray.length; i++) {
// 배열의 인덱스는 0부터 시작한다. 배열 크기는 **************************배열명.length**************************를 사용한다.
			iarray[i] = i + 1;
			// 배열의 인덱스는 0부터인데 넣고 싶은 값은 1부터이므로
			// 인덱스에 1을 더해준 값을 넣어준다.
}
```

## 배열에 저장된 값 모두 더하기

```java
int sum = 0;
// 값을 누적시킬 변수는 반복문 밖에 선언한다.
for(int i = 0; i < iarray.length; i++) {
// 배열 크기만큼 반복한다.
	sum = sum + iarray[i];
	// 반복문 밖에서 선언한 변수에 값을 누적시킨다.
}

System.out.println(sum);
// 배열에 들어있는 모든 값을 누적시킨 변수를 출력한다.
```

## 배열 사용하기 실습 1

`array`는 길이가 100인 배열이다. `for`문을 이용해 `array`에 순서대로 1~100까지 값을 넣어보세요.

```java
public class ArrayWithFor {
	public int[] fill100() {
		int[] array = new int[100];
		// array가 1부터 100까지 순서대로 값을 가지도록 만들어보세요.
		**for(int i = 0; i < array.length; i++) {
			array[i] = i + 1;
		}**
		// 아래는 결과 평가를 위한 코드이다. 수정하지 마세요.
		return array;
	}

	// 아래는 실행을 위한 코드입니다. 수정하지 마세요.
	public static void main(String[] args) {
		ArrayWithFor exam = new ArrayWithFor();
		int[] arr2 = exam.fill100();
		int errCount = 0;
		for (int i = 0; i < 100; i++) {
			if(arr2[i] != i + 1) {
				System.out.println("array[" + i + "]'s value is wrong");
				errCount++;
			}
		}
		if(errCount == 0)
			System.out.println("Correct.");
	}
}
```

배열에 1~100까지 값을 반복해 넣도록 코드를 작성하는 문제이다. 이럴 때는 반복문을 사용한다. 범위가 정확하게 정해진 일을 수행할 때는 `for` 반복문을 이용하는 것이 효과적이다.

반복문의 초깃값으로 0을 지정한다. 배열의 인덱스가 0번부터 시작하기 때문이다. 조건문에는 반복이 끝나는 조건을 준다. 배열의 인덱스는 0부터 시작하기 때문에 배열이 가질 수 있는 인덱스의 값은 ‘배열 크기 - 1’이라고 생각하면 된다. 따라서 조건을 ‘i<100보다 작을 때까지’로 작성한다.

배열의 0번 인덱스에는 1을, 1번 인덱스에는 2를 (…) 99번 인덱스에는 100을 넣어야 한다. 인덱스도 값도 1씩 증가해야 하니까 배열의 인덱스를 넣는 부분에 `for`문에서 선언한 인덱스 변수를 사용하는 것이 효과적일 것이다. 그리고 값은 항상 인덱스보다 1이 큰 값으로 채워주면 되니까 `array[index] = index+1;`로 작성한다. 예제에서는 `index`를 변수`i`로 이용하므로 `array[i] = i + 1;`로 작성한다.

참고로 `for`문의 조건에 `index<100`으로 작성할 수도 있지만, 100이라는 값을 직접 이용하는 것보다는 배열 크기를 리턴해주는 `array.length`를 사용하는 것이 좋다. `**array.length`를 사용하면 길이가 다른 배열을 이용할 때 코드를 수정하지 않아도 되기 때문이다.\*\*

## 배열 사용하기 실습 2

`array`는 길이를 알 수 없는 `int`형 배열이다. `array`에 들어있는 값의 합을 `sum`에 저장하라.

```java
public class ArrayWithFor {
	public int sum(**int[] array**) {
		int sum = 0;

		// array는 길이를 알 수 없는 int형 배열이다.
		// array에는 정수가 들어있다고 가정하고
		// 이 아래에서 sum에 array의 모든 값을 더하세요.
		**for(int i=0; i<array.length; i++) {
			sum += array[i];
		}**

		// 아래는 결과 평가를 위한 코드이다. 수정하지 마세요.
		return sum;
	}

	// 아래는 실행을 위한 코드이다. 수정하지 마세요.
	public static void main(String[] args) {
		int[]testArr = new int[4];
		String str = "";
		int rightResult = 0;
		for(int i=0; i<4; i++) {
			testArr[i] = (int)(Math.random()*100);
			rightResult += testArr[i];
			str+=(testArr[i]+",");
		}
		str=str.substring(0, str.length()-1);

		ArrayWithFor exam = new ArrayWithFor();
		int Answer = exam.sum(testArr);

		if(Answer==rightResult) {
			System.out.println("Correct.");
		}
		else {
			System.out.println(str+" the sum of these is wrong.");
		}
	}

}
```

이 문제는 `array`의 길이를 읽어오는 `array.length`를 사용할 수 있는지 묻는 문제이다. 메서드 안에 들어오는 배열 크기를 알 수 없으므로 배열 크기를 구하는 `array.length`를 사용해 크가보다 작을 때까지 반복 수행하게 한다.

배열의 모든 값의 합을 구하는 문제이므로 더한 값을 담을 수 있는 변수가 필요하다. 문제에서 변수 `sum`을 선언했으므로 `sum`을 사용해 값을 누적한다. `+=`연산자를 이용하면 코드를 짧게 사용할 수 있다. 익숙하지 않다면 `sum = sum + 1`과 같이 사용해도 좋다.

# LESSON 21 2차원 배열

2차원 배열이란 배열의 배열이라는 뜻이다. 배열 요소를 한 번 더 배열한 2차원 배열은 어떤 형태일까?

2차원 배열을 선언할 때는 배열 표시를 두 번 적는다.

예를 들어 정수형 2차원 배열을 만들어보자. `int`형으로 배열 표시 두 개를 만들어 2차원 배열을 하나 선언한다. 다음에 오는 배열명은 원하는 이름으로 설정한다. 책에서는 `array4`라고 했다. 2차원 배열을 설정할 때도 똑같이 `new`라고 적고, 배열 크기를 지정한다. ****************************************************\*\*\*\*****************************************************배열이 두 개이니 배열 크기를 각각 지정한다.****************************************************\*\*\*\*****************************************************

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		int[][] array4 = new int[3][4];
	}
}
```

이렇게 [3][4]라고 지정한 2차원 배열은 다음과 같은 형태이다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/28569e6e-af68-4e6d-8f66-038e78224bab/Untitled.png)

①의 `array4`는 2차원 배열을 가리키는 배열명이다.

②는 1차원 배열을 가리키는 참조 변수이다.

③이 실제 정숫값을 담을 수 있는 그릇들이다.

2차원 배열에 값을 담을 때는 1차원 배열과 똑같이 인덱스를 이용한다. 배열명 다음에 0번 인덱스를 가리키며 10을 넣으려고 하면 오류가 발생한다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		int[][] array4 = new int[3][4];
		**array4[0] = 10; // 이 구문은 사용할 수 없습니다.**
	}                 // Type mismatch: cannot convert from int to int[]

}
```

왜냐하면 `array4`가 가리키는 배열의 0번 인덱스는 위의 그림에도 나와있는 ②인 참조 변수 ‘0’을 의미하기 때문이다. **********************************************************************\*\***********************************************************************이 부분은 실제 인덱스 값을 담을 수 있는 부분이 아니라 `int`형 배열을 가리키는 참조 변수이므로 정숫값을 담을 수 없다.** 정숫값은 ************************************************************************\*\***************************************************************************③************************************************************************\*\*\*\*************************************************************************에 담는다. 따라서 이 구문은 사용할 수 없다.

그럼 값을 담으려면 어떻게 해야 할까? **세 번째 부분, 즉 다음 인덱스까지 지정해줘야 한다**. 참조 변수 ‘0’이 가리키는 1차원 배열 중 1번 인덱스에 10을 넣겠다고 지정하겠다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		// 정수형 이차원 배열 array4, 인덱스는 3까지
		int[][] array4 = new int[3][4];
		**array4[0][1] = 10;**
	}

}
```

이 코드가 아래의 그림에서 어디를 가리키는지 생각해본다면.. 참조 변수 ‘0’의 1차원 배열에서 1번 인덱스이므로 다음 부분에 10을 넣어준다는 의미이다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4a2e2071-71d7-4433-854c-c1c4aa6fc5ca/Untitled.png)

이렇게 2차원 배열을 생성한다.

2차원 배열을 생성하는 다른 방법도 알아보자. 앞서 만든 2차원 배열은 4개로 크기가 모두 같다. 그런데 크기가 다른 배열도 생성할 수 있다. 생성하는 방법은 간단하다. 우선 앞에서 했던 것처럼 2차원 배열을 생성하고, 뒤에 있는 배열의 사이즈를 비워둔다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		**int[][] array5 = new int[3][];**
	}

}
```

이렇게 선언하면 메모리에는 아래의 그림까지만 만들어진다. 참조 변수만 만들어지고 실제로 값을 담을 수 있는 1차원 배열은 만들어지지 않은 상태이다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b5d3dae5-43ff-4173-be85-9d58c579620f/Untitled.png)

이 상태에서는 당연히 값을 저장할 수가 없다. 앞에서 배운 대로 참조 변수 ‘0’의 1차원 배열에서 0번 인덱스에 10을 넣겠다고 코드를 작성해도 실행하면 오류가 발생한다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		int[][] array5 = new int[3][];
		**array5[0][0] = 10;**
	}

}

// 실행결과
// Exception in thread "main" java.lang.NullPointerException:
// Cannot store to int array because "array5[0]" is null
// at ArrayExam2.main(ArrayExam2.java:4)
```

`array5` 배열의 참조 변수 ’0’이 가리키는 1차원 배열이 없기 때문이다. 따라서 **반드시 참조 변수가 가리킬 배열을 만들어줘야 한다.** 한 개짜리 1차원 배열을 만들어보자.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		int[][] array5 = new int[3][];
		**array5[0] = new int[1];**
		array5[0][0] = 10;
	}
}
```

이 방법을 사용하면 참조 변수 ’0’에는 한 개짜리 `int`형 배열을, 참조 변수 ‘1’에는 두 개짜리 `int`형 배열을, 참조 변수 ‘2’에는 세 개짜리 `int`형 배열을 만들 수 있다. 즉, 각각 길이가 다른 배열을 만들 수 있다는 의미이다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		int[][] array5 = new int[3][];
		**array5[0] = new int[1];
		array5[0] = new int[2];
		array5[0] = new int[3];**
		array5[0][0] = 10;
	}
}
```

이렇게 코드를 작성해 아래의 그림과 같은 형태의 2차원 배열을 만들어봤다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ba970e97-efc3-4f58-baa4-306791ddfd8e/Untitled.png)

마지막으로 한 가지 더 알아보자.

1차원 배열은 중괄호를 이용해 선언과 동시에 초기화를 했었다.

2차원 배열도 마찬가지로 선언과 동시에 초기화할 수 있다.

중괄호를 사용해 배열을 만들면 선언과 동시에 값을 저장할 수 있다.

배열 `array6`의 참조 변수 ‘0’의 0번 인덱스를 출력하라고 코드를 작성한다. 제대로 출력한다면 1을 출력해야 한다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		//int[][] array6 = new int[][] {{1}, {1,2}, {1,2,3}}; 아래와 같은 코드입니다.
		// 1차원 배열에서 new int[][] 부분을 생략해도 컴파일러가 알아서 해석해준다.
		**int[][] array6 = {{1},{1,2},{1,2,3}};**
		System.out.println(array6[0][0]);
	}
}

// 1
```

예상대로 1을 출력했다. 이렇게 2차원 배열에 값을 넣거나 꺼내서 사용할 수 있다.

지금까지 2차원 배열을 알아봤다. 2차원 배열뿐 아니라 다차원 배열도 마찬가지로 배열 크기만 하나씩 증가시켜서 사용하면 된다.

## 2차원 배열 실습

### 문제

다음 코드는 2차원 배열을 출력하는 코드이다. 코드를 살펴보고 실행해서 결과를 확인해보세요. 완성형 실습이므로 똑같이 입력하고 실행결과를 확인하면 됩니다.

```java
public class ArrayExam2 {
	public static void main(String[] args) {
		int [][] array = {{1},{1,2},{1,2,3},{1,2,3,4}};

		// 2차원 배열 array를 출력합니다.
		for(int i = 0; i < array.length; i++) {
			System.out.print((i+1) + "th line is to be printed.>");
			for(int j = 0; j < array[i].length; j++) {
				// System.out.print는 줄을 바꾸지 않고 출력하는 코드입니다.
				System.out.print(array[i][j]+" ");
			}
			System.out.println(); // 줄바꿈해주는 코드입니다.
		}
	}
}

// 실행결과
// 1th line is to be printed.>1
// 2th line is to be printed.>1 2
// 3th line is to be printed.>1 2 3
// 4th line is to be printed.>1 2 3 4
```

### 해설

2차원 배열 실습이다. 2차원 배열을 초기할 때는 다음과 같이 괄호 안에 또 괄호를 넣어 사용할 수 있다.

```java
{{1,2,3,4},{5,6,7,8},{9,10,11,12}}
```

괄호 안에 괄호 세 개가 있으므로 이 배열 크기만큼 배열을 생성한다면 다음과 같다.

```java
new int[3]
```

차원이 더 높은 배열도 같은 방법을 이용할 수 있는데, 차원에 따라서 중첩되는 괄호가 늘어난다. 값은 항상 가장 안쪽의 괄호에만 담을 수 있다.

다차원 배열이 헷갈릴 때는 배열을 그림으로 그려보면 훨씬 쉡게 이해할 수 있다. 이번 장에서 배열을 설명할 때 그렸던 그림들을 참조해 사용할 배열을 그려보자. 어디에 값이 들어가는지 눈으로 확인하면 더 명확히 이해할 수 있다. ******************************************************************************************************\*\*******************************************************************************************************차원이 아무리 깊게 들어가도 가장 마지막에만 값이 들어간다는 사실을 기억하자.******************************************************************************************************\*\*******************************************************************************************************

# LESSON 22 for each 문

- NOTE
  자바는 1.5 버전부터 for each 문을 추가했다. 자바에서는 명령어로 for each가 아니라 그냥 `for`를 사용한다. 하지만 대부분 다른 언어에서 `for each`란 용어를 사용하기 때문에 자바에서도 `for each`라는 용어를 사용한다.
  기존에 사용하는 `for`문을 이용해 동일한 일을 수행할 수 있다. 반복되는 자료구조(배열 등…)에서 값을 꺼낼 때, `for`문은 자료구조의 전체 크기를 구하고, 그 크기만큼 인덱스를 이용해 값을 꺼내지만 `for each`문은 그런 일련의 동작을 자동으로 수행해준다. 뒤에서 배울 다양한 자료구조 중에는 순서가 없는 자료구조도 있는데 그런 자료구조는 `index`가 없으므로 다른 방법으로 데이터에 접근해야 한다. 이런 경우에도 `for each`문을 이용하면 더 간편하게 데이터에 접근할 수 있다.

```java
public class ForEachExam {
	public static void main(String[] args) {
		int[] iarr = {10,20,30,40,50};
	}
}
```

`iarr` 배열에 들어있는 값을 모두 출력하려면 어떻게 해야 할까?

```java
public class ForEachExam {
	public static void main(String[] args) {
		int[] iarr = {10,20,30,40,50};

		**for(int i = 0; i < iarr.length; i++) {
			int value = iarr[i];
			System.out.println(value);
		}**
	}
}
```

이 코드를 for each 문으로 바꿔보자

## for each문 형식

`for(형과 값을 받아줄 변수명:출력하고 싶은 자료구조)`

: 뒤에 반복되는 자료구조, 출력하고 싶은 자료구조를 넣는다고 했으니 여기서는 출력하고자 하는 `iarr`를 넣어준다. `for each`는 `iarr` 배열을 자동으로 돌면서 값을 하나씩 꺼내준다.

`for(:iarr)`

그러면 이 값을 받아낼 변수가 필요하다. 콜론 앞에는 값을 받을 수 있는 변수를 선언하면 된다. `iarr`는 `int`형 배열이므로 `int`형 변수를 선언한다. 변수명은 무엇을 써도 상관없다. 일단 `value`라고 해보자!

```java
for(int value:iarr)
```

처음 작성한 `for`문에서는 `index`를 이용해 값을 꺼내서 `int`형 변수 `value`에 담았다. `for each`는 그 일까지 모두 끝내주므로 이 상태에서 `value` 값을 이용하면 된다.

```java
public class ForEachExam {
	public static void main(String[] args) {
		int[] iarr = {10,20,30,40,50};

		for(int i = 0; i < iarr.length; i++) {
			int value = iarr[i];
			System.out.println(value);
		}

		for(int value:iarr) {
			System.out.println(value);
		}
	}
}

// 10
// 20
// 30
// 40
// 50
// 10
// 20
// 30
// 40
// 50
```

## for each문 실습

### 문제

`for each` 문을 이용해 배열 `array`의 값을 한 줄씩 출력하세요.

```java
public class ForEachExam{
	public static void main(String[] args) {
		int [] array = {1,5,3,6,7};
		// for each 문을 이용해 배열 array의 값을 한 줄씩 출력하세요.
		**for(int value:array) {
			System.out.println(value);
		}**
	}
}

// 1
// 5
// 3
// 6
// 7
```

### 해설

for 문 vs for each 문

```java
// for문
for(int index=0; index<array.length; index++) {
			int i = array[index];
			System.out.println(i);
}

// for each 문
for(int i:array) {
	System.out.println(i);
}
```

for each 문은 for 문 내에서 인덱스를 초기화하고, 배열 크기와 인덱스 크기를 비교하고, 인덱스를 증가시키고, 배열에 저장된 인덱스에 해당하는 값을 꺼내서 변수에 담아주는 일까지 자동으로 해준다. for each 문에는 배열뿐만 아니라 (더 배울..) 반복되는 다양한 자료구조를 이용할 수 있다. 아직은 배열까지만 배웠으므로 배열만 예를 들어 설명해보겠다.

배열 인덱스에 해당하는 특정 데이터를 써야 하는 경우가 아니라면 `for each`문을 사용하는 것이 훨씬 편할 것!

```java
for(자료형 변수명:배열명) {
		반복해서 수행할 문장들;
}
```

자료형은 배열에 들어가는 형을 써준다.

int[]라면 int를, char[]라면 char를, Book[]이라면 Book을 형으로 써준다.

for each 문은 배열을 돌면서 배열에 들어있는 데이터를 하나씩 꺼내서 준비한 변수에 담아주기 때문에 **변수의 타입이 배열에 들어있는 자료형과 일치해야 한다.**
