# Branch의 개념과 활용

## 1. Branch란?

Branch는 Git에서 작업 흐름을 나누기 위한 기능이다.

하나의 프로젝트 안에서 여러 작업을 동시에 진행할 때, 각각의 작업을 독립적인 공간에서 진행할 수 있도록 도와준다.

강의에서는 Branch를 “분기된 다른 차원” 또는 “다른 공간”으로 설명했다.

기본적으로 Git 저장소에는 `main` 브랜치가 존재한다.

새로운 기능을 개발하거나 테스트를 진행할 때는 `main`에서 바로 작업하지 않고 새로운 Branch를 만들어 작업할 수 있다.

예시는 다음과 같다.

    main branch
    ├── login branch
    ├── board branch
    └── payment branch

각 Branch는 독립적인 작업 공간처럼 사용할 수 있다.

## 2. Branch가 필요한 이유

협업 프로젝트에서는 여러 사람이 동시에 다른 기능을 개발한다.

모든 사람이 `main` 브랜치에서 직접 작업하면 코드가 섞이고 충돌이 발생할 가능성이 높아진다.

Branch를 사용하면 다음과 같은 장점이 있다.

| 장점 | 설명 |
|---|---|
| 작업 분리 | 기능별로 독립적인 작업 공간을 만들 수 있음 |
| 안정성 유지 | main 브랜치를 안정적인 상태로 유지 가능 |
| 동시 개발 | 여러 개발자가 서로 다른 기능을 동시에 개발 가능 |
| 테스트 가능 | 새로운 시도를 별도 브랜치에서 진행 가능 |
| 병합 관리 | 완료된 작업만 main 브랜치에 합칠 수 있음 |

즉, Branch는 협업에서 안정성과 독립성을 확보하기 위한 중요한 기능이다.

## 3. main 브랜치

`main` 브랜치는 프로젝트의 기준이 되는 브랜치이다.

일반적으로 안정적으로 동작하는 코드를 `main` 브랜치에 유지한다.

새로운 기능을 개발할 때는 `main`에서 직접 작업하기보다 별도의 브랜치를 만들어 작업하는 것이 좋다.

예시는 다음과 같다.

    main
    → 안정적인 코드 유지

    feature/login
    → 로그인 기능 개발

    feature/board
    → 게시판 기능 개발

기능 개발이 끝나면 검토 후 `main` 브랜치에 병합할 수 있다.

## 4. Branch를 공간으로 이해하기

Git은 Commit을 통해 시간의 흐름을 관리한다.

반면 Branch는 작업 공간을 나누는 역할을 한다.

즉, Git은 시간과 공간을 모두 관리할 수 있다.

| 개념 | 의미 |
|---|---|
| Commit | 특정 시점의 상태를 저장 |
| Branch | 독립적인 작업 공간을 생성 |

예를 들어 `main` 브랜치에는 안정적인 코드가 있고, `login` 브랜치에서는 로그인 기능을 개발할 수 있다.

이때 로그인 기능 개발 중 오류가 발생해도 `main` 브랜치에는 영향을 주지 않는다.

## 5. Branch 목록 확인

현재 저장소에 있는 Branch 목록을 확인할 때는 다음 명령어를 사용한다.

    git branch

현재 위치한 Branch에는 `*` 표시가 붙는다.

예시는 다음과 같다.

    * main
      login
      board

위 예시에서는 현재 `main` 브랜치에 있다는 뜻이다.

## 6. Branch 생성

새 Branch를 생성할 때는 다음 명령어를 사용한다.

    git branch 브랜치명

예시는 다음과 같다.

    git branch login

이 명령어는 `login`이라는 새 Branch를 생성한다.

하지만 Branch를 생성한다고 해서 자동으로 해당 Branch로 이동하는 것은 아니다.

새 Branch에서 작업하려면 이동 명령어를 별도로 실행해야 한다.

## 7. Branch 이동

특정 Branch로 이동할 때는 다음 명령어를 사용한다.

    git switch 브랜치명

예시는 다음과 같다.

    git switch login

이 명령어를 실행하면 현재 작업 위치가 `login` 브랜치로 변경된다.

Branch를 이동한 뒤 작업하면 해당 Branch에 변경 사항이 기록된다.

