# Java Class, Instance와 프로젝트 구조

## 1. Class와 Instance 복습

Class는 Instance를 만들기 위한 템플릿이다.

Instance는 Class를 기반으로 실제 메모리에 생성된 객체이다.

Java에서 Class를 작성하는 이유는 프로그램 영역에서 사용할 객체를 생성하기 위해서이다.

    Class
    → 템플릿

    Instance
    → Class를 기반으로 생성된 실제 객체

Class와 Instance는 반드시 구분해야 한다.

## 2. Instance 생성 문법

Instance를 생성할 때는 `new` 키워드를 사용한다.

기본 형식은 다음과 같다.

    클래스명 변수명 = new 클래스명();

예시는 다음과 같다.

    Teacher teacher = new Teacher();

이 코드는 `Teacher` 클래스를 기반으로 Instance를 생성하고, 그 주소 값을 `teacher` 변수에 저장한다.

## 3. 참조 변수

Class 타입으로 선언된 변수는 참조 변수이다.

예를 들어 다음 코드에서 `teacher`는 참조 변수이다.

    Teacher teacher = new Teacher();

참조 변수는 실제 객체 값을 직접 저장하는 것이 아니라, 객체가 메모리에 생성된 위치의 주소 값을 저장한다.

정리하면 다음과 같다.

| 구분 | 저장하는 값 |
|---|---|
| 기본 타입 변수 | 실제 값 |
| 참조 타입 변수 | 객체의 주소 값 |

`Teacher`는 사용자가 만든 Class 타입이므로 참조 타입이다.

## 4. Instance 구성 요소 접근

Instance의 변수와 메서드에 접근할 때는 dot operator를 사용한다.

dot operator는 점 `.`이다.

예시는 다음과 같다.

    teacher.name = "Jisan";
    teacher.eating();

`teacher.name`은 teacher 인스턴스가 가진 name 변수에 접근하는 것이다.

`teacher.eating()`은 teacher 인스턴스가 가진 eating 메서드를 호출하는 것이다.

## 5. Class 구성 요소의 소유

Class 안에 변수와 메서드를 정의할 수 있다.

하지만 Class에 정의된 변수와 메서드는 Class 자체의 소유가 아니라 Instance의 소유로 이해해야 한다.

따라서 다른 Class에서 특정 Class의 변수나 메서드를 사용하려면 먼저 해당 Class의 Instance를 생성해야 한다.

흐름은 다음과 같다.

    Class 작성
    → Instance 생성
    → 참조 변수에 주소 저장
    → dot operator로 변수와 메서드 접근

## 6. 여러 Class의 관계

실제 프로젝트에서는 여러 Class가 함께 동작한다.

하나의 Class가 모든 역할을 담당하지 않고, 각 Class가 역할을 나누어 가진다.

예를 들어 다음과 같은 구조를 생각할 수 있다.

| Class | 역할 |
|---|---|
| Teacher | 강사 객체의 속성과 기능 정의 |
| TeacherApp | 프로그램 실행 및 Teacher 사용 |

`TeacherApp`은 `Teacher`의 기능이 필요하기 때문에 `Teacher` 인스턴스를 생성해서 사용한다.

이처럼 한 Class가 다른 Class를 사용하면 의존 관계가 생긴다.

## 7. 의존 관계란?

의존 관계는 한 Class가 다른 Class의 기능을 필요로 하는 관계이다.

예를 들어 `TeacherApp`이 `Teacher`의 변수와 메서드를 사용한다면 `TeacherApp`은 `Teacher`에 의존한다고 볼 수 있다.

    TeacherApp
    → Teacher 인스턴스 생성
    → Teacher의 변수와 메서드 사용

객체 지향 프로그램은 여러 Class가 서로 필요한 기능을 사용하면서 동작한다.

## 8. Package란?

Package는 Java Class 파일을 역할이나 기능별로 묶어 관리하기 위한 구조이다.

프로젝트가 커질수록 Class 파일이 많아진다.

모든 Class를 한 위치에 두면 관리하기 어렵기 때문에 역할별로 패키지를 나누어 관리한다.

패키지는 폴더 구조와 비슷하게 이해할 수 있다.

예시는 다음과 같다.

    test.controller
    test.service
    test.repository
    test.domain.dto
    test.domain.entity

이처럼 패키지를 사용하면 프로젝트 구조를 더 명확하게 관리할 수 있다.

## 9. Import란?

서로 다른 패키지에 있는 Class를 사용하려면 `import`가 필요하다.

같은 패키지 안에 있는 Class는 바로 사용할 수 있지만, 다른 패키지에 있는 Class는 위치를 알려줘야 한다.

