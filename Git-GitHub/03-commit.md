# Commit 이해하기

## 1. Commit이란?

Commit은 Git에서 변경 사항을 하나의 버전으로 기록하는 작업이다.

파일을 생성하거나 수정하거나 삭제했다고 해서 바로 Git에 버전으로 저장되는 것은 아니다.

Git에서는 변경된 파일을 먼저 Staging Area에 올리고, 그다음 Commit을 통해 하나의 버전으로 기록한다.

기본 흐름은 다음과 같다.

    파일 생성 / 수정 / 삭제
    → git status로 상태 확인
    → git add로 Staging Area에 추가
    → git commit으로 버전 기록
    → git log로 이력 확인

Commit은 특정 시점의 프로젝트 상태를 저장하는 기준점이라고 볼 수 있다.

## 2. Commit이 필요한 이유

개발을 하다 보면 코드가 계속 변경된다.

이때 Commit을 남기지 않으면 어떤 시점에 어떤 변경이 있었는지 추적하기 어렵다.

Commit을 사용하면 다음과 같은 장점이 있다.

| 장점 | 설명 |
|---|---|
| 변경 이력 기록 | 어떤 파일이 언제, 어떻게 바뀌었는지 확인 가능 |
| 이전 상태 확인 | 과거 특정 시점의 코드 상태 확인 가능 |
| 문제 원인 추적 | 오류가 발생했을 때 어떤 변경이 원인인지 파악 가능 |
| 협업 지원 | 팀원들이 각자의 작업 내용을 확인 가능 |
| 롤백 가능 | 문제가 생겼을 때 이전 상태로 되돌릴 수 있음 |

즉, Commit은 단순 저장이 아니라 프로젝트의 변경 이력을 관리하기 위한 기록이다.

## 3. Git의 파일 상태

Git은 파일의 상태를 구분해서 관리한다.

대표적인 상태는 다음과 같다.

| 상태 | 의미 |
|---|---|
| Untracked | Git이 아직 추적하지 않는 새 파일 |
| Modified | Git이 추적 중인 파일이 수정된 상태 |
| Deleted | Git이 추적 중인 파일이 삭제된 상태 |
| Staged | Commit을 위해 Staging Area에 올라간 상태 |
| Committed | 변경 사항이 Commit으로 기록된 상태 |

예를 들어 새로운 파일을 만들면 Git은 해당 파일을 바로 관리하지 않는다.

먼저 `git add`를 통해 Git이 추적할 수 있도록 Staging Area에 올려야 한다.

## 4. git status

`git status`는 현재 Git 저장소의 상태를 확인하는 명령어이다.

    git status

이 명령어를 사용하면 다음 내용을 확인할 수 있다.

- 현재 브랜치
- 변경된 파일
- 삭제된 파일
- 새로 추가된 파일
- Staging Area에 올라간 파일
- Commit할 내용이 있는지 여부

새 파일을 만들었지만 아직 Git에 추가하지 않았다면 `Untracked files`로 표시된다.

기존 파일을 수정하면 `Modified` 상태로 표시된다.

기존 파일을 삭제하면 `Deleted` 상태로 표시된다.

## 5. Staging Area

Staging Area는 Commit할 파일을 임시로 모아두는 공간이다.

강의에서는 Staging Area를 타임캡슐에 비유했다.

`git add`는 변경된 파일을 타임캡슐에 담는 과정이고, `git commit`은 그 타임캡슐을 실제 기록으로 남기는 과정이라고 볼 수 있다.

흐름은 다음과 같다.

    변경 파일
    → git add
    → Staging Area
    → git commit
    → Repository에 버전 기록

Staging Area가 있기 때문에 여러 변경 사항 중 Commit에 포함할 파일만 선택할 수 있다.

예를 들어 A 파일과 B 파일을 모두 수정했지만, A 파일만 Commit하고 싶다면 A 파일만 `git add`하면 된다.

## 6. git add

`git add`는 변경된 파일을 Staging Area에 추가하는 명령어이다.

특정 파일만 추가할 때는 다음과 같이 사용한다.

    git add 파일명

예시는 다음과 같다.

    git add tigers.yaml

현재 폴더 아래의 모든 변경 사항을 추가할 때는 다음 명령어를 사용한다.

    git add .

`git add .`은 새 파일, 수정된 파일, 삭제된 파일을 한 번에 Staging Area에 올릴 때 사용한다.

