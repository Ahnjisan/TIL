# Java 변수와 기본 구조

## 1. 변수란?

변수는 데이터를 저장하기 위한 공간이다.

Java에서 변수는 객체의 명사적인 특징을 표현할 때 사용된다.

예를 들어 회원이라는 객체를 생각하면 이름, 이메일, 나이 같은 값이 변수로 표현될 수 있다.

    회원
    → 이름
    → 이메일
    → 나이

객체 지향 프로그래밍에서는 현실 세계의 객체를 분석한 뒤, 객체가 가진 속성을 변수로 표현한다.

## 2. 변수와 메서드의 차이

Class 안에는 변수와 메서드를 정의할 수 있다.

| 구분 | 의미 | 예시 |
|---|---|---|
| 변수 | 객체의 속성 또는 상태 | name, age, email |
| 메서드 | 객체의 동작 또는 기능 | login, printMessage, playGame |

변수는 명사적인 특징을 표현하고, 메서드는 동사적인 행위를 표현한다.

예를 들어 학생 객체를 생각하면 다음과 같이 나눌 수 있다.

| 구분 | 예시 |
|---|---|
| 변수 | 이름, 학번, 점수 |
| 메서드 | 공부하다, 출석하다, 시험보다 |

## 3. 자료형이 필요한 이유

Java에서 변수는 값을 저장하는 공간이다.

하지만 어떤 종류의 값을 저장할 것인지도 함께 정해야 한다.

이때 사용하는 것이 자료형이다.

자료형은 변수에 저장할 수 있는 데이터의 종류를 의미한다.

예를 들어 숫자를 저장할 변수인지, 문자를 저장할 변수인지, 참과 거짓을 저장할 변수인지에 따라 자료형이 달라진다.

## 4. Java의 기본 자료형

Java의 대표적인 기본 자료형은 다음과 같다.

| 자료형 | 설명 | 예시 |
|---|---|---|
| int | 정수 | 10, 100 |
| long | 큰 정수 | 10000000000L |
| double | 실수 | 3.14 |
| boolean | 참 또는 거짓 | true, false |
| char | 문자 하나 | 'A' |
| String | 문자열 | "Hello" |

`String`은 엄밀히 말하면 기본 자료형은 아니지만, 문자열을 다룰 때 가장 자주 사용하는 타입이다.

## 5. 변수 선언

Java에서 변수를 사용하려면 먼저 변수를 선언해야 한다.

기본 형식은 다음과 같다.

    자료형 변수명;

예시는 다음과 같다.

    int age;
    String name;
    boolean isLogin;

변수를 선언한다는 것은 해당 이름으로 데이터를 저장할 공간을 만들겠다는 의미이다.

## 6. 변수 초기화

변수에 처음 값을 넣는 것을 초기화라고 한다.

기본 형식은 다음과 같다.

    자료형 변수명 = 값;

예시는 다음과 같다.

    int age = 25;
    String name = "Jisan";
    boolean isLogin = true;

변수는 선언만 할 수도 있고, 선언과 동시에 값을 넣을 수도 있다.

## 7. 변수 값 변경

변수는 이름 그대로 값이 변할 수 있는 공간이다.

처음 저장한 값을 나중에 다른 값으로 바꿀 수 있다.

예시는 다음과 같다.

    int score = 80;
    score = 90;

처음에는 `score`에 80이 저장되었지만, 이후 90으로 변경된다.

단, 값을 변경할 때는 변수 선언 시 사용한 자료형과 맞는 값을 넣어야 한다.

## 8. Java 식별자

식별자는 개발자가 클래스, 변수, 메서드 등에 붙이는 이름이다.

Java에서 식별자를 작성할 때는 대소문자를 구분한다.

예를 들어 다음 두 이름은 서로 다른 이름이다.

    GreetingApp
    greetingApp

Java는 대소문자를 구분하기 때문에 이름을 작성할 때 정확히 입력해야 한다.

## 9. Class 이름 규칙

Java에서 Class 이름은 일반적으로 대문자로 시작한다.

예시는 다음과 같다.

    GreetingApp
    Student
    Member
    OrderService

또한 public class 이름은 파일 이름과 동일해야 한다.

예를 들어 파일 이름이 `GreetingApp.java`라면 클래스 이름도 `GreetingApp`이어야 한다.

    GreetingApp.java
    → public class GreetingApp

파일 이름과 public class 이름이 다르면 오류가 발생할 수 있다.

## 10. 변수 이름 규칙

변수 이름은 일반적으로 소문자로 시작한다.

단어가 여러 개 연결될 때는 두 번째 단어부터 첫 글자를 대문자로 작성하는 camelCase 방식을 사용한다.

예시는 다음과 같다.

    name
    age
    engScore
    userEmail
    memberName

변수는 명사적인 의미를 가지는 이름으로 작성하는 것이 좋다.

좋은 예시는 다음과 같다.

    age
    score
    userName

좋지 않은 예시는 다음과 같다.

    a
    test
    data

의미가 명확한 변수명을 사용하면 코드를 이해하기 쉬워진다.

## 11. 메서드 이름 규칙

메서드는 동작이나 행위를 표현한다.

따라서 메서드 이름은 보통 동사 또는 동사와 명사의 조합으로 작성한다.

변수와 마찬가지로 소문자로 시작하고 camelCase 방식을 사용한다.

