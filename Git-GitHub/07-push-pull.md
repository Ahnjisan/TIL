# Push와 Pull 이해하기

## 1. 로컬 저장소와 원격 저장소

Git을 사용할 때 저장소는 크게 로컬 저장소와 원격 저장소로 나눌 수 있다.

| 구분 | 설명 |
|---|---|
| 로컬 저장소 | 내 컴퓨터에 있는 Git 저장소 |
| 원격 저장소 | GitHub 같은 온라인 서버에 있는 Git 저장소 |

로컬 저장소에서는 파일을 수정하고, `git add`, `git commit`을 통해 변경 사항을 기록한다.

하지만 로컬에서 커밋했다고 해서 GitHub에 자동으로 올라가는 것은 아니다.

로컬 커밋을 GitHub 원격 저장소에 반영하려면 `push`가 필요하다.

반대로 GitHub 원격 저장소에 있는 변경 사항을 내 로컬 저장소로 가져오려면 `pull`이 필요하다.

## 2. Git과 GitHub의 차이

Git과 GitHub는 서로 다른 개념이다.

| 구분 | Git | GitHub |
|---|---|---|
| 개념 | 버전 관리 도구 | Git 저장소를 온라인에서 관리하는 플랫폼 |
| 위치 | 내 컴퓨터 | 온라인 서버 |
| 인터넷 필요 여부 | 필요 없음 | 필요함 |
| 주요 역할 | commit, branch, log | repository, push, pull, issue, pull request |

Git은 내 컴퓨터에서 코드의 변경 이력을 관리한다.

GitHub는 Git으로 관리되는 프로젝트를 온라인에 올려 공유하고 협업할 수 있게 해주는 플랫폼이다.

즉, Git은 로컬에서 버전을 관리하는 도구이고, GitHub는 원격 저장소를 제공하는 서비스이다.

## 3. 원격 저장소 연결 확인

로컬 저장소가 어떤 원격 저장소와 연결되어 있는지 확인할 때는 다음 명령어를 사용한다.

    git remote -v

실행 결과는 다음과 같은 형태로 나타난다.

    origin  https://github.com/username/repository.git (fetch)
    origin  https://github.com/username/repository.git (push)

여기서 `origin`은 원격 저장소의 기본 이름이다.

`fetch`는 원격 저장소의 변경 사항을 가져올 때 사용하는 주소이고, `push`는 로컬 커밋을 원격 저장소에 올릴 때 사용하는 주소이다.

## 4. origin이란?

`origin`은 Git에서 기본 원격 저장소를 가리키는 이름이다.

로컬 저장소와 GitHub 저장소를 연결하면 보통 원격 저장소 이름이 `origin`으로 설정된다.

예를 들어 다음 명령어는 로컬 저장소에 GitHub 원격 저장소를 `origin`이라는 이름으로 연결한다.

    git remote add origin https://github.com/username/repository.git

이후에는 긴 GitHub 주소를 매번 입력하지 않고 `origin`이라는 이름으로 원격 저장소를 사용할 수 있다.

## 5. Push란?

Push는 로컬 저장소의 커밋을 원격 저장소로 올리는 작업이다.

로컬에서 파일을 수정하고 커밋을 만들었다면, 이 커밋은 아직 내 컴퓨터에만 존재한다.

GitHub에 반영하려면 다음 명령어를 사용한다.

    git push origin main

이 명령어의 의미는 다음과 같다.

| 요소 | 의미 |
|---|---|
| git push | 로컬 커밋을 원격 저장소에 업로드 |
| origin | 업로드할 원격 저장소 |
| main | 업로드할 브랜치 |

즉, 로컬의 `main` 브랜치를 `origin` 원격 저장소에 올리겠다는 의미이다.

## 6. git push 기본 흐름

Push의 기본 흐름은 다음과 같다.

    파일 수정
    → git status
    → git add .
    → git commit -m "커밋 메시지"
    → git push origin main

예시는 다음과 같다.

    git status
    git add .
    git commit -m "레오파드 멤버 추가"
    git push origin main

