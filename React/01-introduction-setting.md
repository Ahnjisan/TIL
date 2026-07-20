# React 소개 및 기본 개념

## 1. React란?

React는 사용자 인터페이스를 만들기 위한 JavaScript 라이브러리이다.

사용자 인터페이스는 사용자가 웹 페이지에서 직접 보고 조작하는 화면 영역을 의미한다.

기존 웹 개발에서는 HTML, CSS, JavaScript를 각각 작성해서 화면을 구성했다.

하지만 최근 프론트엔드 개발에서는 React, Vue 같은 라이브러리나 프레임워크를 사용해 화면을 구성하는 경우가 많다.

React는 그중에서도 Component 기반으로 UI를 만드는 대표적인 프론트엔드 라이브러리이다.

## 2. Library와 Framework의 차이

React는 Framework가 아니라 Library이다.

Library와 Framework의 차이는 제어권을 누가 가지고 있느냐로 이해할 수 있다.

| 구분 | 설명 |
|---|---|
| Library | 개발자가 필요한 기능을 호출해서 사용 |
| Framework | 정해진 구조 안에서 개발자가 코드를 작성 |

Library는 개발자가 주도권을 가지고 필요한 기능을 가져다 쓰는 방식이다.

Framework는 전체적인 흐름과 구조를 Framework가 정해두고, 개발자는 그 규칙 안에서 코드를 작성한다.

React는 개발자가 필요한 Component를 만들고 조합해서 화면을 구성하기 때문에 Library라고 볼 수 있다.

## 3. React의 핵심은 Component

React는 Component 기반으로 개발한다.

Component는 화면을 구성하는 독립적인 UI 조각이다.

레고 블록을 조립해서 하나의 구조물을 만들듯이, React에서는 Component를 조립해서 하나의 웹 페이지를 만든다.

예를 들어 하나의 웹 페이지는 다음과 같이 나눌 수 있다.

    Header Component
    Search Component
    Card Component
    Footer Component

각 Component는 독립적인 역할을 가지고, 여러 Component가 모여 하나의 화면을 구성한다.

## 4. Component를 사용하는 이유

Component를 사용하는 가장 큰 이유는 재사용성이다.

예를 들어 숙소 정보를 보여주는 Card Component를 만든다고 가정할 수 있다.

Card Component는 이미지, 지역명, 거리, 가격 같은 정보를 전달받아 화면에 하나의 카드 형태로 보여줄 수 있다.

이때 Component의 구조는 같지만, 전달되는 데이터가 다르면 화면에 표시되는 결과도 달라진다.

    Card Component
    → 이미지 전달
    → 지역명 전달
    → 거리 전달
    → 가격 전달
    → 숙소 카드 Element 생성

Component를 잘 만들어두면 같은 UI 구조를 여러 곳에서 재사용할 수 있다.

## 5. Component의 독립성

Component가 재사용되기 위해서는 독립적이어야 한다.

만약 어떤 Component가 특정 프로젝트의 다른 모듈에 강하게 의존하고 있다면, 다른 프로젝트에서 그대로 재사용하기 어렵다.

예를 들어 Calendar Component가 특정 Date Module에 강하게 의존하고 있는데, 다른 프로젝트에는 해당 Date Module이 없다면 Calendar Component를 사용할 수 없다.

따라서 재사용 가능한 Component를 만들기 위해서는 필요한 값은 Props로 전달받고, 특정 외부 구조에 강하게 묶이지 않도록 설계하는 것이 중요하다.

## 6. Props란?

Props는 Component에 전달되는 속성 값이다.

Props는 Properties의 줄임말이다.

Component는 Props를 전달받아 화면에 보여줄 결과를 만든다.

예를 들어 Card Component에 다음과 같은 Props를 전달할 수 있다.

    image
    title
    distance
    price

Component는 이 Props를 이용해서 실제 화면에 표시될 Element를 생성한다.

정리하면 다음과 같다.

    Props
    → Component에 전달되는 입력 값
    → Component가 화면을 만들 때 사용하는 속성

