# React Component와 Props

## 1. Component란?

React는 Component 기반으로 화면을 구성한다.

Component는 화면을 구성하는 독립적인 UI 조각이다.

기존 HTML, CSS, JavaScript 방식에서는 하나의 HTML 파일 안에 화면 구조를 직접 작성했다면, React에서는 화면을 여러 Component로 나누어 관리한다.

예를 들어 로그인 화면은 하나의 `Login` Component로 만들 수 있다.

    Login Component
    → 아이디 입력 영역
    → 비밀번호 입력 영역
    → 로그인 버튼
    → 에러 메시지 영역

이처럼 Component는 하나의 화면 또는 화면 일부를 담당하는 단위이다.

## 2. JSX 기반 Component

React Component는 JavaScript 함수로 만들 수 있다.

그리고 함수 내부의 `return` 영역에서 HTML처럼 보이는 JSX 문법을 작성한다.

기본 구조는 다음과 같다.

    const Login = () => {
        return (
            <div>
                <h2>Login</h2>
            </div>
        );
    };

    export default Login;

JSX는 JavaScript 안에서 HTML 구조를 작성할 수 있게 해주는 문법이다.

즉, React Component는 JavaScript 함수이지만, 그 안에서 JSX를 이용해 화면 구조를 반환한다.

## 3. Component 파일 생성

강의에서는 `src` 폴더 아래에 Component를 관리하기 위한 폴더 구조를 만들었다.

구조는 다음과 같다.

    src
    └── components
        └── page
            └── Login.jsx

`components` 폴더는 Component들을 관리하는 폴더이다.

`page` 폴더는 페이지 역할을 하는 Component를 모아두는 폴더이다.

`Login.jsx`는 로그인 화면을 담당하는 Component이다.

## 4. Component 이름 규칙

React Component 이름은 보통 대문자로 시작한다.

파일 이름이 `Login.jsx`라면 Component 이름도 `Login`으로 맞추는 것이 좋다.

    Login.jsx
    → Login Component

이는 JavaScript 함수 이름이면서 동시에 React Component 이름이 된다.

소문자로 시작하면 일반 HTML 태그처럼 인식될 수 있기 때문에 Component 이름은 대문자로 시작하는 것이 일반적이다.

## 5. import와 export

React에서는 Component를 파일 단위로 나누어 관리한다.

다른 파일에서 Component를 사용하려면 `export`와 `import`가 필요하다.

`export default`는 현재 파일의 Component를 외부에서 사용할 수 있도록 내보내는 역할이다.

    export default Login;

다른 파일에서는 다음과 같이 가져올 수 있다.

    import Login from "./components/page/Login";

정리하면 다음과 같다.

| 키워드 | 역할 |
|---|---|
| export | 현재 파일의 값을 외부로 내보냄 |
| import | 다른 파일에서 내보낸 값을 가져옴 |

## 6. CSS 파일 적용

React Component에서도 CSS 파일을 import해서 사용할 수 있다.

예를 들어 `Login.jsx`에서 `Login.css`를 적용하려면 다음과 같이 작성할 수 있다.

    import "../css/Login.css";

중요한 점은 파일 경로를 정확히 작성해야 한다는 것이다.

React 프로젝트에서는 Component 파일과 CSS 파일의 위치가 다를 수 있기 때문에 상대 경로를 잘 확인해야 한다.

## 7. className

일반 HTML에서는 CSS class를 적용할 때 `class` 속성을 사용한다.

하지만 React JSX에서는 `class` 대신 `className`을 사용한다.

    <div className="login-container">
        ...
    </div>

CSS 파일에서는 다음과 같이 class 선택자를 사용할 수 있다.

    .login-container {
        ...
    }

JSX에서 `class`를 사용하지 않는 이유는 JavaScript에서 `class`가 이미 다른 의미를 가진 예약어이기 때문이다.

정리하면 다음과 같다.

| 환경 | CSS class 적용 방식 |
|---|---|
| HTML | class |
| React JSX | className |

## 8. Login Component 구조

로그인 화면은 다음과 같은 구조로 만들 수 있다.

    div
    → form
    → h2
    → 아이디 input
    → 비밀번호 input
    → button
    → 에러 메시지 영역

예시 구조는 다음과 같다.

    const Login = () => {
        return (
            <div className="login-container">
                <form className="login-box">
                    <h2>Login</h2>

                    <div className="input-group">
                        <label>아이디</label>
                        <input type="text" />
                    </div>

                    <div className="input-group">
                        <label>비밀번호</label>
                        <input type="password" />
                    </div>

                    <button type="submit">로그인</button>
                </form>
            </div>
        );
    };

## 9. Props란?

Props는 Component에 전달되는 속성 값이다.

Props는 Properties의 줄임말이다.

Component는 Props를 전달받고, 그 값을 이용해 화면을 구성할 수 있다.

예를 들어 Card Component가 있다고 하면 다음과 같은 값을 Props로 전달할 수 있다.

    image
    title
    distance
    price

같은 Card Component라도 전달되는 Props 값이 다르면 서로 다른 화면 결과를 만들 수 있다.

즉, Props는 Component를 재사용 가능하게 만들어주는 중요한 개념이다.

## 10. Component와 Element의 관계

Component는 화면을 만들기 위한 틀이다.

Element는 Component로부터 만들어져 실제 브라우저에 렌더링되는 결과물이다.

흐름은 다음과 같다.

    Component
    → Props 전달
    → Element 생성
    → Browser에 Rendering