이미 원격 브랜치와 연결되어 있다면 다음처럼 간단히 사용할 수도 있다.

    git push

즉, push는 로컬에서 만든 커밋을 GitHub에 반영하는 작업이다.

## 7. Pull이란?

Pull은 원격 저장소의 변경 사항을 로컬 저장소로 가져오는 작업이다.

다른 사람이 GitHub에 코드를 올렸거나, GitHub 웹 화면에서 직접 파일을 수정했다면 원격 저장소와 로컬 저장소의 상태가 달라진다.

이때 원격 저장소의 최신 변경 사항을 내 로컬로 가져오기 위해 `pull`을 사용한다.

기본 명령어는 다음과 같다.

    git pull origin main

또는 원격 브랜치와 연결되어 있다면 다음처럼 사용할 수 있다.

    git pull

Pull을 실행하면 원격 저장소의 변경 사항을 가져오고, 현재 로컬 브랜치에 병합한다.

## 8. git pull 기본 흐름

Pull의 기본 흐름은 다음과 같다.

    GitHub 원격 저장소에 새로운 변경 발생
    → 로컬 저장소에서 git pull 실행
    → 원격 변경 사항을 로컬로 가져옴
    → 로컬 파일이 최신 상태로 변경됨

협업에서는 작업을 시작하기 전에 먼저 pull을 하는 것이 좋다.

    git pull
    파일 수정
    git add .
    git commit -m "작업 내용"
    git push

이 흐름을 지키면 원격 저장소와 로컬 저장소의 상태 차이로 인한 문제를 줄일 수 있다.

## 9. Push 전에 Pull이 필요한 이유

로컬에서 커밋을 만들었더라도 원격 저장소에 더 최신 커밋이 존재할 수 있다.

예를 들어 다음과 같은 상황을 생각할 수 있다.

    로컬에서 leopards.yaml 수정 후 commit
    → GitHub에서도 leopards.yaml 수정 발생
    → 로컬에서 바로 push 시도
    → 원격 저장소에 최신 커밋이 있으므로 push 거부 가능

이 경우 먼저 원격 저장소의 변경 사항을 가져와야 한다.

    git pull
    git push

즉, 원격 저장소에 내가 가지고 있지 않은 커밋이 있다면 먼저 pull을 해서 로컬을 최신 상태로 만든 뒤 push해야 한다.

## 10. Push가 거부되는 상황

Push가 거부되는 대표적인 이유는 원격 저장소에 내 로컬에는 없는 새로운 커밋이 존재하기 때문이다.

이 상황에서 Git은 로컬 커밋을 바로 원격 저장소에 올리지 못하게 막는다.

그 이유는 원격 저장소의 변경 사항을 덮어쓰는 문제가 발생할 수 있기 때문이다.

이때 해결 흐름은 다음과 같다.

    git pull
    충돌 발생 시 충돌 해결
    git add .
    git commit
    git push

만약 pull 과정에서 충돌이 발생하지 않는다면 바로 push할 수 있다.

## 11. Pull 방식: Merge와 Rebase

Pull은 원격 저장소의 변경 사항을 가져오고 로컬 변경 사항과 합치는 작업이다.

이때 합치는 방식은 크게 Merge 방식과 Rebase 방식으로 나눌 수 있다.

| 방식 | 설명 |
|---|---|
| Merge 방식 Pull | 원격 변경 사항과 로컬 변경 사항을 병합 커밋으로 합침 |
| Rebase 방식 Pull | 로컬 커밋을 원격 최신 커밋 뒤에 이어 붙임 |

Merge 방식으로 pull하려면 다음과 같이 사용할 수 있다.

    git pull --no-rebase

Rebase 방식으로 pull하려면 다음과 같이 사용할 수 있다.

    git pull --rebase

두 방식은 기존에 학습한 Merge와 Rebase의 차이와 동일하다.

## 12. Merge 방식 Pull

Merge 방식 Pull은 원격 저장소의 변경 사항과 로컬 변경 사항을 병합하는 방식이다.

