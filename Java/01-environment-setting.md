# Java 개발 환경 세팅

## 1. Java를 배우는 이유

Java는 국내 공공기관, 금융권, 기업 내부 시스템에서 많이 사용되는 프로그래밍 언어이다.

특히 백엔드 개발에서 Java는 Spring Boot와 함께 많이 사용된다.

웹 서비스는 보통 프론트엔드와 백엔드로 나뉜다.

| 구분 | 역할 |
|---|---|
| Frontend | 사용자가 보는 화면 구성 |
| Backend | 요청 처리, 데이터 처리, 응답 반환 |
| Database | 서비스에 필요한 데이터 저장 |

프론트엔드는 직접 데이터를 가지고 있지 않기 때문에 백엔드와 통신하여 필요한 데이터를 가져온다.

Java는 이 백엔드 영역에서 많이 사용되며, Spring Boot를 통해 웹 애플리케이션 서버를 만들 수 있다.

## 2. Python과 Java의 차이

개발 입문 과정에서 자주 접하는 대표적인 언어로 Python과 Java가 있다.

| 언어 | 주 사용 분야 |
|---|---|
| Python | 인공지능, 데이터 분석, 데이터 사이언스 |
| Java | 백엔드, 공공기관, 금융권, 기업 시스템 |

Python은 AI와 데이터 분석 분야에서 많이 사용된다.

반면 Java는 대규모 백엔드 시스템과 기업용 애플리케이션에서 많이 사용된다.

## 3. Java의 특징

Java는 객체 지향 프로그래밍 언어이다.

객체 지향 프로그래밍은 영어로 Object-Oriented Programming이라고 하며, 줄여서 OOP라고 부른다.

객체 지향은 현실 세계에 존재하는 사물이나 개념을 프로그램 안에서 객체로 표현하는 방식이다.

예를 들어 회원, 주문, 상품, 계좌 같은 개념을 프로그램 안에서 객체로 표현할 수 있다.

## 4. Class와 Instance

Java에서 Class는 객체를 만들기 위한 템플릿이다.

현실 세계의 객체를 프로그램 안으로 그대로 가져올 수는 없기 때문에, 객체의 특징과 동작을 코드로 정의한 설계도가 필요하다.

이 설계도 역할을 하는 것이 Class이다.

Class를 바탕으로 프로그램 안에서 실제로 만들어진 객체를 Instance라고 한다.

| 구분 | 설명 |
|---|---|
| Class | 객체를 만들기 위한 설계도 |
| Instance | Class를 바탕으로 생성된 실제 객체 |

## 5. Variable과 Method

Class 안에는 변수와 메서드를 정의할 수 있다.

| 구성 요소 | 의미 |
|---|---|
| Variable | 객체의 명사적인 특징 |
| Method | 객체의 동작 또는 행위 |

예를 들어 회원이라는 객체를 생각하면 이름, 이메일, 나이는 변수로 표현할 수 있고 로그인하다, 회원가입하다, 정보를 수정하다 같은 행위는 메서드로 표현할 수 있다.

정리하면 다음과 같다.

    Class
    → Variable
    → Method
    → Instance 생성

## 6. Java 개발 환경이 필요한 이유

Java 코드를 작성하고 실행하기 위해서는 개발 환경이 필요하다.

VS Code는 코드를 작성할 수 있는 편집기이다.

하지만 Java 코드를 실행하려면 Java 실행 환경이 별도로 필요하다.

이를 위해 설치해야 하는 것이 JDK이다.

JDK는 Java Development Kit의 약자이며, Java 개발을 위한 도구 모음이다.

## 7. JDK, JRE, JVM

Java 개발 환경을 이해하기 위해서는 JDK, JRE, JVM의 관계를 알아야 한다.

| 용어 | 의미 |
|---|---|
| JDK | Java Development Kit, Java 개발 도구 |
| JRE | Java Runtime Environment, Java 실행 환경 |
| JVM | Java Virtual Machine, Java 가상 머신 |

