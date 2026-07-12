# Remote Repository 이해하기

## 1. 원격 저장소란?

원격 저장소는 내 컴퓨터가 아닌 외부 서버에 존재하는 Git 저장소이다.

대표적인 원격 저장소 플랫폼으로는 GitHub가 있다.

Git은 로컬 환경에서 버전 관리를 할 수 있는 도구이고, GitHub는 Git 저장소를 온라인에서 관리하고 협업할 수 있게 해주는 플랫폼이다.

정리하면 다음과 같다.

| 구분 | 설명 |
|---|---|
| 로컬 저장소 | 내 컴퓨터에 있는 Git 저장소 |
| 원격 저장소 | GitHub 같은 온라인 서버에 있는 Git 저장소 |

로컬 저장소에서는 `git add`, `git commit`, `git log` 같은 작업을 수행한다.

원격 저장소와 연결하면 내가 만든 커밋을 GitHub에 올리거나, 다른 사람이 올린 커밋을 내 컴퓨터로 가져올 수 있다.

## 2. 원격 저장소가 필요한 이유

혼자 로컬에서만 작업한다면 Git만으로도 버전 관리를 할 수 있다.

하지만 실제 개발 프로젝트에서는 여러 사람이 함께 작업하는 경우가 많다.

이때 코드를 공유하고 협업하려면 온라인 저장소가 필요하다.

원격 저장소를 사용하면 다음과 같은 작업이 가능하다.

- 내 코드를 온라인에 백업할 수 있다.
- 다른 사람과 코드를 공유할 수 있다.
- 팀원이 작업한 코드를 가져올 수 있다.
- Pull Request를 통해 코드 리뷰를 받을 수 있다.
- Issue를 통해 작업과 버그를 관리할 수 있다.
- GitHub Actions를 통해 빌드, 테스트, 배포를 자동화할 수 있다.

즉, 원격 저장소는 협업과 백업을 위한 중요한 공간이다.

## 3. Git과 GitHub의 관계

Git과 GitHub는 같은 개념이 아니다.

| 구분 | Git | GitHub |
|---|---|---|
| 개념 | 버전 관리 도구 | Git 저장소를 온라인에서 관리하는 플랫폼 |
| 위치 | 로컬 컴퓨터 | 원격 서버 |
| 인터넷 필요 여부 | 필요 없음 | 필요함 |
| 목적 | 변경 이력 관리 | 코드 공유와 협업 |
| 주요 기능 | commit, branch, log | repository, issue, pull request, actions |

Git은 내 컴퓨터에서 소스 코드의 변경 이력을 관리한다.

GitHub는 Git으로 관리되는 코드를 온라인 저장소에 올려 다른 사람과 공유하고 협업할 수 있게 한다.

## 4. Repository란?

Repository는 저장소를 의미한다.

Git에서는 프로젝트의 파일과 변경 이력을 관리하는 공간을 Repository라고 한다.

Repository는 크게 두 가지로 나눌 수 있다.

| 종류 | 설명 |
|---|---|
| Local Repository | 내 컴퓨터에 있는 저장소 |
| Remote Repository | GitHub 같은 서버에 있는 저장소 |

로컬 저장소에서 커밋을 만들고, 이 커밋을 원격 저장소로 올리면 다른 사람도 해당 변경 사항을 확인할 수 있다.

## 5. 원격 저장소 연결

로컬 저장소와 GitHub 원격 저장소를 연결할 때는 `git remote add` 명령어를 사용한다.

기본 형식은 다음과 같다.

    git remote add origin 원격저장소URL

예시는 다음과 같다.

    git remote add origin https://github.com/username/repository.git

여기서 `origin`은 원격 저장소의 기본 이름이다.

보통 하나의 로컬 저장소에 연결된 기본 원격 저장소를 `origin`이라고 부른다.

## 6. 원격 저장소 확인

현재 로컬 저장소에 연결된 원격 저장소를 확인하려면 다음 명령어를 사용한다.

    git remote -v

이 명령어를 실행하면 fetch와 push에 사용되는 원격 저장소 주소를 확인할 수 있다.

예시는 다음과 같다.

    origin  https://github.com/username/repository.git (fetch)
    origin  https://github.com/username/repository.git (push)

`fetch`는 원격 저장소의 변경 사항을 가져올 때 사용되는 주소이고, `push`는 로컬 커밋을 원격 저장소에 올릴 때 사용되는 주소이다.

## 7. Push란?

Push는 로컬 저장소의 커밋을 원격 저장소로 업로드하는 작업이다.

로컬에서 커밋을 만들었다고 해서 자동으로 GitHub에 올라가는 것은 아니다.

GitHub에 반영하려면 push를 해야 한다.

기본 명령어는 다음과 같다.

    git push origin main

이 명령어는 로컬의 `main` 브랜치를 `origin` 원격 저장소에 업로드한다는 의미이다.

처음 push할 때는 다음과 같이 upstream을 설정할 수 있다.

    git push -u origin main

`-u` 옵션을 사용하면 이후에는 `git push`만 입력해도 기본 원격 브랜치로 push할 수 있다.

## 8. Pull이란?

Pull은 원격 저장소의 변경 사항을 로컬 저장소로 가져와 병합하는 작업이다.

다른 사람이 GitHub에 올린 코드를 내 컴퓨터로 가져올 때 사용한다.

기본 명령어는 다음과 같다.

    git pull origin main

이 명령어는 원격 저장소 `origin`의 `main` 브랜치 내용을 가져와 현재 로컬 브랜치에 반영한다.

협업 프로젝트에서는 작업을 시작하기 전에 먼저 pull을 해서 최신 상태를 맞추는 것이 중요하다.

## 9. Fetch란?

