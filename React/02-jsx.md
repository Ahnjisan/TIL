# React JSX와 프로젝트 구조

## 1. React 프로젝트 생성 복습

React 프로젝트는 Node.js 기반 환경에서 생성한다.

강의에서는 CRA 방식으로 프로젝트를 생성했다.

CRA는 Create React App의 약자이다.

프로젝트 생성 명령어는 다음과 같다.

    npx create-react-app react_project

이 명령어를 실행하면 `react_project`라는 이름의 React 프로젝트가 생성된다.

생성된 프로젝트는 VS Code에서 열어 구조를 확인할 수 있다.

## 2. React 프로젝트 기본 구조

React 프로젝트를 생성하면 여러 폴더와 파일이 만들어진다.

대표적인 구조는 다음과 같다.

    react_project
    ├── node_modules
    ├── public
    ├── src
    └── package.json

각 항목의 역할은 다음과 같다.

| 항목 | 역할 |
|---|---|
| node_modules | 설치된 라이브러리와 패키지 저장 |
| public | 정적 파일 저장 |
| src | 실제 React 코드 작성 |
| package.json | 프로젝트 정보와 실행 스크립트 관리 |

React 개발에서 주로 수정하는 폴더는 `src`이다.

## 3. public 폴더

`public` 폴더는 정적 파일을 저장하는 공간이다.

React 프로젝트의 기본 HTML 파일인 `index.html`도 이 폴더 안에 있다.

React는 SPA 방식으로 동작하기 때문에 기본 HTML 페이지는 하나이다.

즉, 여러 HTML 페이지를 직접 만드는 방식이 아니라 하나의 HTML 파일을 기준으로 JavaScript가 화면을 구성한다.

## 4. public/index.html

`public/index.html`은 React 애플리케이션의 기본 HTML 파일이다.

이 파일 안에는 다음과 같은 root 영역이 존재한다.

    <div id="root"></div>

이 root 영역은 React Component가 렌더링될 위치이다.

처음에는 HTML 안에 실제 화면 내용이 거의 없지만, React가 JavaScript를 통해 이 root 영역에 화면을 채워 넣는다.

정리하면 다음과 같다.

    index.html
    → root 영역 제공
    → React가 이 영역에 Component 결과를 Rendering

## 5. src 폴더

`src` 폴더는 실제 React 코드를 작성하는 공간이다.

기본 프로젝트에서는 대표적으로 다음 파일을 확인할 수 있다.

    index.js
    App.js
    App.css

각 파일의 역할은 다음과 같다.

| 파일 | 역할 |
|---|---|
| index.js | React 애플리케이션의 시작 지점 |
| App.js | 기본 App Component 정의 |
| App.css | App Component 스타일 정의 |

React 개발에서는 보통 `src` 폴더 안에 Component 파일을 추가하며 화면을 구성한다.

## 6. src/index.js

`src/index.js`는 React 애플리케이션의 시작 지점이다.

이 파일은 `public/index.html`에 있는 root 영역을 찾아 React Component를 렌더링한다.

강의에서는 `document.getElementById("root")`를 통해 HTML의 root 영역에 접근하는 구조를 확인했다.

흐름은 다음과 같다.

    index.html의 root 영역 확인
    → index.js에서 root에 접근
    → App Component 등록
    → App Component 결과가 브라우저에 렌더링

즉, `index.js`는 HTML과 React Component를 연결하는 역할을 한다.

## 7. src/App.js

`App.js`는 React Component 파일이다.

React 프로젝트를 처음 생성하면 기본적으로 App Component가 만들어져 있다.

`App.js` 안에는 함수 형태의 Component가 작성되어 있고, 그 함수 내부에서 HTML처럼 보이는 구조를 반환한다.

이 구조가 JSX이다.

`App.js`에서 만든 App Component는 외부에서 사용할 수 있도록 export된다.

그리고 `index.js`에서 App Component를 import하여 root 영역에 렌더링한다.

## 8. JSX란?