JDK를 설치하면 Java 개발에 필요한 도구와 실행 환경이 함께 설치된다.

Java 프로그램은 운영체제에서 직접 실행되는 것이 아니라 JVM 위에서 실행된다.

## 8. JVM과 플랫폼 독립성

Java의 중요한 특징 중 하나는 플랫폼 독립성이다.

Java 프로그램은 Windows, Mac, Linux 같은 운영체제에 직접 의존하지 않고 JVM 위에서 실행된다.

따라서 운영체제가 달라도 해당 운영체제에 맞는 JVM이 설치되어 있다면 Java 프로그램을 실행할 수 있다.

이를 표현하는 문장이 다음과 같다.

    Write Once, Run Anywhere

즉, 한 번 작성한 Java 코드를 JVM이 설치된 다양한 환경에서 실행할 수 있다는 의미이다.

## 9. JDK 버전 선택

JDK는 여러 종류와 버전이 존재한다.

대표적으로 Oracle JDK, OpenJDK, Eclipse Temurin JDK 등이 있다.

이번 실습에서는 Eclipse Adoptium에서 제공하는 Temurin JDK 17을 기준으로 설치했다.

Spring Boot 3.x 버전은 Java 17 이상을 요구하기 때문에, Spring Boot 학습을 고려한다면 Java 17 또는 Java 21을 사용하는 것이 적절하다.

| 버전 | 특징 |
|---|---|
| Java 11 | 현업에서 많이 사용되는 LTS 버전 |
| Java 17 | Spring Boot 3.x 학습에 적합한 LTS 버전 |
| Java 21 | 비교적 최신 LTS 버전 |

## 10. JDK 설치 흐름

JDK 설치 흐름은 다음과 같다.

    Eclipse Adoptium 사이트 접속
    → Temurin JDK 17 선택
    → 운영체제에 맞는 설치 파일 다운로드
    → 설치 파일 실행
    → 라이선스 동의
    → 기본 설치 경로 확인
    → 설치 진행
    → 설치 완료

Windows 환경에서는 보통 다음과 같은 경로에 설치된다.

    C:\Program Files\Eclipse Adoptium\jdk-17...

JDK 설치 폴더 안의 `bin` 디렉터리에는 Java 명령어들이 들어 있다.

대표적인 명령어는 다음과 같다.

| 명령어 | 역할 |
|---|---|
| javac | Java 소스 코드 컴파일 |
| java | Java 프로그램 실행 |

## 11. JAVA_HOME 설정

`JAVA_HOME`은 JDK가 설치된 위치를 나타내는 환경 변수이다.

간단한 Java 문법 실습만 한다면 반드시 필요하지는 않을 수 있다.

하지만 Spring Boot, Gradle, Maven 같은 도구들은 JDK 위치를 확인하기 위해 `JAVA_HOME`을 사용하는 경우가 많다.

따라서 Java 백엔드 개발을 학습할 예정이라면 `JAVA_HOME`을 설정하는 것이 좋다.

설정 흐름은 다음과 같다.

    내 PC 우클릭
    → 속성
    → 고급 시스템 설정
    → 환경 변수
    → 시스템 변수 새로 만들기
    → 변수 이름: JAVA_HOME
    → 변수 값: JDK 설치 경로

## 12. PATH 설정

PATH는 터미널에서 실행할 수 있는 명령어의 위치를 등록하는 환경 변수이다.

JDK의 `bin` 디렉터리가 PATH에 등록되어 있어야 터미널에서 `java`, `javac` 명령어를 사용할 수 있다.

확인해야 할 경로는 다음과 같다.

    C:\Program Files\Eclipse Adoptium\jdk-17...\bin

JDK 설치 과정에서 자동으로 PATH가 등록될 수 있다.

## 13. Java 설치 확인

JDK 설치와 환경 변수 설정이 끝났다면 CMD에서 Java 명령어를 확인한다.

    java

    javac

또는 버전 확인 명령어를 사용할 수 있다.

    java -version

    javac -version