예시는 다음과 같다.

    run
    login
    playGame
    printMessage
    calculateScore

메서드 이름만 보아도 어떤 동작을 하는지 알 수 있게 작성하는 것이 좋다.

## 12. Camel Case

Camel Case는 여러 단어를 연결할 때 두 번째 단어부터 첫 글자를 대문자로 작성하는 방식이다.

예시는 다음과 같다.

    engScore
    userName
    printMessage
    playGame

낙타의 혹처럼 중간중간 대문자가 올라오는 형태라서 camelCase라고 부른다.

Java에서는 변수명과 메서드명에 camelCase를 자주 사용한다.

## 13. Java의 대소문자 구분

Java는 대소문자를 구분하는 언어이다.

예를 들어 다음 코드는 서로 다르게 인식된다.

    System
    system

Java에서 콘솔 출력문을 작성할 때는 다음처럼 `System`의 첫 글자를 대문자로 작성해야 한다.

    System.out.println("Hello Java");

만약 다음처럼 작성하면 오류가 발생한다.

    system.out.println("Hello Java");

VS Code에서는 잘못 작성된 코드에 빨간 밑줄이 표시될 수 있다.

## 14. Java 소스 파일

Java 소스 파일은 `.java` 확장자를 가진다.

예시는 다음과 같다.

    GreetingApp.java

이 파일 안에는 Java 코드가 작성된다.

Java 소스 파일은 사람이 이해할 수 있는 고급 언어로 작성된 파일이다.

컴퓨터가 바로 실행할 수 있는 형태가 아니기 때문에 컴파일 과정이 필요하다.

## 15. 컴파일

컴파일은 사람이 작성한 소스 코드를 컴퓨터가 실행할 수 있는 형태로 변환하는 과정이다.

Java에서는 `javac` 명령어가 컴파일을 담당한다.

흐름은 다음과 같다.

    .java 파일 작성
    → javac로 컴파일
    → .class 파일 생성

예시는 다음과 같다.

    javac GreetingApp.java

컴파일이 성공하면 `GreetingApp.class` 파일이 생성된다.

## 16. Bytecode

Java 소스 코드를 컴파일하면 `.class` 파일이 생성된다.

이 `.class` 파일 안에는 Bytecode가 들어 있다.

Bytecode는 JVM이 이해할 수 있는 코드이다.

Java 프로그램은 운영체제에서 직접 실행되는 것이 아니라 JVM 위에서 실행된다.

따라서 Java는 운영체제에 직접 의존하지 않고 JVM에 의존해서 동작한다.

## 17. java 명령어

컴파일된 `.class` 파일을 실행할 때는 `java` 명령어를 사용한다.

예시는 다음과 같다.

    java GreetingApp

`javac`는 컴파일 명령어이고, `java`는 실행 명령어이다.

| 명령어 | 역할 |
|---|---|
| javac | `.java` 파일을 `.class` 파일로 컴파일 |
| java | 컴파일된 Java 프로그램 실행 |

## 18. main 메서드

Java 프로그램은 `main` 메서드에서 실행을 시작한다.

기본 구조는 다음과 같다.

    public static void main(String[] args)

main 메서드는 Java 프로그램의 진입점이다.

즉, 프로그램을 실행하면 JVM은 main 메서드부터 실행한다.

## 19. 출력문

Java에서 콘솔에 내용을 출력할 때는 `System.out.println()`을 사용한다.

예시는 다음과 같다.

    System.out.println("처음 만나는 Java");

문자열은 큰따옴표로 감싼다.

실행하면 터미널에 해당 문자열이 출력된다.

## 20. Java 기본 코드 구조

Java의 기본 코드 구조는 다음과 같다.

    public class GreetingApp {
        public static void main(String[] args) {
            System.out.println("처음 만나는 Java");
        }
    }

각 요소의 의미는 다음과 같다.

| 요소 | 의미 |
|---|---|
| public class GreetingApp | GreetingApp 클래스 정의 |
| main method | Java 프로그램 실행 시작점 |
| System.out.println | 콘솔 출력 |

## 21. 정리

이번 학습에서는 Java의 변수 개념, 식별자 규칙, 기본 실행 구조를 정리했다.

핵심 개념은 다음과 같다.

- 변수는 데이터를 저장하는 공간이다.
- 자료형은 변수에 저장할 데이터의 종류를 의미한다.
- Java에서는 변수를 선언할 때 자료형을 함께 작성한다.
- 변수는 객체의 명사적인 특징을 표현할 수 있다.
- 메서드는 객체의 동작을 표현한다.
- Class 이름은 일반적으로 대문자로 시작한다.
- 변수와 메서드 이름은 일반적으로 소문자로 시작한다.
- 여러 단어를 연결할 때 camelCase를 사용한다.
- Java는 대소문자를 구분한다.
- public class 이름은 파일 이름과 동일해야 한다.
- Java 소스 파일은 `.java` 확장자를 가진다.
- `javac`는 Java 소스 코드를 컴파일한다.
- 컴파일 결과로 `.class` 파일이 생성된다.
- `.class` 파일에는 JVM이 이해할 수 있는 Bytecode가 들어 있다.
- `java` 명령어는 컴파일된 Java 프로그램을 실행한다.
- Java 프로그램은 `main` 메서드에서 실행을 시작한다.
- 콘솔 출력에는 `System.out.println()`을 사용할 수 있다.