## 8. Branch 생성과 동시에 이동

새 Branch를 만들고 바로 이동하려면 다음 명령어를 사용할 수 있다.

    git switch -c 브랜치명

예시는 다음과 같다.

    git switch -c login

이 명령어는 `login` 브랜치를 생성한 뒤, 바로 `login` 브랜치로 이동한다.

실무에서는 브랜치를 만들고 바로 작업하는 경우가 많기 때문에 `git switch -c`를 자주 사용할 수 있다.

## 9. Branch 이름 변경

Branch 이름을 변경할 때는 다음 명령어를 사용한다.

    git branch -m 기존브랜치명 새브랜치명

예시는 다음과 같다.

    git branch -m login feature-login

위 명령어는 `login` 브랜치의 이름을 `feature-login`으로 변경한다.

Branch 이름에 오타가 있거나, 브랜치 네이밍 규칙을 맞춰야 할 때 사용할 수 있다.

## 10. Branch 삭제

Branch를 삭제할 때는 다음 명령어를 사용한다.

    git branch -d 브랜치명

예시는 다음과 같다.

    git branch -d login

소문자 `-d`는 안전 삭제 옵션이다.

Git은 해당 Branch의 변경 사항이 다른 Branch에 병합되지 않은 상태라면 삭제를 막을 수 있다.

즉, 실수로 작업 내용을 잃어버리는 것을 방지한다.

## 11. Branch 강제 삭제

병합되지 않은 변경 사항이 있는 Branch를 강제로 삭제해야 할 때는 대문자 `-D` 옵션을 사용한다.

    git branch -D 브랜치명

예시는 다음과 같다.

    git branch -D test

대문자 `-D`는 강제 삭제이다.

병합되지 않은 변경 사항까지 삭제될 수 있으므로 신중하게 사용해야 한다.

정리하면 다음과 같다.

| 명령어 | 설명 |
|---|---|
| git branch -d 브랜치명 | 안전 삭제 |
| git branch -D 브랜치명 | 강제 삭제 |

## 12. Branch 관련 명령어 정리

Branch 관련 주요 명령어는 다음과 같다.

| 작업 | 명령어 |
|---|---|
| Branch 목록 확인 | git branch |
| Branch 생성 | git branch 브랜치명 |
| Branch 이동 | git switch 브랜치명 |
| Branch 생성 후 이동 | git switch -c 브랜치명 |
| Branch 이름 변경 | git branch -m 기존브랜치명 새브랜치명 |
| Branch 삭제 | git branch -d 브랜치명 |
| Branch 강제 삭제 | git branch -D 브랜치명 |

Branch를 사용할 때는 현재 내가 어느 Branch에 있는지 항상 확인하는 것이 중요하다.

현재 Branch를 확인하지 않고 작업하면 원하지 않는 Branch에 Commit을 남길 수 있다.

## 13. Branch 작업 흐름

일반적인 Branch 작업 흐름은 다음과 같다.

    main 브랜치에서 시작
    → 새 브랜치 생성
    → 새 브랜치로 이동
    → 기능 개발
    → 변경 사항 Commit
    → main 브랜치로 병합

예시는 다음과 같다.

    git branch
    git switch -c login
    파일 수정
    git status
    git add .
    git commit -m "로그인 기능 추가"

이렇게 하면 `login` 브랜치에서 독립적으로 작업을 진행할 수 있다.

## 14. Branch와 Commit의 관계

Branch는 Commit의 흐름을 가리키는 이름이라고 볼 수 있다.

Commit은 특정 시점의 프로젝트 상태를 기록하고, Branch는 그 Commit 흐름을 따라 이동한다.

예를 들어 `main` 브랜치에서 새 Branch를 만들면, 새 Branch는 현재 Commit 지점에서 시작한다.

그 후 새 Branch에서 Commit을 남기면 `main`과는 다른 흐름이 만들어진다.

흐름은 다음과 같다.

    main: A → B
              \
    login:     C → D

위 구조에서 `login` 브랜치는 `main`의 B 시점에서 분기되어 C, D Commit을 추가한 상태이다.

## 15. Branch와 협업

협업에서는 Branch를 기능 단위로 나누어 사용하는 경우가 많다.

