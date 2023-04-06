# LESSON 25 필드 선언

앞에서 클래스를 선언하는 방법을 간단히 살펴봤다. 이번에는 그 클래스의 구성요소인 **필드**에 대해서 알아보자.

자동차라는 **객체**가 있다고 생각해보자. 앞에서 `Car`라는 객체를 만들었다. 이 자동차에는 이름이나 번호가 있을 텐데, 이것을 **속성**이라고 한다. 자바에서는 이러한 속성을 ********\*\*\*\*********필드(field)********\*\*\*\*********라고 한다.

예를 하나 더 들어보자. 학교에서 공부하는 학생은 어떤 피드를 가질까? 학생은 이름이나 학번을 속성, 즉 필드로 가질 수 있다. 한 반을 구성하는 학생이 20명이라면 학생 객체가 20개 있다는 의미이다. 각 학생은 이름이 구별된다. **이름이 구별된다는 것은 객체별로 필드 값이 유지된다**는 의미이다.

자, 그러면 앞에서 배웠던 `Car` 객체가 이름과 번호를 가지도록 피드를 선언하겠다.

```java
package javaStudy;

public class Car {
		// 자료형 필드명
}
```

필드는 코드에서 변수로 표현된다. 따라서 변수를 선언하는 것과 비슷하게 ‘`자료형 필드명`'으로 선언할 수 있다.

`Car` 객체에 만들려는 필드는 이름과 번호이다. 그러면 어떤 자료형을 사용하면 좋을까?

```java
package javaStudy;

public class Car{
	// (자료형)타입 필드명
	String name;
	int number;
}
```

이름은 문자열을 나타낼 수 있는 `String` 형이 적합할 것이다. 마찬가지로 번호는 숫자를 나타낼 수 있는 `int`형이 좋겠다. `String`형으로 `name`이라는 필드를 선언하고, `int`형으로 `number`라는 필드를 선언했다.

이제 이 자동차를 `CarExam` 클래스에서 이용하겠다. `[CarExam.java](http://CarExam.java)` 파일에 `c1`과 `c2`, 이렇게 `Car` 객체 두 개를 만들었다. 이를 실행시키면 메모리에 `Car` 객체가 두 개 만들어지고, 각 객체는 `name`과 `number`라는 필드를 지니게 된다.

필드에 값을 넣어보자. 코드에서 변수 `c1`은 참조 변수이다. 참조 변수 다음에 마침표(`.`)를 입력하면 참조 변수가 참조하는 객체가 가진 것들을 사용할 수 있다. 따라서 `c1.`를 입력하면 `Car` 객체가 가진 것들을 사용할 수 있다.

```java
package javaStudy;

public class CarExam{

	public static void main(String[] args) {
		Car c1 = new Car();
		Car c2 = new Car();

		c1.
	}
}
```

`c1.` 을 입력하니 `Car` 객체가 가진 것들을 보여준다. 그중에 `name`과 `number`도 보인다. 아까 선언한 필드이다.

```java
package javaStudy;

public class CarExam{

	public static void main(String[] args) {
		Car c1 = new Car();
		Car c2 = new Car();

		**c1.name = "fire truck";
		c1.number = 1234;

		c2.name = "ambulance";
		c2.number = 1111;

		System.out.println(c1.name);
		System.out.println(c1.number);**
	}
}

// fire truck
// 1234
```

첫 번째 `Car` 객체인 `c1`에는 fire truck이라는 이름과 1234라는 번호를 넣었다. 마찬가지로 두 번째 `Car` 객체인 `c2`에는 ambulance라는 이름과 1111이라는 번호를 넣었다.

넣은 다음에는 들어있는 값을 출력해본다.

`"참조 변수 c1이 가진 name이라는 값을 출력해주세요."`

`"참조 변수 c1이 가진 number라는 값을 출력해주세요."`

실행 결과를 보면, 넣은 값 그대로 `c1`의 `name`에는 fire truck이 들어있고, `number`는 1234가 들어있다.

마찬가지로 `c2`가 가진 값도 출력하면 `c2`의 `name`과 `number`를 확인할 수 있다.

```java
package javaStudy;

public class CarExam{

	public static void main(String[] args) {
		Car c1 = new Car();
		Car c2 = new Car();

		c1.name = "fire truck";
		c1.number = 1234;

		c2.name = "ambulance";
		c2.number = 1111;

		System.out.println(c1.name);
		System.out.println(c1.number);
		**System.out.println(c2.name);
		System.out.println(c2.number);**
	}
}

// fire truck
// 1234
// ambulance
// 1111
```

마찬가지로 `c2`가 가진 값도 출력하면, `c2`의 `name`과 `number`를 확인할 수 있다.

실행결과, `c1`과 `c2`에는 각각 다른 값이 들어있다.

지금까지 `Car` 클래스에 객체를 각각 생성할 수 있고, 각 객체마다 속성을 넣을 수 있다는 것을 배웠다.

필드를 선언하고 이용하는 방법을 요약하겠다.

## 필드 선언하고 이용하는 방법 요약

### 1 이름과 번호를 필드로 가진 `Car` 클래스 선언

```java
public class Car{
		String name;
		int number;
}
```

### 2 Car 클래스를 인스턴스화하기

```java
Car c1 = new Car();
Car c2 = new Car();
// Car라는 인스턴스가 메모리에 두 개 만들어진다.
// 객체별로 name과 number라는 필드를 가진다.
```

### 3 속성 이용하기

```java
// c1.name은 c1이 참조하는 객체의 name을 의미한다.

c1.name = "fire truck"; // c1이 참조하는 객체의 name을 fire truck으로 설정
c1.number = 1234; // c1이 참조하는 객체의 number를 1234로 설정

c2.name = "ambulance"; // c2가 가리키는 객체의 name을 ambulance로 설정
c2.number = 1111; // c2가 가리키는 객체의 number를 1111로 설정

System.out.println(c1.name); // 콘솔에 c1이 참조하는 객체의 name을 출력
System.out.println(c1.number); // 콘솔에 c1이 참조하는 객체의 number를 출력
```

## 필드 선언 실습

### 문제

`Song` 이라는 클래스에 필드를 선언해보자. `Song` 클래스는 다음과 같은 필드를 가진다.

1. 노래의 곡명을 나타내는 `songTitle` (String형으로 선언하기)
2. 가수를 나타내는 `singer` (String형으로 선언하기)
3. 노래가 속한 앨범 이름을 나타내는 `albumName` (String형으로 선언하기)
4. 노래가 속한 앨범에서 트랙 번호를 나타내는 `trackNumber` (int형으로 선언하기)

```java
package javaStudy;

public class Song {

	**String songTitle;

	String singer;

	String albumName;

	int trackNumber;**
}
```

```java
package javaStudy;

public class SongTest {

	public static void main(String[] args) {
		Song song = new Song();
		song.songTitle = "Perfect Illusion";
		song.singer = "Lady Gaga";
		song.albumName = "Joanne";
		song.trackNumber = 7;

		System.out.println("[songTitle=" + song.songTitle + ", "
				+ "singer=" + song.singer + ", "
				+ "albumName= " + song.albumName + ", "
				+ "trackNumber= " + song.trackNumber + "]");
	}
}

// [songTitle=Perfect Illusion, singer=Lady Gaga, albumName= Joanne, trackNumber= 7]
```

### 해설

**\*\***필드**\*\***는 일종의 변수이다. 변수를 선언하는 것과 같은 방법으로 필드를 선언한다.