JSX는 JavaScript 안에서 HTML처럼 보이는 UI 구조를 작성할 수 있게 해주는 문법이다.

React Component는 JSX를 반환하여 화면에 표시할 Element를 만든다.

예를 들어 다음과 같은 형태를 사용할 수 있다.

    function App() {
        return (
            <div>
                <h1>Hello React</h1>
                <p>React JSX Example</p>
            </div>
        );
    }

겉으로는 HTML처럼 보이지만, 실제로는 JavaScript 안에서 사용되는 JSX 문법이다.

## 9. JSX를 사용하는 이유

JSX를 사용하면 UI 구조를 직관적으로 작성할 수 있다.

HTML 구조와 JavaScript 로직을 Component 단위로 함께 관리할 수 있기 때문에 화면을 구성하는 코드를 이해하기 쉽다.

React에서는 Component가 화면을 만드는 단위이기 때문에, JSX를 사용해 각 Component가 어떤 화면 구조를 반환하는지 표현한다.

정리하면 다음과 같다.

    Component
    → JSX 반환
    → Element 생성
    → Browser에 Rendering

## 10. JSX는 하나의 부모 요소를 반환해야 한다

JSX에서는 여러 요소를 반환할 때 하나의 부모 요소로 감싸야 한다.

잘못된 예시는 다음과 같다.

    function App() {
        return (
            <h1>Hello</h1>
            <p>React</p>
        );
    }

위 코드는 두 개의 요소가 나란히 반환되고 있어 오류가 발생할 수 있다.

올바른 예시는 다음과 같다.

    function App() {
        return (
            <div>
                <h1>Hello</h1>
                <p>React</p>
            </div>
        );
    }

여러 요소를 반환할 때는 `div` 또는 Fragment로 감싸야 한다.

## 11. JSX에서 JavaScript 사용

JSX 안에서 JavaScript 값을 사용하려면 중괄호를 사용한다.

예시는 다음과 같다.

    function App() {
        const name = "React";

        return (
            <div>
                <h1>Hello {name}</h1>
            </div>
        );
    }

`{name}` 부분에는 JavaScript 변수 값이 들어간다.

즉, JSX 안에서 JavaScript 표현식을 사용하려면 `{}`를 사용한다.

## 12. JSX와 className

HTML에서는 CSS 클래스를 적용할 때 `class` 속성을 사용한다.

하지만 JSX에서는 `class` 대신 `className`을 사용한다.

예시는 다음과 같다.

    function App() {
        return (
            <div className="container">
                <h1>Hello React</h1>
            </div>
        );
    }

JavaScript에서 `class`는 예약어이기 때문에 JSX에서는 `className`을 사용한다.

## 13. JSX와 style

JSX에서 inline style을 작성할 때는 객체 형태를 사용한다.

예시는 다음과 같다.

    function App() {
        return (
            <h1 style={{ color: "blue", fontSize: "20px" }}>
                Hello React
            </h1>
        );
    }

일반 HTML의 style 문자열과 다르게 JSX에서는 JavaScript 객체 형태로 작성한다.

속성 이름도 `font-size`가 아니라 `fontSize`처럼 camelCase로 작성한다.

## 14. import와 export

React에서는 Component를 파일 단위로 나누어 관리한다.

다른 파일에서 만든 Component를 사용하려면 import와 export가 필요하다.

`export`는 현재 파일의 Component를 외부에서 사용할 수 있도록 내보내는 역할이다.

`import`는 다른 파일에서 내보낸 Component를 가져오는 역할이다.

예시는 다음과 같다.

    export default App;

    import App from './App';

`App.js`에서 App Component를 export하고, `index.js`에서 App Component를 import하여 사용할 수 있다.

## 15. Component 렌더링 흐름

React 프로젝트의 기본 렌더링 흐름은 다음과 같다.

    public/index.html
    → <div id="root"></div> 제공

    src/index.js
    → root 영역을 찾음
    → App Component를 등록

    src/App.js
    → App Component 정의
    → JSX 반환

    Browser
    → App Component가 만든 Element를 화면에 Rendering