이 방식은 병합 커밋이 생길 수 있다.

장점은 원격과 로컬의 작업 흐름이 이력에 남는다는 점이다.

단점은 커밋 이력이 복잡해질 수 있다는 점이다.

흐름은 다음과 같다.

    원격 저장소 변경 사항 존재
    → 로컬에서도 커밋 존재
    → git pull --no-rebase
    → 병합 커밋 생성 가능
    → git push

## 13. Rebase 방식 Pull

Rebase 방식 Pull은 로컬 커밋을 원격 저장소의 최신 커밋 뒤에 이어 붙이는 방식이다.

커밋 이력을 한 줄처럼 깔끔하게 유지할 수 있다.

흐름은 다음과 같다.

    원격 저장소 변경 사항 존재
    → 로컬에서도 커밋 존재
    → git pull --rebase
    → 로컬 커밋이 원격 최신 커밋 뒤로 이동
    → git push

다만 이미 팀원과 공유된 커밋에 대해서는 Rebase 사용에 주의해야 한다.

커밋 이력이 변경될 수 있기 때문이다.

## 14. Clone이란?

Clone은 원격 저장소를 내 컴퓨터로 복사하는 작업이다.

GitHub에 있는 프로젝트를 로컬 환경에서 작업하고 싶을 때 사용한다.

명령어는 다음과 같다.

    git clone 원격저장소URL

예시는 다음과 같다.

    git clone https://github.com/username/repository.git

Clone을 하면 프로젝트 파일뿐만 아니라 Git 이력까지 함께 내려받는다.

즉, 단순히 파일만 다운로드하는 것이 아니라 Git 저장소 전체를 복사하는 것이다.

## 15. Push와 Pull의 차이

Push와 Pull은 방향이 반대이다.

| 명령어 | 방향 | 설명 |
|---|---|---|
| git push | 로컬 → 원격 | 로컬 커밋을 GitHub에 업로드 |
| git pull | 원격 → 로컬 | GitHub 변경 사항을 로컬로 가져옴 |
| git clone | 원격 → 로컬 | 원격 저장소 전체를 처음 복사 |

정리하면 다음과 같다.

    push
    → 내가 만든 커밋을 GitHub에 올림

    pull
    → GitHub의 최신 변경 사항을 내 컴퓨터로 가져옴

    clone
    → GitHub 저장소를 처음부터 내 컴퓨터에 복사

## 16. 원격 저장소 사용 흐름

원격 저장소를 사용하는 기본 흐름은 다음과 같다.

    작업 시작 전 git pull
    → 파일 수정
    → git status
    → git add .
    → git commit -m "작업 내용"
    → git push

협업 환경에서는 이 흐름을 지키는 것이 중요하다.

작업 시작 전에 pull을 하지 않으면 원격 저장소의 최신 변경 사항을 모른 채 작업할 수 있다.

작업이 끝난 뒤 push를 하지 않으면 내 로컬 커밋이 GitHub에 반영되지 않는다.

## 17. 정리

Push와 Pull은 GitHub 원격 저장소를 사용할 때 핵심이 되는 명령어이다.

핵심 개념은 다음과 같다.

- 로컬 저장소는 내 컴퓨터에 있는 Git 저장소이다.
- 원격 저장소는 GitHub 같은 온라인 서버에 있는 Git 저장소이다.
- `origin`은 기본 원격 저장소 이름이다.
- `git remote -v`는 연결된 원격 저장소를 확인한다.
- `git push`는 로컬 커밋을 원격 저장소에 올린다.
- `git pull`은 원격 저장소의 변경 사항을 로컬로 가져온다.
- `git clone`은 원격 저장소를 로컬로 복사한다.
- 원격 저장소에 더 최신 커밋이 있으면 바로 push가 거부될 수 있다.
- push가 거부되면 먼저 pull을 해야 한다.
- pull은 merge 방식 또는 rebase 방식으로 수행될 수 있다.
- 협업에서는 작업 전 pull, 작업 후 push 흐름을 지키는 것이 중요하다.