이때 사용하는 키워드가 `import`이다.

    import test.service.TestService;

`import`를 사용하면 다른 패키지에 있는 Class를 현재 Class에서 사용할 수 있다.

## 10. 백엔드 프로젝트의 계층 구조

Java 백엔드 프로젝트에서는 역할에 따라 Class를 나누는 경우가 많다.

Spring Framework 또는 Spring Boot 기반 프로젝트에서는 보통 다음과 같은 계층 구조를 가진다.

| 계층 | 역할 |
|---|---|
| Controller | 요청을 받고 흐름을 제어 |
| Service | 비즈니스 로직 처리 |
| Repository / DAO | 데이터베이스 접근 |
| DTO | 계층 간 데이터 전달 |
| Entity | 데이터베이스 테이블과 매핑 |

이 구조는 물리적으로 완전히 분리된 구조라기보다, 역할을 기준으로 나눈 논리적인 계층 구조이다.

## 11. Controller

Controller는 클라이언트의 요청을 받는 역할을 한다.

프론트엔드에서 백엔드로 요청이 들어오면 가장 먼저 Controller가 요청을 받는다.

Controller는 요청을 직접 모두 처리하기보다, 필요한 작업을 Service에 전달한다.

즉, Controller는 전체 흐름을 제어하는 역할을 한다.

    Frontend
    → Controller
    → Service 호출

## 12. Service

Service는 비즈니스 로직을 담당한다.

비즈니스 로직은 실제 서비스의 핵심 처리 규칙이다.

예를 들어 회원 가입, 로그인, 주문 처리, 결제 검증 같은 기능이 Service 계층에서 처리될 수 있다.

Controller는 요청을 받고, Service는 실제 로직을 처리한다.

    Controller
    → Service
    → 비즈니스 로직 수행

## 13. Repository와 DAO

Repository 또는 DAO는 데이터베이스와의 통신을 담당한다.

Service에서 비즈니스 로직을 처리하려면 데이터가 필요한 경우가 많다.

이때 데이터베이스에 접근해서 데이터를 조회하거나 저장하는 역할을 Repository 또는 DAO가 수행한다.

| 용어 | 주 사용 맥락 |
|---|---|
| Repository | JPA 기반에서 자주 사용 |
| DAO | MyBatis 기반에서 자주 사용 |

둘 다 데이터 접근 계층으로 이해할 수 있다.

## 14. DTO, VO, Entity

백엔드 프로젝트에서는 데이터를 담기 위한 객체도 자주 사용한다.

대표적인 용어는 DTO, VO, Entity이다.

| 용어 | 의미 |
|---|---|
| DTO | Data Transfer Object, 계층 간 데이터 전달 객체 |
| VO | Value Object, 값을 표현하는 객체 |
| Entity | 데이터베이스 테이블과 매핑되는 객체 |

DTO는 요청 데이터나 응답 데이터를 담는 용도로 많이 사용한다.

예를 들어 요청 데이터를 담는 `TestRequestDto`, 응답 데이터를 담는 `TestResponseDto`를 만들 수 있다.

Entity는 데이터베이스 테이블과 연결되는 객체로 볼 수 있다.

## 15. Package 구조 예시

역할별 패키지 구조는 다음과 같이 만들 수 있다.

    test
    ├── controller
    │   └── TestController.java
    ├── service
    │   └── TestService.java
    ├── repository
    │   └── TestRepository.java
    └── domain
        ├── dto
        │   ├── TestRequestDto.java
        │   └── TestResponseDto.java
        └── entity
            └── TestEntity.java

이렇게 패키지를 나누면 Class의 역할이 명확해진다.

프로젝트 규모가 커져도 파일을 찾고 관리하기 쉬워진다.

## 16. 요청 처리 흐름

Spring 기반 백엔드 프로젝트의 일반적인 요청 처리 흐름은 다음과 같다.

    Frontend
    → Controller
    → Service
    → Repository
    → Database

응답은 반대 방향으로 전달된다.

    Database
    → Repository
    → Service
    → Controller
    → Frontend

프론트엔드는 직접 데이터베이스에 접근하지 않는다.

프론트엔드는 백엔드에 데이터를 요청하고, 백엔드는 필요한 로직과 데이터베이스 처리를 수행한 뒤 JSON 형식으로 응답한다.

## 17. Class 간 의존 관계

계층 구조에서는 Class 간 의존 관계가 생긴다.

예를 들어 Controller는 Service를 필요로 한다.

Service는 Repository를 필요로 한다.