명령어가 정상적으로 실행되면 Java 개발 환경이 준비된 상태이다.

명령어가 인식되지 않는다면 JDK 설치 경로 또는 PATH 설정을 다시 확인해야 한다.

## 14. VS Code Java 확장 설치

VS Code에서 Java를 편하게 작성하고 실행하려면 Java 확장 프로그램이 필요하다.

이번 실습에서는 `Extension Pack for Java`를 설치했다.

설치 흐름은 다음과 같다.

    VS Code 실행
    → Extensions 메뉴 열기
    → Extension Pack for Java 검색
    → Install
    → Java 개발 환경 구성 완료

이 확장팩을 설치하면 Java 파일 작성, 자동 완성, 오류 표시, 실행 기능 등을 사용할 수 있다.

## 15. Java 프로젝트 폴더 구성

Java 실습 코드는 기존 프론트엔드 실습과 구분해서 관리하는 것이 좋다.

이번 실습에서는 다음과 같은 구조를 사용했다.

    backend
    └── java-project

VS Code에서 `java-project` 폴더를 열고 Java 파일을 작성했다.

이렇게 폴더를 분리하면 프론트엔드 실습 코드와 Java 백엔드 학습 코드를 구분해서 관리할 수 있다.

## 16. 첫 Java 파일 작성

실습에서는 `GreetingApp.java` 파일을 생성했다.

Java에서는 public class 이름과 파일 이름이 동일해야 한다.

예를 들어 파일 이름이 `GreetingApp.java`라면 클래스 이름도 `GreetingApp`이어야 한다.

    파일 이름: GreetingApp.java
    클래스 이름: GreetingApp

Java 프로그램의 기본 구조는 다음과 같다.

    public class GreetingApp {
        public static void main(String[] args) {
            System.out.println("처음 만나는 Java");
        }
    }

## 17. main 메서드

Java에서 `main` 메서드는 프로그램의 실행 시작점이다.

프로그램을 실행하면 JVM은 `main` 메서드부터 실행한다.

    public static void main(String[] args)

`System.out.println()`은 콘솔에 문자열을 출력할 때 사용한다.

    System.out.println("처음 만나는 Java");

VS Code에서 Run 버튼을 누르면 Java 프로그램이 실행되고, 터미널 영역에서 출력 결과를 확인할 수 있다.

## 18. 저장과 실행

Java 파일을 수정한 뒤에는 반드시 저장해야 한다.

VS Code에서는 저장과 동시에 코드 분석이 이루어지고, 오류가 있으면 빨간 밑줄로 표시될 수 있다.

실행 흐름은 다음과 같다.

    Java 파일 작성
    → 저장
    → 오류 확인
    → Run 실행
    → 터미널에서 결과 확인

Java는 대소문자를 구분하기 때문에 `System`을 `system`으로 작성하면 오류가 발생한다.

## 19. 정리

이번 학습에서는 Java 개발 환경 세팅 과정을 정리했다.

핵심 개념은 다음과 같다.

- Java는 백엔드와 기업 시스템에서 많이 사용된다.
- Java는 객체 지향 프로그래밍 언어이다.
- Class는 객체를 만들기 위한 설계도이다.
- Instance는 Class를 바탕으로 생성된 실제 객체이다.
- Variable은 객체의 속성을 표현한다.
- Method는 객체의 동작을 표현한다.
- Java 개발을 위해서는 JDK가 필요하다.
- JDK는 Java Development Kit의 약자이다.
- JRE는 Java Runtime Environment의 약자이다.
- JVM은 Java Virtual Machine의 약자이다.
- Java 프로그램은 JVM 위에서 실행된다.
- `JAVA_HOME`은 JDK 설치 경로를 나타내는 환경 변수이다.
- `PATH`에 JDK의 `bin` 경로가 등록되어야 `java`, `javac` 명령어를 사용할 수 있다.
- VS Code에서 Java를 사용하려면 Extension Pack for Java를 설치할 수 있다.
- Java 프로그램은 `main` 메서드에서 실행을 시작한다.