## 7. Component와 Element의 차이

React에서는 Component와 Element를 구분해야 한다.

Component는 화면을 만들기 위한 틀이다.

Element는 Component로부터 생성되어 실제 브라우저에 렌더링되는 결과물이다.

강의에서는 붕어빵 틀과 붕어빵에 비유했다.

| 개념 | 비유 | 설명 |
|---|---|---|
| Component | 붕어빵 틀 | 화면 요소를 만들기 위한 틀 |
| Props | 팥, 슈크림, 고구마 | Component에 전달되는 속성 값 |
| Element | 실제 붕어빵 | Component로부터 만들어진 결과물 |

즉, Component에 어떤 Props가 전달되느냐에 따라 만들어지는 Element가 달라진다.

## 8. Rendering이란?

Rendering은 화면에 보여주는 과정을 의미한다.

브라우저는 HTML, CSS, JavaScript를 해석해서 사용자가 볼 수 있는 화면으로 표시한다.

이 과정을 Rendering이라고 한다.

React에서는 Component가 Props를 전달받아 Element를 만들고, 그 Element가 브라우저에 표시된다.

흐름은 다음과 같다.

    Component 작성
    → Props 전달
    → Element 생성
    → Browser에 Rendering

React에서 실제 브라우저에 보이는 것은 Component 자체가 아니라 Component가 만들어낸 Element이다.

## 9. React와 SPA

React는 Single Page Application, 즉 SPA 방식의 개발에 많이 사용된다.

SPA는 하나의 HTML 페이지를 기반으로 동작하는 웹 애플리케이션이다.

전통적인 웹 방식에서는 페이지를 이동할 때마다 새로운 HTML 문서를 서버에서 받아오는 경우가 많다.

반면 SPA에서는 HTML 페이지 하나를 기준으로 JavaScript가 필요한 부분만 변경하며 화면을 구성한다.

React 프로젝트도 기본 HTML 파일 하나를 기준으로 하고, Component를 이용해 화면을 렌더링한다.

## 10. React Component는 함수로 만들 수 있다

React Component는 JavaScript 함수로 만들 수 있다.

과거에는 Class 기반 Component도 사용했지만, 현재는 Function 기반 Component를 많이 사용한다.

Function Component는 JavaScript 함수처럼 작성되지만, React에서는 UI Element를 반환하는 Component 역할을 한다.

일반 JavaScript 함수와 React Component의 차이는 다음과 같다.

| 구분 | 일반 JavaScript 함수 | React Component |
|---|---|---|
| 입력 | 매개변수 | Props |
| 처리 | 일반 로직 실행 | UI 구성 |
| 출력 | 값 반환 | Element 반환 |

React Component는 Props를 전달받고, 화면에 보여줄 Element를 반환한다.

## 11. React 개발 환경이 필요한 이유

React를 사용하려면 React 기반 개발 환경이 필요하다.

단순히 HTML 파일 하나를 만들고 브라우저에서 여는 방식이 아니라, Node.js 기반의 개발 환경에서 프로젝트를 생성하고 실행한다.

React 개발 환경을 구성하기 위해 필요한 대표적인 도구는 다음과 같다.

| 도구 | 역할 |
|---|---|
| Node.js | JavaScript 실행 환경 |
| npm | Node Package Manager, 패키지 관리 도구 |
| npx | 패키지를 실행하고 프로젝트 생성을 도와주는 도구 |
| CRA | Create React App, React 프로젝트 생성 도구 |

## 12. Node.js

Node.js는 브라우저 밖에서도 JavaScript를 실행할 수 있게 해주는 환경이다.

React 프로젝트를 생성하고 실행하기 위해서는 Node.js가 필요하다.

Node.js를 설치하면 npm도 함께 설치된다.

설치 후 다음 명령어로 버전을 확인할 수 있다.

    node --version

    npm --version

버전이 정상적으로 출력되면 Node.js와 npm이 설치된 상태이다.

