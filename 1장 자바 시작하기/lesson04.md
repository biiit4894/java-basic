# LESSON 04 주석문

앞 장에서 작성한 코드는 main이라는 메서드가 프로그램의 시작점이다. 

```java
public class HelloWorld{
	프로그램의 시작점
	public static void main(String args[]) {
		System.out.println("Hello World")
	}
}
```

이따위로 주석을 넣으면 바로 **************************컴파일 에러**************************가 발생한다.

❗ **컴파일**?

사람이 알아보기 쉽게 작성한 코드를 컴퓨터가 알아들을 수 있는 언어로 번역하는 과정.

language code → compiler → machine code

❗ **컴파일 에러**?

애초에 작성한 코드에 오류가 있다면 컴파일러가 제대로 변환할 수 없기 때문에 컴파일 에러가 발생한다.

## 구현 주석

정상적인 주석처리는 다음과 같다

```java
public class HelloWorld{
	// 프로그램의 시작점
	public static void main(String args[]) {
		System.out.println("Hello World")
	}
}

// Hello World
```

이와 같이 주석으로 처리하면 컴파일 대상에서 제외되기 때문에 주석에 무엇을 쓰든 결과에는 영향을 미치지 않는다. 

이번에는 코드에 몇 줄을 더 추가하자.

```java
public class HelloWorld{
// 프로그램의 시작점
    public static void main(String args[]) {
        System.out.println("Hello World");
        System.out.println("test");
        System.out.println("1");
        System.out.println("2");
        System.out.println("3");
    }
}

// Hello World
// test
// 1
// 2
// 3
```

이 중에서 ‘test’가 있는 행을 실행시키고 싶지 않다면 ‘test’가 있는 코드를 주석으로 처리하면 된다.

```java
public class HelloWorld{
// 프로그램의 시작점
    public static void main(String args[]) {
        System.out.println("Hello World");
//      System.out.println("test");
        System.out.println("1");
        System.out.println("2");
        System.out.println("3");
    }
}

// Hello World
// 1
// 2
// 3
```

이렇게 주석을 사용하면 프로그램에 필요한 설명을 적어놓거나 일부 코드를 실행시키지 않을 수 있다.

❗ **구현 주석**이란?

구현할 때 사용하는 이러한 주석을 구현 주석이라고도 한다.

### 행 단위 주석, 블록 단위 주석

❗ ******************************행 단위 주석******************************

`// 주석 처리`

❗ ************************************블록 단위 주석************************************

`/* .... */`

```jsx
public class HelloWorld{
// 프로그램의 시작점
    public static void main(String args[]) {
        System.out.println("Hello World");
        System.out.println("test");
/*      System.out.println("1");
        System.out.println("2");
        System.out.println("3");  */
    }
}

// Hello World
// test
```

### 주석 처리 단축키

`Ctrl + Shift + /` : `/*  */` 주석 처리

`Ctrl + /` : `//` 주석 처리

## 문서화 주석

코드에서 사용한 클래스가 뭐 하는 건지, 클래스 내 메서드는 뭐 하는 건지 사용하는 사람이 쉽게 이해할 수 있도록 자바에서 문서화 코드를 만들 수 있다. 

❗ **문서화 주석**

**문서화 코드를 만드는 주석**을 문서화 주석이라고 한다.

코드의 명세 사항(specification)을 포함하며 자바 클래스, 인터페이스, 생성자, 메서드, 필드를 설명할 때 사용한다. 

문서화 주석은 사용하는 프로그램에 따라 자동으로 나오거나 나오지 않을 수 있다. 안에 들어가는 내용도 달라진다. 

### 문서화 주석 형식 (이클립스)

`/**    ...     */`

코드 중간에 `/**`를 넣고 `Enter`를 누르면 이렇게 된다.  

```jsx
public class HelloWorld{
// 프로그램의 시작점
	/**
	 * 
	 * @param args
	 */
    public static void main(String args[]) {
        System.out.println("Hello World");
        System.out.println("test");
        System.out.println("1");
        System.out.println("2");
        System.out.println("3");  
    }
}
```

문서화 주석 부분에 여기에 들어있는 파라미터가 뭔지, 이 클래스를 누가 만들었는지, 무슨 용도로 만들었는지 등에 대한 설명이 나온다. 

지금 HelloWorld 코드의 문서화 주석에는 어떤 파라미터(args)가 들어있는 지만 나왔다. 

## 정리

********************구현 주석********************

- 행 단위 주석: `// 주석`
- 블록 단위 주석: `/* 주석 */`

****************************문서화 주석****************************

- `/** 주석 */`
- 클래스, 인터페이스 멤버 당 하나씩 가질 수 있고, 선언 바로 전에 작성.

## 주석 실습

```jsx
public class HelloWorld{
	public static void main(String[] args) {
//		이 부분을 주석 처리해 프로그램이 정상적으로 실행되게 만들어 보세요.
		System.out.println("HelloWorld");
	}
}

// HelloWorld
```