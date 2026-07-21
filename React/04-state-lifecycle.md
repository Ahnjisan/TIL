# React State와 생명주기 기본 흐름

## 1. State란?

State는 Component 내부에서 관리되는 상태 값이다.

React 화면은 사용자의 입력이나 이벤트에 따라 계속 바뀔 수 있다.

예를 들어 로그인 화면에서는 다음 값들이 상태가 될 수 있다.

    userId
    password
    error

사용자가 아이디를 입력하면 `userId` 상태가 바뀐다.

비밀번호를 입력하면 `password` 상태가 바뀐다.

입력값이 비어 있거나 로그인에 실패하면 `error` 상태가 바뀐다.

## 2. useState

React에서 State를 관리할 때는 `useState` Hook을 사용할 수 있다.

기본 형식은 다음과 같다.

    const [state, setState] = useState(초기값);

예시는 다음과 같다.

    const [userId, setUserId] = useState("");
    const [password, setPassword] = useState("");
    const [error, setError] = useState("");

`userId`는 현재 상태 값이다.

`setUserId`는 상태 값을 변경하는 함수이다.

`useState("")`는 초기값을 빈 문자열로 설정한다는 의미이다.

## 3. State가 필요한 이유

React에서는 화면에 영향을 주는 값을 일반 변수로만 관리하지 않는다.

일반 변수는 값이 바뀌어도 React가 화면을 다시 그려야 한다는 사실을 알기 어렵다.

반면 State는 값이 변경되면 React가 이를 감지하고 화면을 다시 렌더링할 수 있다.

흐름은 다음과 같다.

    사용자 입력
    → State 변경
    → React가 변경 감지
    → Component 다시 Rendering
    → 변경된 값이 화면에 반영

즉, 화면과 연결되는 값은 State로 관리하는 것이 중요하다.

## 4. input과 State 연결

로그인 화면에서 input 값은 State와 연결할 수 있다.

예시는 다음과 같다.

    <input
        type="text"
        value={userId}
        onChange={(event) => setUserId(event.target.value)}
    />

사용자가 input에 값을 입력하면 `onChange` 이벤트가 발생한다.

이때 `event.target.value`를 통해 입력된 값을 가져오고, `setUserId`를 이용해 상태를 변경한다.

## 5. 양방향 데이터 관리

React에서는 input 값과 State를 연결해 양방향처럼 데이터를 관리할 수 있다.

흐름은 다음과 같다.

    State 값
    → input의 value로 표시

    사용자 입력
    → onChange 이벤트 발생
    → State 변경

즉, 화면의 입력값과 Component 내부의 State가 연결된다.

이 구조를 이용하면 사용자가 입력한 값을 JavaScript 로직에서 쉽게 사용할 수 있다.

## 6. Event와 State

State는 이벤트와 함께 사용되는 경우가 많다.

예를 들어 로그인 버튼을 누르면 `handleSubmit` 함수가 실행된다.

이 함수 안에서 현재 State 값을 확인할 수 있다.

    const handleSubmit = (event) => {
        event.preventDefault();

        console.log(userId);
        console.log(password);
    };

사용자가 입력한 아이디와 비밀번호는 State에 저장되어 있기 때문에, 이벤트 핸들러에서 해당 값을 사용할 수 있다.

## 7. Validation과 State

Validation은 사용자 입력값을 검증하는 과정이다.

로그인 화면에서는 아이디와 비밀번호가 모두 입력되었는지 확인할 수 있다.

예시는 다음과 같다.

    if (!userId || !password) {
        setError("아이디와 비밀번호를 모두 입력해 주세요.");
        return;
    }

입력값이 비어 있다면 `setError`를 이용해 에러 메시지를 상태로 저장한다.

에러 메시지 State가 변경되면 화면에 에러 메시지가 표시된다.

## 8. 에러 메시지 Rendering

에러 메시지는 State에 따라 조건부로 렌더링할 수 있다.

예시는 다음과 같다.

    {error && <p className="error-message">{error}</p>}

이 코드는 `error` 값이 존재할 때만 에러 메시지를 화면에 보여준다.

즉, State 값에 따라 화면에 보이는 내용이 달라진다.

## 9. 임시 로그인 검증

백엔드가 아직 없는 상태에서는 프론트엔드에서 임시로 로그인 검증을 할 수 있다.

예를 들어 다음과 같은 조건을 사용할 수 있다.

    userId === "admin"
    password === "1234"

아이디가 `admin`이고 비밀번호가 `1234`이면 로그인 성공으로 처리한다.

그렇지 않으면 에러 메시지를 출력한다.

이 방식은 실제 로그인 로직이 아니라 백엔드 연동 전 화면 흐름을 테스트하기 위한 임시 검증이다.

## 10. CSS와 State 결과 표시

State에 따라 화면에 표시되는 메시지가 달라질 수 있다.

에러 메시지를 보기 좋게 표시하기 위해 CSS를 적용할 수 있다.

예를 들어 `error-message` class를 만들고 색상이나 여백을 지정할 수 있다.

    .error-message {
        color: red;
        margin-top: 10px;
    }

React에서는 JSX에서 `className="error-message"`를 사용해 이 스타일을 적용한다.

## 11. Component 생명주기란?

Component 생명주기는 Component가 만들어지고, 화면에 표시되고, 변경되고, 사라지는 흐름을 의미한다.

