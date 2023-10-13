# Chapter 4 조건문과 반복문

# 01 if문

- 제어문
  - 조건문
  - 반복문

# 02 조건식의 다양한 예

| 조건식                      | 조건식이 참일 조건                                |
| --------------------------- | ------------------------------------------------- | -------- | --- | -------- | ------------------------------------------ |
| ch==’ ‘                     |                                                   | ch==’\t’ |     | ch==’\n’ | 문자 ch가 공백이거나 탭 또는 개행문자일 때 |
| ‘A’ ≤ ch && ch ≤ ‘Z’        | 문자 ch가 대문자일 때                             |
| ‘a’ ≤ ch && ch ≤ ‘z’        | 문자 ch가 소문자일 때                             |
| ‘0’ ≤ ch && ch ≤ ‘9’        | 문자 ch가 숫자일 때                               |
| str.equals(”yes”)           | 문자열 str의 내용이 “yes”일 때(대소문자 구분)     |
| str.equalsIgnoreCase(”yes”) | 문자열 str의 내용이 “yes”일 때(대소문자 구분안함) |

- 자바에서 조건식의 결과는 반드시 true 또는 false이어야 한다
  - ex) `if(0) { ... }` ⇒ 결과가 true 또는 false가 아니므로 에러가 발생한다.

# 03 블럭{}

- 블럭 내 문장이 하나뿐이면 괄호 생략 가능(가능하면 써주기)
  ```java
  iif(score > 60)
  	System.out.println("합격입니다.");
  ```
- 한 줄 작성도 가능
  ```java
  if(score > 60) System.out.println("합격입니다.");
  ```

# 05 if-else if문

- 처리해야 할 경우의 수가 셋 이상인 경우

```java
if (조건식1) {
			// 조건식1의 연산결과가 참일 때 수행될 문장들을 적는다.
		} else if (조건식2) {
			// 조건식2의 연산결과가 참일 때 수행될 문장들을 적는다.
		} else if (조건식3) { // 여러 개의 else if 사용 가능
			// 조건식3의 연산결과가 참일 때 수행될 문장들을 적는다.
		} else { // 마지막은 보통 else 블럭으로 끝나며, else블럭은 생략가능하다.
			// 위의 어느 조건식도 만족하지 않을 때 수행될 문장들을 적는다.
		}
```

- 첫번째 조건식부터 순서대로 평가
  - 결과가 참인 조건식을 만나면, 해당 블럭만 수행
    - if-else if문 전체를 벗어남
  - 결과가 참인 조건식이 없음
    - else블럭이 수행
    - else 블럭 생략한 경우
      - if-else if문의 어떤 블럭도 수행 x 가능

# 07 중첩 if문

- 중첩의 횟수에는 거의 제한 없음

```java
if (조건식1) {
   // 조건식1의 연산결과가 true일 때 수행될 문장들을 적는다.
   if (조건식2) {
     // 조건식1과 조건식2가 모두 true일 때 수행될 문장들
   } else {
     // 조건식1이 true이고, 조건식2가 false일 때 수행되는 문장들
   }
} else {
   // 조건식1이 false일 때 수행되는 문장들
}
```

- (주의) 괄호가 생략됐을 때 else블럭은 가까운 if문에 속한 것으로 간주됨

# 09 switch문

```java
switch(조건식) {
			case 값1 :
				// 조건식의 결과가 값1과 같을 경우 수행될 문장들
				// ...
				break;
			case 값2 :
				// 조건식의 결과가 값2와 같을 경우 수행될 문장들
				// ...
				break;  // switch문을 벗어난다.
			// ...
			default :
				// 조건식의 결과와 일치하는 case문이 없을 때 수행될 문장들
				// ...

		}
```

1. 조건식 계산
2. 조건식의 결과와 일치하는 case문으로 이동
3. 이후 문장 수행
4. break문이나 switch문의 끝을 만나면 switch문 전체를 빠져나감

- 하나의 조건식으로 많은 경우 처리 가능
- 제약조건이 있음
- break문
  - 각 case문의 마지막에 break문 빼먹지 말기.
- default문
  - 조건식의 결과와 일치하는 case문이 없으면 default문으로 이동.
  - 보통 마지막에 놓기 때문에 break문을 사용하지 않아도 ok

# 4.10. switch문의 제약조건

1. switch문의 조건식 결과는 정수 또는 문자열이어야 한다.
2. case문의 값은 정수 상수(문자 포함), 문자열만 가능하며, 중복되지 않아야 한다.

```java
public static void main(String[] args) {
		int num, result;
		final int ONE = 1;
		...
		switch(result) {
			case '1':   // 문자 리터럴
			case ONE:   // 정수 상수
			case "YES": // 문자열 리터럴
			case num:   // 변수 불가
			case 1.0;   // 실수 불가
      ...
		}

	}
```

# 4.11. switch문의 제약조건 예제

- case문은 한 줄에 하나씩 쓰던, 한 줄에 붙여서 쓰던 무관하다.

```java
switch(month) {
			case 3:
			case 4:
			case 5:
				System.out.println("the current season is spring.");
				break;
			case 6: case 7: case 8:
				System.out.println("the current season is summer.");
				break;
			case 9: case 10: case 11:
				System.out.println("the current season is fall.");
				break;
			default:
				System.out.println("the current season is winter.");
		};
```

# 4.12 임의의 정수만들기 Math.random()

- Math.random()
  - 0.0~1.0 사이 범위에 속하는 double값 반환(이상, 미만)
- 1과 3 사이 정수를 구한다면?
  - 1 ≤ (int)(Math.random() \* 3) + 1 < 4

# 13 for문

```java
for (초기화;조건식;증감식) {
	// 조건식이 참(true)인 동안 수행될 문장들을 적음
}
```

### ****\*\*\*\*****초기화****\*\*\*\*****

둘 이상의 변수가 필요할 때는 콤마를 구분자로 초기화하기(변수 타입 같아야 함)

```java
for(int i=1, j=0; i<= 10; i++) { ... } // int 타입의 변수 i와 j를 선언하고 초기화
```

### ****\*\*\*\*****조건식****\*\*\*\*****

거짓일 때 for문을 벗어남

### ******\*\*******증감식******\*\*******

- 다양한 연산자 사용 가능(++, —, +=, \*= …)
- 콤마를 구분자로 두 문장 이상을 연결할 수 있음
  ```java
  for(int i=1, j=10; i<=10 ;i++, j--) { ... }
  // i는 1부터 10까지 1씩 증가
  // i는 10부터 1까지 1씩 감소
  ```

초기화, 조건식, 증감식은 모두 생략가능함

```java
for(;;) {...} // 조건식은 참이 된다.
```

⇒ 조건식 생략은 참으로 간주, 무한 반복문

# 16 while문

```java
while(조건식) {
}
```

- for문-while문은 항상 서로 변환 가능
  - 초기화, 증감식 필요 x - while문이 더 적합

# 17 while문 예제1

- 후위형 감소 연산자 사용
  ```java
  	while(i-- != 0) {
  	System.out.println(i + " - I can do it.");
  }
  ```
  ```java
  while(i!=0) {
  	i--;
  	System.out.println(i + " - I can do it.");
  }
  ```

# 18 while문 예제 2

n % 10 → 마지막 자리

n / 10 → 마지막 자리 제거

# 19 do-while문

```java
do {
		// 조건식의 연산결과가 참일 때 수행될 문장들
		// 처음 한 번은 무조건 실행
} while (조건식);
```

# 20 break문

- 자신이 포함된 가장 가까운 반복문을 벗어남.
- 무한 반복문에는 조건문, break문이 항상 같이 사용됨.