## 13. npm

npm은 Node Package Manager의 약자이다.

Node.js 환경에서 필요한 패키지나 라이브러리를 설치하고 관리하는 도구이다.

React 프로젝트에는 여러 라이브러리와 의존성이 필요하다.

npm은 이러한 패키지를 설치하고 관리하는 역할을 한다.

정리하면 다음과 같다.

    npm
    → Node.js 패키지 관리 도구
    → 프로젝트 의존성 관리
    → 개발 서버 실행 명령어 관리

## 14. npx

npx는 패키지를 실행할 때 사용하는 도구이다.

React 프로젝트를 생성할 때는 다음과 같이 사용할 수 있다.

    npx create-react-app react_project

npm이 패키지를 설치하고 관리하는 도구라면, npx는 특정 패키지를 실행해서 프로젝트 생성 같은 작업을 도와주는 도구로 이해할 수 있다.

## 15. CRA

CRA는 Create React App의 약자이다.

React 프로젝트를 직접 설정하려면 여러 설정이 필요하다.

CRA를 사용하면 React 프로젝트에 필요한 기본 구조와 라이브러리를 자동으로 구성할 수 있다.

React 프로젝트 생성 명령어는 다음과 같다.

    npx create-react-app react_project

이 명령어를 실행하면 `react_project`라는 이름의 React 프로젝트가 생성된다.

## 16. Git Bash 사용

Windows 환경에서는 CMD를 사용할 수도 있지만, 강의에서는 Git Bash 사용을 권장했다.

Git Bash는 Git 설치 시 함께 사용할 수 있는 터미널 환경이다.

프로젝트 폴더에서 마우스 오른쪽 버튼을 누르고 Git Bash를 열어 명령어를 실행할 수 있다.

React 프로젝트 생성도 Git Bash에서 진행할 수 있다.

    npx create-react-app react_project

## 17. React 프로젝트 생성 흐름

React 프로젝트 생성 흐름은 다음과 같다.

    Node.js 설치
    → node, npm 버전 확인
    → Git Bash 실행
    → 프로젝트를 만들 폴더로 이동
    → npx create-react-app react_project 실행
    → 필요한 패키지 설치
    → React 프로젝트 생성 완료

설치가 정상적으로 완료되면 React 프로젝트 폴더가 생성된다.

## 18. React 프로젝트 실행

React 프로젝트를 실행하려면 프로젝트 폴더에서 다음 명령어를 사용한다.

    npm start

이 명령어를 실행하면 React 개발 서버가 실행된다.

기본적으로 브라우저에서 다음 주소로 접근할 수 있다.

    http://localhost:3000

3000번 포트는 React 개발 서버의 기본 포트이다.

## 19. 정리

이번 학습에서는 React의 기본 개념과 개발 환경 세팅 흐름을 정리했다.

핵심 개념은 다음과 같다.

- React는 사용자 인터페이스를 만들기 위한 JavaScript 라이브러리이다.
- React는 Component 기반으로 UI를 구성한다.
- Component는 화면을 구성하는 독립적인 UI 조각이다.
- Component를 잘 만들면 재사용성이 높아진다.
- Component가 재사용되려면 독립적으로 설계되어야 한다.
- Props는 Component에 전달되는 속성 값이다.
- Element는 Component로부터 만들어져 브라우저에 렌더링되는 결과물이다.
- Rendering은 화면에 보여주는 과정이다.
- React는 SPA 방식의 개발에 많이 사용된다.
- React Component는 보통 JavaScript 함수로 만든다.
- React 개발 환경을 만들기 위해 Node.js가 필요하다.
- npm은 Node.js의 패키지 관리 도구이다.
- npx는 패키지를 실행하고 프로젝트 생성을 도와준다.
- CRA는 Create React App의 약자이다.
- `npx create-react-app 프로젝트명`으로 React 프로젝트를 만들 수 있다.
- `npm start`로 React 개발 서버를 실행할 수 있다.