기본적으로 다음과 같은 흐름으로 이해할 수 있다.

    Mount
    → Component가 처음 화면에 나타남

    Update
    → State나 Props가 변경되어 화면이 다시 렌더링됨

    Unmount
    → Component가 화면에서 사라짐

이번 강의에서는 생명주기 Hook을 깊게 다루기보다는, State 변경에 따라 Component가 다시 Rendering된다는 흐름을 중심으로 이해하면 된다.

## 12. State 변경과 Update

React에서 State가 변경되면 Component는 다시 렌더링된다.

예를 들어 사용자가 input에 값을 입력하면 `setUserId`가 실행된다.

그러면 `userId` State가 변경되고, React는 화면을 다시 계산한다.

흐름은 다음과 같다.

    사용자가 값 입력
    → setUserId 실행
    → State 변경
    → Component Update
    → 화면 다시 Rendering

이것이 React에서 State와 화면이 연결되는 핵심 흐름이다.

## 13. Axios 설치

백엔드와 통신하기 위해 Axios를 사용할 수 있다.

Axios는 HTTP 요청과 응답을 쉽게 처리할 수 있도록 도와주는 라이브러리이다.

설치 명령어는 다음과 같다.

    npm install axios

설치 후 Component 파일에서 import할 수 있다.

    import axios from "axios";

## 14. Axios 통신 구조

로그인 요청은 보통 POST 방식으로 처리한다.

예시는 다음과 같다.

    const response = await axios.post("/api/login", {
        userId: userId,
        password: password
    });

이 코드는 백엔드 로그인 API로 아이디와 비밀번호를 JSON 형식으로 전달하는 구조이다.

백엔드가 준비되어 있어야 실제 통신을 테스트할 수 있다.

## 15. async와 await

Axios 통신은 비동기 방식으로 처리된다.

비동기 요청은 응답이 언제 올지 정확히 알 수 없기 때문에 코드 실행 순서를 관리해야 한다.

이때 `async`와 `await`를 사용할 수 있다.

    const handleSubmit = async (event) => {
        event.preventDefault();

        const response = await axios.post("/api/login", {
            userId,
            password
        });
    };

`async`는 비동기 함수를 선언하는 키워드이다.

`await`는 비동기 요청의 결과가 올 때까지 기다리는 역할을 한다.

## 16. Token 저장

실제 로그인 API에서는 로그인 성공 시 서버가 token을 응답할 수 있다.

프론트엔드는 이 token을 받아 저장할 수 있다.

예시는 다음과 같다.

    const token = response.data.token;
    localStorage.setItem("token", token);

`localStorage`는 브라우저에 데이터를 저장할 수 있는 공간이다.

token은 이후 인증이 필요한 API 요청에서 사용할 수 있다.

다만 실제 서비스에서는 token 저장 방식과 보안 문제도 함께 고려해야 한다.

## 17. React Router DOM 설치

Component 간 이동을 구현하려면 React Router DOM을 사용할 수 있다.

설치 명령어는 다음과 같다.

    npm install react-router-dom

React Router DOM을 사용하면 URL 경로에 따라 다른 Component를 보여줄 수 있다.

예를 들어 `/` 경로에서는 Login Component를 보여주고, `/welcome` 경로에서는 Welcome Component를 보여줄 수 있다.

## 18. App.js에서 Router 설정

라우터 설정은 보통 `App.js`에서 구성할 수 있다.

필요한 항목은 다음과 같다.

    BrowserRouter
    Routes
    Route

각 Route는 특정 경로와 Component를 연결한다.

예시는 다음과 같다.

    <Route path="/" element={<Login />} />
    <Route path="/welcome" element={<Welcome />} />

이 설정을 통해 경로에 따라 렌더링되는 Component가 달라진다.

## 19. index.js와 App.js

라우터를 사용하면 `index.js`에서는 App Component를 렌더링하고, App Component 내부에서 라우터 설정을 관리한다.

흐름은 다음과 같다.

    index.html
    → root 영역 제공

    index.js
    → App Component 렌더링

    App.js
    → Router 설정

    Route
    → 경로에 맞는 Component 렌더링

즉, App Component는 화면 자체라기보다 전체 라우팅 구조를 관리하는 Root Component 역할을 할 수 있다.

## 20. 정리

이번 학습에서는 React의 State와 State 변경에 따른 Rendering 흐름, Axios 통신 준비, Router 설정 흐름을 정리했다.

핵심 개념은 다음과 같다.

- State는 Component 내부에서 관리되는 상태 값이다.
- React에서는 `useState` Hook으로 State를 관리한다.
- `useState`는 현재 값과 값을 변경하는 함수를 반환한다.
- input 값은 `value`와 `onChange`를 이용해 State와 연결할 수 있다.
- State가 변경되면 Component가 다시 Rendering된다.
- Validation은 사용자 입력값을 검증하는 과정이다.
- 에러 메시지도 State로 관리할 수 있다.
- Component 생명주기는 Mount, Update, Unmount 흐름으로 이해할 수 있다.
- 이번 단계에서는 State 변경에 따른 Update와 Rendering 흐름이 중요하다.
- Axios는 HTTP 통신을 도와주는 라이브러리이다.
- Axios는 `npm install axios`로 설치할 수 있다.
- 비동기 통신에는 `async`와 `await`를 사용할 수 있다.
- 로그인 성공 시 token을 받아 localStorage에 저장할 수 있다.
- Component 간 이동에는 React Router DOM을 사용할 수 있다.
- `BrowserRouter`, `Routes`, `Route`를 이용해 경로와 Component를 연결한다.