즉, React는 HTML 페이지 하나를 기준으로 하고, JavaScript Component를 이용해 root 영역에 화면을 그려 넣는다.

## 16. Virtual DOM

React는 Virtual DOM이라는 개념을 사용한다.

Virtual DOM은 실제 DOM을 바로 조작하기 전에 React가 내부적으로 관리하는 가상의 DOM 구조로 이해할 수 있다.

`index.js`에서는 root 영역을 기준으로 React의 렌더링 구조를 만들고, App Component를 등록한다.

이후 React는 Component의 결과를 바탕으로 화면을 갱신한다.

정리하면 다음과 같다.

    Component 변경
    → Virtual DOM에서 변경 내용 계산
    → 필요한 부분만 실제 화면에 반영

처음 학습 단계에서는 Virtual DOM을 완벽히 이해하려고 하기보다, React가 HTML root 영역에 Component 결과를 렌더링한다는 흐름을 먼저 이해하는 것이 중요하다.

## 17. npm start

React 개발 서버를 실행할 때는 다음 명령어를 사용한다.

    npm start

이 명령어를 실행하면 React 개발 서버가 실행되고, 기본 브라우저에서 React 페이지가 열린다.

기본 주소는 다음과 같다.

    http://localhost:3000

만약 `npm` 명령어가 인식되지 않는다면 VS Code를 껐다가 다시 실행해 볼 수 있다.

Node.js 설치 후 환경 변수 반영이 되지 않은 상태일 수 있기 때문이다.

## 18. React 개발 서버

React 프로젝트는 내부적으로 개발 서버를 제공한다.

`npm start`를 실행하면 개발 서버가 실행되고, 브라우저에서 React 화면을 확인할 수 있다.

이 서버는 실제 배포용 서버라기보다 개발 중 화면을 확인하기 위한 개발 서버이다.

개발 중 코드를 수정하면 브라우저에 변경 사항이 반영될 수 있다.

## 19. JSX 학습 시 주의할 점

JSX는 HTML과 비슷하지만 완전히 같은 문법은 아니다.

주의할 점은 다음과 같다.

- 여러 요소는 하나의 부모 요소로 감싸야 한다.
- JavaScript 값을 사용할 때는 `{}`를 사용한다.
- CSS class는 `className`으로 작성한다.
- inline style은 객체 형태로 작성한다.
- Component 이름은 보통 대문자로 시작한다.
- JSX는 Component가 Element를 반환하기 위한 문법이다.

## 20. 정리

이번 학습에서는 React 프로젝트 구조와 JSX의 기본 개념을 정리했다.

핵심 개념은 다음과 같다.

- React 프로젝트는 Node.js 기반 환경에서 생성한다.
- CRA를 사용하면 React 프로젝트 기본 구조를 자동으로 만들 수 있다.
- `public/index.html`은 React의 기본 HTML 파일이다.
- React는 SPA 방식이므로 기본 HTML 페이지는 하나이다.
- `index.html`의 `<div id="root"></div>`는 React Component가 렌더링될 위치이다.
- `src/index.js`는 root 영역과 React Component를 연결한다.
- `src/App.js`는 기본 App Component를 정의한다.
- App Component는 JSX를 반환한다.
- JSX는 JavaScript 안에서 HTML처럼 UI 구조를 작성하는 문법이다.
- JSX는 하나의 부모 요소를 반환해야 한다.
- JSX 안에서 JavaScript 값을 사용할 때는 `{}`를 사용한다.
- JSX에서는 `class` 대신 `className`을 사용한다.
- Component는 export하고, 다른 파일에서는 import해서 사용할 수 있다.
- React는 Component가 만든 Element를 root 영역에 렌더링한다.
- `npm start`로 React 개발 서버를 실행할 수 있다.
- React 개발 서버는 기본적으로 `localhost:3000`에서 실행된다.