Fetch는 원격 저장소의 변경 사항을 가져오지만, 현재 작업 브랜치에 바로 병합하지는 않는 명령어이다.

기본 명령어는 다음과 같다.

    git fetch origin

Pull과 Fetch의 차이는 다음과 같다.

| 명령어 | 설명 |
|---|---|
| git fetch | 원격 저장소의 변경 정보를 가져오기만 함 |
| git pull | 원격 저장소의 변경 정보를 가져오고 현재 브랜치에 병합함 |

즉, Fetch는 원격 저장소의 변경 사항을 먼저 확인하고 싶을 때 사용할 수 있다.

## 10. Clone이란?

Clone은 원격 저장소를 내 컴퓨터로 복사하는 작업이다.

이미 GitHub에 존재하는 프로젝트를 로컬에서 작업하고 싶을 때 사용한다.

기본 명령어는 다음과 같다.

    git clone 원격저장소URL

예시는 다음과 같다.

    git clone https://github.com/username/repository.git

Clone을 하면 프로젝트 파일뿐만 아니라 Git 이력까지 함께 로컬로 가져온다.

따라서 clone한 프로젝트에서는 바로 Git 명령어를 사용할 수 있다.

## 11. 원격 저장소 기본 작업 흐름

원격 저장소를 사용하는 기본 흐름은 다음과 같다.

    GitHub에서 원격 저장소 생성
    → 로컬 프로젝트에서 git init
    → 파일 작성
    → git add
    → git commit
    → git remote add origin 원격저장소URL
    → git push -u origin main

명령어 흐름은 다음과 같다.

    git init
    git add .
    git commit -m "first commit"
    git remote add origin 원격저장소URL
    git push -u origin main

이 과정을 통해 로컬 프로젝트를 GitHub 원격 저장소에 업로드할 수 있다.

## 12. 원격 저장소에서 가져와 작업하는 흐름

이미 GitHub에 있는 프로젝트를 가져와 작업할 때는 clone을 사용한다.

기본 흐름은 다음과 같다.

    git clone 원격저장소URL
    → 프로젝트 폴더로 이동
    → 작업 브랜치 생성
    → 파일 수정
    → git add
    → git commit
    → git push

명령어 흐름은 다음과 같다.

    git clone 원격저장소URL
    cd repository
    git switch -c feature/example
    git add .
    git commit -m "작업 내용"
    git push origin feature/example

협업에서는 보통 main 브랜치에 직접 push하지 않고, 별도 브랜치에서 작업한 뒤 Pull Request를 생성한다.

## 13. Pull Request란?

Pull Request는 내가 작업한 브랜치의 변경 사항을 기준 브랜치에 병합해달라고 요청하는 기능이다.

GitHub 협업에서는 Pull Request를 통해 코드 리뷰를 진행하는 경우가 많다.

기본 흐름은 다음과 같다.

    새 브랜치 생성
    → 기능 개발
    → 커밋
    → 원격 저장소에 push
    → Pull Request 생성
    → 코드 리뷰
    → 승인 후 main 브랜치에 병합

Pull Request를 사용하면 main 브랜치에 바로 반영하지 않고, 변경 내용을 검토한 뒤 병합할 수 있다.

## 14. origin과 upstream

Git에서 원격 저장소 이름으로 가장 많이 사용하는 이름은 `origin`이다.

`origin`은 보통 내가 clone하거나 연결한 기본 원격 저장소를 의미한다.

오픈소스 프로젝트에서는 `upstream`이라는 이름도 자주 사용된다.

| 이름 | 설명 |
|---|---|
| origin | 내 계정 또는 현재 로컬 저장소가 연결된 원격 저장소 |
| upstream | 원본 프로젝트 저장소 |

개인 프로젝트에서는 대부분 `origin`만 사용해도 충분하다.

## 15. 원격 저장소 사용 시 주의할 점

원격 저장소를 사용할 때는 다음 사항을 주의해야 한다.

- 작업 전 `git pull`로 최신 상태를 확인한다.
- main 브랜치에 직접 push하지 않는 것이 좋다.
- 기능별로 브랜치를 나누어 작업한다.
- 커밋 메시지를 명확하게 작성한다.
- push하기 전에 `git status`로 상태를 확인한다.
- Pull Request를 통해 코드 리뷰 후 병합한다.
- 충돌이 발생하면 파일을 직접 확인하고 해결한다.

협업에서는 내 작업뿐만 아니라 다른 팀원의 작업 흐름도 고려해야 한다.

따라서 원격 저장소를 사용할 때는 최신 상태를 유지하고, 브랜치 전략을 지키는 것이 중요하다.

## 16. 정리

원격 저장소는 GitHub 같은 온라인 서버에 있는 Git 저장소이다.

Git은 로컬에서 버전 관리를 수행하고, GitHub는 코드를 온라인에서 공유하고 협업할 수 있도록 도와준다.

핵심 개념은 다음과 같다.

- 로컬 저장소는 내 컴퓨터에 있는 Git 저장소이다.
- 원격 저장소는 GitHub 같은 온라인 서버에 있는 Git 저장소이다.
- `git remote add origin`은 로컬 저장소와 원격 저장소를 연결한다.
- `git remote -v`는 연결된 원격 저장소를 확인한다.
- `git push`는 로컬 커밋을 원격 저장소에 업로드한다.
- `git pull`은 원격 저장소의 변경 사항을 가져와 병합한다.
- `git fetch`는 원격 저장소의 변경 사항을 가져오기만 한다.
- `git clone`은 원격 저장소를 로컬로 복사한다.
- Pull Request는 변경 사항을 병합해달라고 요청하는 기능이다.
- 협업에서는 main 브랜치에 직접 push하기보다 별도 브랜치에서 작업하고 Pull Request를 사용하는 것이 좋다.