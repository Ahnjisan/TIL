# Java 객체 지향 기본 개념

## 1. 객체 지향 프로그래밍이란?

Java는 객체 지향 프로그래밍 언어이다.

객체 지향 프로그래밍은 현실 세계에 존재하는 유형 또는 무형의 객체를 프로그램 안에서 표현하는 방식이다.

예를 들어 강사, 학생, 회원, 주문, 게시글, 계좌 같은 개념은 모두 객체로 볼 수 있다.

객체는 보통 두 가지 특징을 가진다.

| 구분 | 의미 | 예시 |
|---|---|---|
| 명사적인 특징 | 객체가 가진 상태나 속성 | 이름, 나이, 주소 |
| 동사적인 특징 | 객체가 수행하는 행위 | 먹다, 가르치다, 로그인하다 |

Java에서는 명사적인 특징을 변수로 표현하고, 동사적인 특징을 메서드로 표현한다.

## 2. Class란?

Class는 객체를 만들기 위한 템플릿이다.

현실 세계의 객체를 프로그램 안에서 사용하려면 먼저 그 객체를 코드로 표현할 수 있는 설계도가 필요하다.

이 설계도 역할을 하는 것이 Class이다.

즉, Class는 인스턴스를 만들기 위한 틀이다.

    Class
    → 객체를 만들기 위한 템플릿
    → 변수와 메서드를 가짐
    → 인스턴스 생성의 기준이 됨

## 3. Instance란?

Instance는 Class를 바탕으로 메모리에 실제로 생성된 객체이다.

Class는 설계도이고, Instance는 그 설계도를 기반으로 만들어진 실제 객체라고 이해할 수 있다.

| 구분 | 설명 |
|---|---|
| Class | 객체를 만들기 위한 템플릿 |
| Instance | Class를 기반으로 메모리에 생성된 실제 객체 |

Class와 Instance는 같은 의미가 아니다.

Class는 Class이고, Instance는 Instance이다.

## 4. Class와 Instance를 구분해야 하는 이유

Class에 변수와 메서드를 정의했다고 해서 바로 외부에서 사용할 수 있는 것은 아니다.

Class에 정의된 변수와 메서드는 Class 자체의 소유가 아니라 Instance의 소유로 이해해야 한다.

따라서 외부 클래스에서 특정 Class의 변수나 메서드에 접근하려면 먼저 Instance를 생성해야 한다.

흐름은 다음과 같다.

    Class 정의
    → new 키워드로 Instance 생성
    → 참조 변수에 Instance 주소 저장
    → 참조 변수를 통해 변수와 메서드 접근

즉, Class는 템플릿이고 실제 사용 대상은 Instance이다.

## 5. Class의 구성 요소

Class는 주로 변수와 메서드로 구성된다.

| 구성 요소 | 의미 |
|---|---|
| 변수 | 객체의 상태 또는 속성 |
| 메서드 | 객체의 기능 또는 행위 |

예를 들어 `Teacher`라는 Class를 만든다고 가정하면 다음과 같이 구성할 수 있다.

| 구분 | 예시 |
|---|---|
| 변수 | name, age, address, isMarried |
| 메서드 | eating(), teaching() |

변수는 객체의 명사적인 특징을 나타내고, 메서드는 객체의 동사적인 특징을 나타낸다.

## 6. Teacher 클래스 예시

강사라는 객체를 프로그램에서 표현하려면 `Teacher` 클래스를 만들 수 있다.

예시는 다음과 같다.

    public class Teacher {
        public String name;
        public int age;
        public String address;
        public boolean isMarried;

        public void eating() {
            System.out.println("먹는다");
        }

        public String teaching(String subject) {
            return subject + "를 가르친다";
        }
    }

위 코드에서 `name`, `age`, `address`, `isMarried`는 변수이다.

`eating()`과 `teaching()`은 메서드이다.

## 7. 변수

변수는 객체의 상태나 속성을 표현한다.

예를 들어 강사 객체가 가진 이름, 나이, 주소, 결혼 여부 같은 값은 변수로 표현할 수 있다.

    public String name;
    public int age;
    public String address;
    public boolean isMarried;

변수를 선언할 때는 다음과 같은 형식을 사용한다.

    접근지정자 타입 변수명;

예를 들어 `public String name;`은 외부에서 접근 가능한 문자열 타입의 name 변수를 선언한 것이다.

## 8. 메서드

메서드는 객체의 행위나 기능을 표현한다.

메서드는 선언되어 있다고 자동으로 실행되지 않는다.

누군가에 의해 호출되어야 실행된다.

예시는 다음과 같다.

    public void eating() {
        System.out.println("먹는다");
    }

이 메서드는 반환값이 없고, 매개변수도 없는 메서드이다.

반환값이 없을 때는 `void`를 사용한다.

## 9. 반환 타입이 있는 메서드

메서드는 실행 결과를 호출한 쪽으로 반환할 수 있다.

예시는 다음과 같다.

    public String teaching(String subject) {
        return subject + "를 가르친다";
    }

이 메서드는 문자열 타입의 `subject`를 매개변수로 전달받는다.

그리고 문자열 결과를 반환한다.

반환 타입이 `String`이므로 메서드 내부에서 반드시 문자열을 `return`해야 한다.

## 10. 메서드 호출

메서드는 정의만으로 실행되지 않는다.

메서드를 실행하려면 호출해야 한다.

예를 들어 다음과 같이 호출할 수 있다.

    teacher.eating();

    String result = teacher.teaching("Java");