이 관계는 다음과 같이 표현할 수 있다.

    Controller
    → Service 의존

    Service
    → Repository 의존

    Repository
    → Database 접근

강의에서는 의존 관계를 한 Class가 다른 Class를 멤버 변수로 가지고 사용하는 구조로 설명했다.

예를 들어 Controller 내부에 Service 타입 변수를 선언하고, Service Instance를 생성해서 사용할 수 있다.

## 18. 의존 관계 예시

예시 구조는 다음과 같다.

    public class TestController {
        private TestService testService = new TestService();
    }

    public class TestService {
        private TestRepository testRepository = new TestRepository();
    }

위 코드에서 `TestController`는 `TestService`에 의존한다.

`TestService`는 `TestRepository`에 의존한다.

이 구조를 통해 Controller는 요청 흐름을 담당하고, Service는 비즈니스 로직을 담당하며, Repository는 데이터 접근을 담당한다.

## 19. 역할 분리의 이유

Class를 역할별로 나누면 코드 관리가 쉬워진다.

하나의 Class가 모든 기능을 담당하면 코드가 복잡해지고 수정하기 어려워진다.

반면 역할별로 Class를 나누면 각 Class가 자신의 책임에 집중할 수 있다.

예를 들어 다음과 같이 책임을 나눌 수 있다.

| Class | 책임 |
|---|---|
| Controller | 요청과 응답 흐름 |
| Service | 핵심 비즈니스 로직 |
| Repository | 데이터베이스 접근 |
| DTO | 데이터 전달 |
| Entity | DB 테이블 매핑 |

이렇게 나누면 유지보수와 확장이 쉬워진다.

## 20. Cohesion

Cohesion은 응집도를 의미한다.

응집도는 하나의 Class나 모듈이 하나의 역할에 얼마나 집중하고 있는지를 나타낸다.

응집도가 높다는 것은 Class가 자신의 책임을 명확하게 가지고 있다는 의미이다.

좋은 설계에서는 하나의 Class가 너무 많은 역할을 담당하지 않도록 한다.

    높은 응집도
    → 하나의 Class가 하나의 명확한 책임에 집중

## 21. Coupling

Coupling은 결합도를 의미한다.

결합도는 Class나 모듈이 서로 얼마나 강하게 연결되어 있는지를 나타낸다.

결합도가 너무 높으면 하나의 Class가 변경될 때 다른 Class까지 영향을 많이 받을 수 있다.

좋은 설계에서는 필요한 관계는 유지하되, 너무 강하게 묶이지 않도록 한다.

    낮은 결합도
    → Class 간 변경 영향 최소화

## 22. 좋은 설계 방향

소프트웨어 설계에서는 보통 높은 응집도와 낮은 결합도를 지향한다.

정리하면 다음과 같다.

| 개념 | 의미 | 좋은 방향 |
|---|---|---|
| Cohesion | 하나의 Class가 자기 역할에 집중하는 정도 | 높을수록 좋음 |
| Coupling | Class끼리 강하게 연결된 정도 | 낮을수록 좋음 |

즉, 각 Class는 자신의 역할에 집중하고, 다른 Class와는 필요한 만큼만 연결되는 구조가 좋다.

## 23. 정리

이번 학습에서는 Class와 Instance의 관계를 복습하고, Java 프로젝트의 패키지 구조와 백엔드 계층 구조를 정리했다.

핵심 개념은 다음과 같다.

- Class는 Instance를 만들기 위한 템플릿이다.
- Instance는 Class를 기반으로 메모리에 생성된 실제 객체이다.
- Instance 생성에는 `new` 키워드를 사용한다.
- Class 타입 변수는 참조 타입 변수이다.
- 참조 타입 변수는 객체의 주소 값을 저장한다.
- dot operator를 사용해 Instance의 변수와 메서드에 접근한다.
- 여러 Class는 서로 의존 관계를 가지며 함께 동작한다.
- Package는 Java Class 파일을 역할별로 관리하기 위한 구조이다.
- 다른 Package의 Class를 사용하려면 `import`가 필요하다.
- Spring 기반 프로젝트는 Controller, Service, Repository 계층으로 나눌 수 있다.
- Controller는 요청을 받고 흐름을 제어한다.
- Service는 비즈니스 로직을 처리한다.
- Repository 또는 DAO는 데이터베이스 접근을 담당한다.
- DTO는 계층 간 데이터 전달에 사용된다.
- Entity는 데이터베이스 테이블과 매핑되는 객체이다.
- 역할별 패키지 구조를 사용하면 프로젝트 관리가 쉬워진다.
- 좋은 설계는 높은 응집도와 낮은 결합도를 지향한다.