예를 들어 팀원이 각각 다른 기능을 개발할 때 다음과 같이 브랜치를 나눌 수 있다.

    main
    ├── feature/login
    ├── feature/signup
    ├── feature/board
    └── feature/payment

이렇게 작업하면 각 개발자가 독립적으로 기능을 구현할 수 있다.

개발이 끝난 Branch는 코드 리뷰를 거쳐 `main` 브랜치에 병합할 수 있다.

이 과정에서 GitHub의 Pull Request를 사용할 수 있다.

## 16. Branch 네이밍

Branch 이름은 작업 내용을 이해할 수 있도록 작성하는 것이 좋다.

예시는 다음과 같다.

| 브랜치 이름 | 의미 |
|---|---|
| feature/login | 로그인 기능 개발 |
| feature/signup | 회원가입 기능 개발 |
| fix/login-error | 로그인 오류 수정 |
| docs/readme | README 문서 수정 |
| test/api | API 테스트 작업 |

좋은 Branch 이름은 어떤 작업을 위한 Branch인지 바로 이해할 수 있게 해준다.

## 17. Branch 사용 시 주의할 점

Branch를 사용할 때 주의할 점은 다음과 같다.

첫 번째, 작업 전 현재 Branch를 확인해야 한다.

    git branch

두 번째, main 브랜치에서 직접 기능 개발을 하지 않는 것이 좋다.

세 번째, Branch를 생성한 뒤 실제로 이동했는지 확인해야 한다.

    git switch 브랜치명

네 번째, 작업이 끝난 Branch는 병합 후 정리할 수 있다.

다섯 번째, 강제 삭제 옵션인 `-D`는 신중하게 사용해야 한다.

## 18. reset, revert와 Branch의 관계

Commit은 시간의 흐름을 관리하고, Branch는 작업 공간을 나눈다.

Git에서는 Commit을 기준으로 과거로 돌아갈 수 있고, Branch를 통해 여러 작업 흐름을 만들 수 있다.

되돌리기 명령어는 다음과 같다.

| 명령어 | 설명 |
|---|---|
| git reset | 특정 Commit으로 돌아가며 이후 이력을 삭제할 수 있음 |
| git revert | 기존 이력을 유지하면서 특정 변경 사항을 취소하는 새 Commit 생성 |

Branch를 사용하면 새로운 기능이나 실험적인 작업을 별도 공간에서 진행할 수 있기 때문에 main 브랜치의 안정성을 유지할 수 있다.

## 19. Branch 학습 흐름

이번 강의에서 다룬 Branch 학습 흐름은 다음과 같다.

    Git 이력 확인
    → reset과 revert 개념 학습
    → Branch 필요성 이해
    → Branch 생성 명령어 확인
    → Branch 이동 명령어 확인
    → Branch 삭제 명령어 확인
    → Branch 강제 삭제 옵션 확인

Branch는 이후 협업, Pull Request, Merge, 충돌 해결을 이해하기 위한 기반 개념이다.

## 20. 정리

Branch는 Git에서 작업 흐름을 나누기 위한 기능이다.

하나의 프로젝트 안에서 여러 기능을 동시에 개발할 때 Branch를 사용하면 각 작업을 독립적으로 진행할 수 있다.

핵심 개념은 다음과 같다.

- Branch는 독립적인 작업 공간이다.
- main 브랜치는 프로젝트의 기준이 되는 브랜치이다.
- 새 기능 개발은 별도 Branch에서 진행하는 것이 좋다.
- `git branch`는 Branch 목록을 확인한다.
- `git branch 브랜치명`은 새 Branch를 생성한다.
- `git switch 브랜치명`은 특정 Branch로 이동한다.
- `git switch -c 브랜치명`은 Branch를 생성하면서 동시에 이동한다.
- `git branch -m 기존브랜치명 새브랜치명`은 Branch 이름을 변경한다.
- `git branch -d 브랜치명`은 Branch를 안전 삭제한다.
- `git branch -D 브랜치명`은 Branch를 강제 삭제한다.
- Branch를 사용할 때는 현재 위치한 Branch를 항상 확인해야 한다.
- Branch는 협업에서 작업 분리와 안정성 유지를 위해 중요하다.