다만 실제 협업에서는 어떤 파일이 포함되는지 확인한 뒤 신중하게 사용하는 것이 좋다.

## 7. git commit

`git commit`은 Staging Area에 올라간 변경 사항을 하나의 버전으로 기록하는 명령어이다.

기본 형식은 다음과 같다.

    git commit -m "커밋 메시지"

예시는 다음과 같다.

    git commit -m "first commit"

커밋 메시지는 해당 Commit에서 어떤 작업을 했는지 설명하는 문장이다.

좋은 커밋 메시지는 나중에 이력을 확인할 때 변경 내용을 이해하기 쉽게 만든다.

예시는 다음과 같다.

    git commit -m "팀 정보 YAML 파일 추가"
    git commit -m "타이거즈 매니저 이름 수정"
    git commit -m "사용하지 않는 라이온스 파일 삭제"

## 8. git commit -m과 git commit -am

`git commit -m`과 `git commit -am`은 비슷해 보이지만 차이가 있다.

| 명령어 | 설명 | 새 파일 포함 가능 여부 |
|---|---|---|
| git commit -m | Staging Area에 올라간 변경 사항을 Commit | 가능 |
| git commit -am | 추적 중인 파일의 수정/삭제를 add와 commit 동시에 처리 | 새 파일은 불가능 |

`git commit -m`은 먼저 `git add`를 실행한 뒤 사용한다.

    git add .
    git commit -m "커밋 메시지"

`git commit -am`은 이미 Git이 추적하고 있는 파일의 수정 또는 삭제를 한 번에 Commit할 때 사용할 수 있다.

    git commit -am "타이거즈 멤버 추가"

하지만 `git commit -am`은 새로 생성된 Untracked 파일에는 사용할 수 없다.

새 파일이 추가된 경우에는 반드시 `git add`를 먼저 실행해야 한다.

## 9. git log

`git log`는 Commit 이력을 확인하는 명령어이다.

    git log

`git log`를 실행하면 다음 정보를 확인할 수 있다.

- Commit Hash
- 작성자
- 작성 시간
- Commit 메시지

Commit Hash는 각 Commit을 구분하는 고유한 값이다.

Git은 이 Hash 값을 기준으로 특정 Commit을 식별할 수 있다.

`git log` 화면에서 빠져나오려면 `q`를 누르면 된다.

## 10. Commit Hash

Commit Hash는 Commit을 구분하기 위한 고유한 식별값이다.

각 Commit은 서로 다른 Hash 값을 가진다.

Commit Hash는 다음과 같은 상황에서 사용될 수 있다.

- 특정 Commit으로 이동할 때
- 특정 Commit을 되돌릴 때
- Commit 이력을 비교할 때
- SourceTree에서 특정 Commit을 확인할 때

예를 들어 `git reset`이나 `git revert`를 사용할 때 Commit Hash를 기준으로 특정 시점을 지정할 수 있다.

## 11. SourceTree로 Commit 이력 확인하기

SourceTree는 Git 이력을 시각적으로 확인할 수 있는 GUI 도구이다.

CLI에서는 `git log` 명령어로 Commit 이력을 확인하지만, SourceTree를 사용하면 Commit 흐름을 그래프 형태로 볼 수 있다.

SourceTree에서 확인할 수 있는 정보는 다음과 같다.

| 항목 | 설명 |
|---|---|
| Branch | 현재 작업 중인 브랜치 |
| Commit History | Commit 목록 |
| Commit Hash | Commit 고유 식별값 |
| Author | Commit 작성자 |
| Date | Commit 생성 시간 |
| Changed Files | 해당 Commit에서 변경된 파일 |

SourceTree는 Git의 시간 흐름을 시각적으로 이해하는 데 도움이 된다.

## 12. 파일 추가, 수정, 삭제와 Commit

Git은 파일의 추가, 수정, 삭제를 모두 변경 사항으로 관리한다.

예를 들어 다음과 같은 작업을 했다고 가정할 수 있다.

- 기존 파일 삭제
- 기존 파일 수정
- 새 파일 추가

이때 `git status`를 실행하면 각각 다른 상태로 표시된다.

| 작업 | Git 상태 |
|---|---|
| 새 파일 추가 | Untracked |
| 기존 파일 수정 | Modified |
| 기존 파일 삭제 | Deleted |

이 변경 사항을 모두 Commit하려면 다음 흐름으로 진행한다.

    git status
    git add .
    git status
    git commit -m "파일 추가 수정 삭제"
    git log

