# 1장 자바 시작하기

# LESSON 01 자바란?

## 자바 언어의 특징

- 쉽다 (?)
    - C, C++의 포인터와 다중상속 부분이 없음
- 플랫폼 독립적
    - C, C++ 개발 프로그램은 특정 OS에서만 동작
        - ex. 리눅스에서 개발 - 리눅스에서만 실행
    - 자바로 만든 프로그램은 JVM(Java Virtual Machine, 자바 가상 머신)만 있으면 모든 운영체제에서 실행할 수 있음
- 객체 지향 언어
- 메모리 관리를 자동으로 해줌.

### 플랫폼 독립적

가령 워드 파일을 연다면 스마트폰용, PC용 프로그램이 있는 것처럼 JVM도 리눅스용, 위도우용, 맥용이 있어서 이를 이용하면 모든 플랫폼에서 동작시킬 수 있음.

JVM 위에서 애플리케이션이 실행되기 때문에 자바로 프로그래밍하면 윈도우, 리눅스, 맥 등 다양한 OS에서 돌아간다. 

![image](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c3cad42d-a325-4900-93a8-3d3f3ddd72ba/Untitled.png)

### 객체지향언어

******************객체지향******************

객체를 중심으로 프로그램이나 시스템을 구성하는 것

******객체******

데이터나 데이터와 관련한 동작을 모두 포함하는 개념

### 메모리 관리

자바 언어는 어려운 메모리 관리를 자동으로 해준다.

C, C++은 프로그래머가 직접 메모리를 할당하거나 다 사용한 메모리를 다시 회수했는데, 자바에서는 가비지 컬렉터(garbage collector)가 메모리를 자동으로 관리한다. 

# LESSON 02 자바 개발환경 구축

# LESSON 03 자바 개발 순서

## 콘솔에서 HelloWorld 출력

1. 코드를 작성한다.
2. 작성한 코드를 컴파일한다.
3. 컴파일한 코드를 JVM으로 실행한다. 

### 1 콘솔

코드를 작성할 java 파일 작성

```java
public class HelloWorld{
    public static void main(String args[]) {
        System.out.println("Hello World");
    }
}
```

윈도우 콘솔에서 tmp 폴더로 이동, 파일 목록을 살펴보면 [HelloWorld.java](http://HelloWorld.java) 파일이 보임

```java
C:\tmp>dir
```

### 2 컴파일

두번째로 컴파일한다.

```java
C:\tmp>javac HelloWorld.java
C:\tmp>
```

이렇게 메시지가 나오지 않았다는 건 에러 없이 컴파일이 잘 됐다는 것.

여기서 dir을 입력하면 tmp 폴더에 아까는 없었던 HelloWorld.class가 만들어진다.

```java
C:\tmp>dir
... HelloWorld.class
... HelloWorld.java
```

### 3 코드 실행

세번째로 컴파일한 코드를 실행한다. 

```java
C:\tmp>java HelloWorld
Hello World
C:\tmp>
```

### 4 note

자바로 만든 프로그램의 최소 단위는 ****************************************클래스이다.**************************************** “Hello World”를 출력하는 매우 간단한 프로그램도 하나의 클래스는 존재해야 한다.

```java
public class 클래스명 {
.....
}
```

이 구조가 클래스를 선언하는 가장 간단한 방법이다. 클래스명은 식별자 규칙을 따른다.

❓**********************식별자(identifier)란?**********************

클래스, 메서드, 변수 등 다양한 대상에 이름이 붙은 경우, 또는 그 이름을 말한다.

보통 영문자로 시작하고 중간에 숫자가 있으면 된다.

소문자로 **클래스명**을 작성해도 되지만 보통 **대문자**로 이름을 작성한다. ********(카멜케이스)********

ex) helloworld보다는 HelloWorld 

클래스명 다음에는 **********************************************중괄호를 붙인다.********************************************** 

클래스 안에는 클래스와 메서드가 올 수 있다. 

```java
public class HelloWorld{
    public static void main(String args[]) {
        System.out.println("Hello World");
    }
}
```

여기에는 main이라는 메서드가 있다. 

******************************************************************************************************************자바 프로그램을 실행하기 위해서는 반드시 `public static void main(String[] args) { ... }`** 이라는 메서드가 있어야 한다. 여기서부터 프로그램이 실행된다.

그래서 main 메서드를 다른 말로 프로그램 시작점이라고도 한다. 

`System.out.println(문자열);` 은 화면에 문자열을 출력하는 명령이다. 

`System` 클래스가 가지는 `out`, 그 `out`이 가지는 `println`이라는 메서드를 이용해 화면에 출력한다. 

## 이클립스에서 HelloWorld 출력하기

### 1 eclipse.exe 실행

### 2 사용자 홈 디렉터리 아래에 workspace 폴더 지정

### 3 first 프로젝트 생성

❗ 프로젝트 생성 - 소스 작성 - 컴파일을 했을 때 이런 에러가 발생한다면

```java
Must declare a named package becuase this compilation unit is associated to the named module 'algorithm'
```

use default location을 체크 해제하고 Use an execution environment JRE > JavaSE-1.8을 선택하자.

### 4 소스 작성

src 폴더에서 [HelloWolrd.java](http://HelloWolrd.java) 파일 생성

### 5 컴파일

bin 폴더를 열어보면 HelloWorld.class 파일이 생성됐음

### 6 실행

이클립스에서 클래스(HelloWorld.class) 선택 → 오른쪽 버튼 클릭 → 자바 어플리케이션 실행

❗ bin이 package explorer에서 안 보일때는 Window > Show View> 

Navigator(Deprecated) 를 클릭하자.