`eating()`은 호출되면 내부의 출력문이 실행된다.

`teaching("Java")`는 문자열을 전달받아 처리한 뒤 결과를 반환한다.

반환된 값은 변수에 담아서 사용할 수 있다.

## 11. new 키워드

Class를 기반으로 Instance를 생성할 때는 `new` 키워드를 사용한다.

예시는 다음과 같다.

    new Teacher();

이 코드는 `Teacher` 클래스를 기반으로 메모리에 새로운 Instance를 생성한다.

하지만 생성된 Instance를 계속 사용하려면 그 주소 값을 담을 변수가 필요하다.

그래서 보통 다음과 같이 작성한다.

    Teacher teacher = new Teacher();

## 12. 참조 타입 변수

`Teacher teacher = new Teacher();` 코드는 두 부분으로 나누어 이해할 수 있다.

| 코드 | 의미 |
|---|---|
| `Teacher teacher` | Teacher 타입의 참조 변수 선언 |
| `new Teacher()` | Teacher 인스턴스 생성 |

여기서 `Teacher`는 사용자가 직접 만든 Class 타입이다.

기본 타입이 아니므로 참조 타입으로 볼 수 있다.

참조 타입 변수는 실제 값을 직접 저장하는 것이 아니라, 생성된 객체의 주소 값을 저장한다.

## 13. Dot Operator

Instance를 생성한 뒤에는 dot operator를 사용해 변수와 메서드에 접근할 수 있다.

dot operator는 점 `.`을 의미한다.

예시는 다음과 같다.

    teacher.name = "Jisan";
    System.out.println(teacher.name);

    teacher.eating();

    String result = teacher.teaching("Java");
    System.out.println(result);

`teacher.name`은 teacher 인스턴스의 name 변수에 접근하는 것이다.

`teacher.eating()`은 teacher 인스턴스의 eating 메서드를 호출하는 것이다.

## 14. main 메서드가 없는 클래스

모든 클래스가 `main` 메서드를 가져야 하는 것은 아니다.

`main` 메서드는 Java 프로그램의 실행 시작점이다.

따라서 직접 실행할 클래스에는 `main` 메서드가 필요하다.

하지만 인스턴스를 만들기 위한 템플릿 역할의 클래스는 `main` 메서드가 없어도 된다.

예를 들어 `Teacher` 클래스는 직접 실행하기 위한 클래스라기보다, `Teacher` 인스턴스를 만들기 위한 템플릿이다.

## 15. 실행용 클래스

인스턴스를 생성하고 사용하는 코드는 보통 실행용 클래스에서 작성한다.

예를 들어 `TeacherApp` 클래스를 만들 수 있다.

    public class TeacherApp {
        public static void main(String[] args) {
            Teacher teacher = new Teacher();

            teacher.name = "Jisan";
            System.out.println(teacher.name);

            teacher.eating();

            String result = teacher.teaching("Java");
            System.out.println(result);
        }
    }

`TeacherApp` 클래스에는 `main` 메서드가 있으므로 실행할 수 있다.

그리고 `Teacher` 클래스를 기반으로 Instance를 생성한 뒤 변수와 메서드에 접근한다.

## 16. 여러 Class가 함께 동작하는 구조

실제 개발에서는 하나의 Class만으로 프로그램을 만들지 않는다.

여러 개의 Class가 각자의 역할을 가지고 함께 동작한다.

예를 들어 다음과 같이 나눌 수 있다.

| Class | 역할 |
|---|---|
| Teacher | 강사 객체의 속성과 기능 정의 |
| TeacherApp | 프로그램 실행 및 Teacher 인스턴스 사용 |

이처럼 Class를 역할별로 나누면 코드의 책임이 명확해진다.

## 17. 객체 지향 코드 흐름

객체 지향 코드의 기본 흐름은 다음과 같다.

    현실 세계의 객체 분석
    → 명사적인 특징을 변수로 정의
    → 동사적인 특징을 메서드로 정의
    → Class 작성
    → new 키워드로 Instance 생성
    → 참조 변수를 통해 변수와 메서드 사용

Java에서 Class를 만드는 이유는 결국 프로그램에서 사용할 Instance를 만들기 위해서이다.

## 18. 정리

이번 학습에서는 Java 객체 지향의 기본 개념을 정리했다.

핵심 개념은 다음과 같다.

- Java는 객체 지향 프로그래밍 언어이다.
- 객체는 명사적인 특징과 동사적인 특징을 가진다.
- 명사적인 특징은 변수로 표현한다.
- 동사적인 특징은 메서드로 표현한다.
- Class는 Instance를 만들기 위한 템플릿이다.
- Instance는 Class를 기반으로 메모리에 생성된 실제 객체이다.
- Class와 Instance는 같은 개념이 아니다.
- Class에 정의된 변수와 메서드는 Instance의 소유로 이해해야 한다.
- 외부에서 변수와 메서드에 접근하려면 먼저 Instance를 생성해야 한다.
- Instance 생성에는 `new` 키워드를 사용한다.
- Class도 변수의 타입으로 사용할 수 있다.
- 사용자가 만든 Class 타입은 참조 타입이다.
- 참조 타입 변수는 객체의 주소 값을 저장한다.
- dot operator를 사용하면 Instance의 변수와 메서드에 접근할 수 있다.
- 메서드는 정의만으로 실행되지 않고 호출되어야 실행된다.
- 반환 타입이 있는 메서드는 `return`을 통해 값을 반환해야 한다.
- 모든 Class가 main 메서드를 가져야 하는 것은 아니다.