`git add .` 이후 다시 `git status`를 확인하면 변경 사항이 Staging Area에 올라간 것을 볼 수 있다.

## 13. 단일 파일만 Commit하기

모든 변경 사항을 한 번에 Commit하지 않고 특정 파일만 Commit할 수도 있다.

예를 들어 `cheetas.yaml` 파일만 Commit하고 싶다면 다음과 같이 작성한다.

    git add cheetas.yaml
    git commit -m "치타스 팀 정보 추가"

이 방식은 여러 작업이 섞였을 때 유용하다.

예를 들어 로그인 기능 수정과 문서 수정이 동시에 발생했다면, 두 작업을 별도의 Commit으로 나누어 기록하는 것이 좋다.

## 14. 좋은 Commit 메시지

Commit 메시지는 변경 사항을 설명하는 문장이다.

나중에 이력을 확인할 때 어떤 작업을 했는지 쉽게 이해할 수 있어야 한다.

좋은 Commit 메시지의 특징은 다음과 같다.

- 변경 내용을 간단히 설명한다.
- 너무 길지 않게 작성한다.
- 무엇을 했는지 명확하게 표현한다.
- 하나의 Commit에는 하나의 목적을 담는다.

예시는 다음과 같다.

    로그인 화면 HTML 구조 추가
    로그인 CSS 스타일 적용
    타이거즈 멤버 정보 수정
    사용하지 않는 파일 삭제

좋지 않은 예시는 다음과 같다.

    수정
    작업함
    test
    asdf

Commit 메시지는 협업에서 다른 사람이 변경 이력을 이해하는 데 중요한 역할을 한다.

## 15. Commit 실습 흐름

이번 강의에서 다룬 Commit 실습 흐름은 다음과 같다.

    Git 저장소 확인
    → 파일 추가
    → 파일 수정
    → 파일 삭제
    → git status로 상태 확인
    → git add로 Staging Area에 추가
    → git commit으로 버전 기록
    → git log로 이력 확인
    → SourceTree에서 Commit 흐름 확인

명령어 흐름은 다음과 같다.

    git status
    git add .
    git commit -m "커밋 메시지"
    git log

새 파일이 없는 수정/삭제 작업만 있다면 다음 명령어도 사용할 수 있다.

    git commit -am "커밋 메시지"

하지만 새 파일이 있다면 반드시 `git add`를 먼저 해야 한다.

## 16. Commit과 Rollback

Commit을 남겨두면 필요할 때 특정 시점으로 되돌아갈 수 있다.

예를 들어 특정 Commit 이후 코드에 문제가 생겼다면, 이전 Commit을 기준으로 상태를 확인하거나 복구할 수 있다.

Git에서 되돌리기와 관련된 대표 명령어는 다음과 같다.

| 명령어 | 설명 |
|---|---|
| git reset | 특정 Commit으로 돌아가며 이후 이력을 삭제할 수 있음 |
| git revert | 기존 이력을 유지하면서 특정 변경 사항을 되돌리는 새 Commit 생성 |

Commit을 잘게 나누어 기록해두면 문제가 발생했을 때 원인을 찾고 복구하기 쉬워진다.

## 17. 정리

Commit은 Git에서 변경 사항을 하나의 버전으로 기록하는 작업이다.

Git은 파일의 상태를 Untracked, Modified, Deleted, Staged, Committed 등으로 구분해서 관리한다.

변경 사항을 Commit하기 위해서는 먼저 `git add`로 Staging Area에 올리고, 이후 `git commit`으로 기록해야 한다.

핵심 개념은 다음과 같다.

- Commit은 특정 시점의 프로젝트 상태를 기록하는 작업이다.
- `git status`는 현재 파일 상태를 확인한다.
- `git add`는 변경 사항을 Staging Area에 추가한다.
- Staging Area는 Commit할 파일을 임시로 모아두는 공간이다.
- `git commit`은 Staging Area에 올라간 변경 사항을 버전으로 기록한다.
- `git commit -m`은 메시지를 포함해 Commit을 생성한다.
- `git commit -am`은 추적 중인 파일의 수정/삭제를 add와 commit 동시에 처리한다.
- 새 파일은 `git commit -am`으로 Commit할 수 없으므로 먼저 `git add`가 필요하다.
- `git log`는 Commit 이력을 확인한다.
- Commit Hash는 각 Commit을 구분하는 고유한 값이다.
- SourceTree를 사용하면 Commit 이력을 시각적으로 확인할 수 있다.