Component는 직접 브라우저에 표시되는 것이 아니라, Component가 반환한 Element가 브라우저에 표시된다.

## 11. Event 연결

React에서는 JSX 태그에 이벤트를 연결할 수 있다.

예를 들어 form 제출 이벤트는 `onSubmit`으로 연결한다.

    <form onSubmit={handleSubmit}>
        ...
    </form>

input 값 변경 이벤트는 `onChange`로 연결할 수 있다.

    <input onChange={handleUserIdChange} />

버튼 클릭, input 변경, form 제출 같은 사용자 행동은 이벤트로 처리한다.

## 12. Event Handler

Event Handler는 이벤트가 발생했을 때 실행되는 함수이다.

예를 들어 로그인 버튼을 눌렀을 때 실행할 함수를 `handleSubmit`으로 만들 수 있다.

    const handleSubmit = (event) => {
        event.preventDefault();
        console.log("로그인 버튼 클릭");
    };

이 함수는 사용자가 form을 제출했을 때 실행된다.

## 13. preventDefault

HTML form은 기본적으로 submit 이벤트가 발생하면 페이지를 새로고침하려는 동작을 가진다.

React에서는 이 기본 동작을 막고, 직접 원하는 로직을 실행해야 한다.

이때 사용하는 것이 `event.preventDefault()`이다.

    const handleSubmit = (event) => {
        event.preventDefault();
    };

이 코드를 작성하면 form 제출 시 페이지가 새로고침되지 않는다.

## 14. useState

React에서 입력값처럼 변경되는 데이터를 관리할 때는 `useState`를 사용할 수 있다.

`useState`는 React Hook 중 하나이다.

아이디, 비밀번호, 에러 메시지 같은 값은 상태로 관리할 수 있다.

    const [userId, setUserId] = useState("");
    const [password, setPassword] = useState("");
    const [error, setError] = useState("");

각 상태는 현재 값과 값을 변경하는 함수로 구성된다.

| 값 | 의미 |
|---|---|
| userId | 현재 아이디 값 |
| setUserId | 아이디 값을 변경하는 함수 |
| password | 현재 비밀번호 값 |
| setPassword | 비밀번호 값을 변경하는 함수 |
| error | 현재 에러 메시지 |
| setError | 에러 메시지를 변경하는 함수 |

## 15. input과 State 연결

사용자가 input에 값을 입력하면 `onChange` 이벤트가 발생한다.

이 이벤트에서 상태 변경 함수를 호출하면 input 값과 React state를 연결할 수 있다.

    <input
        type="text"
        value={userId}
        onChange={(event) => setUserId(event.target.value)}
    />

흐름은 다음과 같다.

    사용자가 input에 입력
    → onChange 이벤트 발생
    → setUserId 실행
    → userId 상태 변경
    → 화면에 반영

이렇게 input 값과 state를 연결하면 사용자가 입력한 값을 React Component 내부에서 관리할 수 있다.

## 16. index.js에서 Component 렌더링

만든 Component를 브라우저에 보여주려면 React의 렌더링 흐름에 등록해야 한다.

강의에서는 `index.js`에서 기존 App Component 대신 Login Component를 가져와 렌더링하는 방식도 확인했다.

    import Login from "./components/page/Login";

    root.render(
        <Login />
    );

다만 라우터를 사용할 경우에는 `index.js`에서 App Component를 렌더링하고, App Component 안에서 Route 설정을 관리하는 방식이 더 적절하다.

## 17. Backend 통신의 시작점

로그인 화면에서 사용자가 아이디와 비밀번호를 입력하고 로그인 버튼을 누르면, 실제 서비스에서는 이 데이터가 백엔드로 전달된다.

프론트엔드는 입력값을 JSON 형식으로 백엔드 로그인 API에 전달할 수 있다.

이때 사용할 수 있는 도구는 다음과 같다.

| 도구 | 설명 |
|---|---|
| Axios | HTTP 요청과 응답을 쉽게 처리하는 라이브러리 |
| Fetch API | 브라우저에서 기본 제공하는 HTTP 통신 API |

React 화면은 사용자 입력을 받고, 백엔드는 해당 데이터를 검증한 뒤 결과를 응답한다.

## 18. 정리

이번 학습에서는 React Component와 Props, JSX 기반 화면 구성, 이벤트 연결 흐름을 정리했다.

핵심 개념은 다음과 같다.

- React는 Component 기반으로 화면을 구성한다.
- Component는 화면을 구성하는 독립적인 UI 조각이다.
- Component 파일은 `.jsx` 확장자로 만들 수 있다.
- JSX는 JavaScript 안에서 HTML처럼 화면 구조를 작성하는 문법이다.
- Component 이름은 보통 대문자로 시작한다.
- Component는 `export default`로 외부에 내보낼 수 있다.
- 다른 파일에서는 `import`를 이용해 Component를 가져온다.
- CSS 파일도 Component에서 import해서 사용할 수 있다.
- JSX에서는 `class` 대신 `className`을 사용한다.
- Props는 Component에 전달되는 속성 값이다.
- Component는 Props를 바탕으로 Element를 생성한다.
- Event Handler는 이벤트 발생 시 실행되는 함수이다.
- form 제출 이벤트는 `onSubmit`으로 처리할 수 있다.
- input 값 변경 이벤트는 `onChange`로 처리할 수 있다.
- form 기본 submit 동작은 `event.preventDefault()`로 막을 수 있다.
- `useState`는 Component의 상태를 관리하는 Hook이다.