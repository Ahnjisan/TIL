# Git 설치 및 초기 세팅

## 1. Git 설치가 필요한 이유

Git을 사용하기 위해서는 먼저 로컬 환경에 Git이 설치되어 있어야 한다.

Git은 로컬 컴퓨터에서 프로젝트의 변경 이력을 관리하는 도구이다.  
따라서 GitHub를 사용하기 전에도 내 컴퓨터에서 Git 명령어를 사용할 수 있는 환경을 먼저 구성해야 한다.

Git을 설치하면 다음과 같은 작업을 할 수 있다.

| 작업 | 설명 |
|---|---|
| 버전 확인 | Git이 정상적으로 설치되었는지 확인 |
| 사용자 설정 | 커밋 작성자 이름과 이메일 설정 |
| 저장소 생성 | 프로젝트 폴더를 Git 저장소로 초기화 |
| 변경 이력 관리 | 파일 수정 내역을 추적하고 기록 |
| 브랜치 관리 | 여러 작업 흐름을 분리하여 관리 |

즉, Git 설치는 로컬에서 버전 관리를 시작하기 위한 첫 단계이다.

## 2. Git 다운로드

Windows 환경에서는 Git 공식 사이트에서 설치 파일을 다운로드할 수 있다.

검색창에 다음과 같이 입력한다.

    git download

검색 결과에서 Git 공식 다운로드 페이지로 이동한 뒤, 사용 중인 운영체제에 맞는 설치 파일을 다운로드한다.

Windows 사용자는 일반적으로 64-bit 설치 파일을 다운로드하면 된다.

설치 파일은 보통 다음과 같은 형태이다.

    Git-2.xx.x-64-bit.exe

다운로드한 실행 파일을 실행하면 Git 설치를 진행할 수 있다.

## 3. Git 설치 과정

Git 설치는 일반적인 프로그램 설치 과정과 비슷하다.

기본 흐름은 다음과 같다.

    Git 설치 파일 실행
    → 라이선스 확인
    → 설치 경로 선택
    → 기본 에디터 선택
    → PATH 설정
    → 설치 옵션 확인
    → 설치 완료

대부분의 설정은 기본값으로 진행해도 큰 문제가 없다.

다만 PATH 설정은 중요하다.  
PATH에 Git이 등록되면 터미널이나 Git Bash에서 Git 명령어를 사용할 수 있다.

설치가 완료되면 Git Bash 또는 터미널에서 Git 명령어를 실행할 수 있다.

## 4. Mac 환경의 Git

Mac은 기본적으로 Git이 설치되어 있는 경우가 많다.

따라서 별도 설치를 하기 전에 먼저 Git 버전을 확인해보는 것이 좋다.

터미널에서 다음 명령어를 입력한다.

    git --version

Git 버전이 출력되면 이미 설치되어 있는 상태이다.

예시는 다음과 같다.

    git version 2.39.0

만약 Git이 설치되어 있지 않다면 Xcode Command Line Tools 또는 Homebrew를 통해 설치할 수 있다.

## 5. Git 버전 확인

Git 설치가 완료되었는지 확인하려면 다음 명령어를 사용한다.

    git --version

정상적으로 설치되어 있다면 다음과 같이 Git 버전이 출력된다.

    git version 2.51.0

이 명령어가 정상적으로 실행되면 Git을 사용할 수 있는 상태이다.

만약 명령어가 인식되지 않는다면 Git이 제대로 설치되지 않았거나 PATH 설정이 되어 있지 않을 수 있다.

## 6. Git 사용 방식

Git을 사용하는 방식은 크게 CLI 방식과 GUI 방식으로 나눌 수 있다.

| 방식 | 의미 | 설명 | 예시 |
|---|---|---|---|
| CLI | Command Line Interface | 명령어를 입력해서 사용하는 방식 | Git Bash, 터미널 |
| GUI | Graphical User Interface | 그래픽 화면에서 사용하는 방식 | SourceTree, GitHub Desktop |

CLI 방식은 터미널에 명령어를 직접 입력해서 Git을 사용하는 방식이다.

GUI 방식은 버튼, 메뉴, 그래프 화면을 통해 Git을 사용하는 방식이다.

Git을 처음 배울 때는 CLI 명령어의 의미를 먼저 익히는 것이 중요하다.  
GUI 도구는 Git의 흐름을 시각적으로 확인하는 데 도움이 된다.

## 7. Git Bash

Git Bash는 Windows 환경에서 Git 명령어를 사용할 수 있도록 제공되는 터미널 도구이다.

Git Bash를 사용하면 Linux나 Mac 터미널과 비슷한 방식으로 명령어를 입력할 수 있다.

Git Bash에서는 다음과 같은 명령어를 사용할 수 있다.

    git --version
    git config
    git init
    git status
    git add
    git commit
    git log

Windows 탐색기에서 특정 폴더를 마우스 오른쪽 버튼으로 클릭하면 Git Bash Here 메뉴를 통해 해당 위치에서 Git Bash를 실행할 수 있다.

## 8. SourceTree

SourceTree는 Git을 GUI 방식으로 사용할 수 있게 해주는 도구이다.

SourceTree를 사용하면 Git 저장소의 커밋 이력과 브랜치 흐름을 그래프 형태로 확인할 수 있다.

SourceTree의 주요 특징은 다음과 같다.

| 특징 | 설명 |
|---|---|
| 시각적 이력 확인 | 커밋 흐름을 그래프로 확인 가능 |
| 브랜치 관리 | 브랜치 생성, 이동, 병합을 화면에서 처리 가능 |
| 변경 파일 확인 | 어떤 파일이 수정되었는지 쉽게 확인 가능 |
| GitHub 연동 | 원격 저장소와 연결 가능 |

SourceTree는 CLI 명령어가 익숙하지 않은 경우 Git의 흐름을 이해하는 데 도움이 된다.

하지만 Git의 원리를 정확히 이해하려면 CLI 명령어의 의미를 먼저 학습하는 것이 좋다.

## 9. SourceTree 설치

SourceTree를 설치하려면 검색창에 다음과 같이 입력한다.

    sourcetree download

SourceTree 공식 사이트에서 설치 파일을 다운로드한 뒤 실행한다.

설치 과정에서는 다음과 같은 단계가 나타날 수 있다.

    SourceTree 설치 파일 실행
    → 라이선스 동의
    → 계정 등록 또는 건너뛰기
    → 사용자 정보 입력
    → SSH Key 설정 여부 확인
    → 설치 완료

GitHub 계정이나 Bitbucket 계정 연동을 요구할 수 있지만, 실습 목적이라면 우선 건너뛰고 로컬 저장소를 연결해도 된다.

SSH Key를 가지고 있지 않다면 해당 단계도 건너뛸 수 있다.

## 10. Git 사용자 설정

Git을 처음 사용할 때는 사용자 이름과 이메일을 설정해야 한다.

이 정보는 커밋을 남길 때 작성자 정보로 기록된다.

사용자 이름 설정 명령어는 다음과 같다.

    git config --global user.name "사용자이름"

사용자 이메일 설정 명령어는 다음과 같다.

    git config --global user.email "이메일주소"

예시는 다음과 같다.

    git config --global user.name "Jisan"
    git config --global user.email "jisan@example.com"

여기서 `--global` 옵션은 현재 컴퓨터 전체에서 사용할 기본 설정을 의미한다.

즉, 한 번 설정하면 이후 다른 Git 저장소에서도 같은 사용자 정보가 기본으로 사용된다.

## 11. Git 설정 확인

설정한 사용자 이름과 이메일은 다음 명령어로 확인할 수 있다.

    git config --global user.name
    git config --global user.email

정상적으로 설정되어 있다면 입력한 이름과 이메일이 출력된다.

예시는 다음과 같다.

    Jisan
    jisan@example.com

전체 Git 설정 목록을 확인하고 싶다면 다음 명령어를 사용할 수 있다.

    git config --list

이 명령어를 사용하면 사용자 이름, 이메일, 기본 브랜치 설정 등 현재 Git 설정 정보를 확인할 수 있다.

## 12. GitHub 계정과 Git 사용자 정보

Git 사용자 설정에서 입력하는 이름과 이메일은 커밋 작성자 정보를 의미한다.

GitHub 계정 자체와 완전히 같은 개념은 아니다.

하지만 GitHub에 코드를 올릴 계획이라면 GitHub 계정에서 사용하는 이메일과 Git 사용자 이메일을 맞춰두는 것이 좋다.

이렇게 하면 GitHub에서 커밋 작성자를 더 정확하게 인식할 수 있다.

정리하면 다음과 같다.

| 구분 | 설명 |
|---|---|
| Git user.name | 커밋 작성자 이름 |
| Git user.email | 커밋 작성자 이메일 |
| GitHub 계정 | 온라인 저장소를 사용하는 계정 |

## 13. 기본 브랜치 이름 설정

예전에는 Git의 기본 브랜치 이름으로 `master`가 많이 사용되었다.

하지만 최근에는 기본 브랜치 이름으로 `main`을 사용하는 경우가 많다.

새 저장소를 만들 때 기본 브랜치 이름을 `main`으로 설정하려면 다음 명령어를 사용할 수 있다.

    git config --global init.defaultBranch main

이 설정을 해두면 이후 `git init`으로 새 저장소를 만들 때 기본 브랜치가 `main`으로 생성된다.

기본 브랜치 이름을 확인하거나 변경해두면 GitHub 저장소와 연결할 때 브랜치 이름 혼선을 줄일 수 있다.

## 14. 실습 폴더 생성

Git 실습을 위해서는 테스트용 프로젝트 폴더를 하나 만드는 것이 좋다.

예를 들어 다음과 같은 폴더를 만들 수 있다.

    C:\vscode_project\git-demo

또는 원하는 위치에 `git-demo`라는 폴더를 생성해도 된다.

이 폴더는 Git 명령어를 실습하기 위한 작업 공간으로 사용한다.

폴더를 만든 뒤 VS Code에서 해당 폴더를 열면 된다.

흐름은 다음과 같다.

    실습 폴더 생성
    → VS Code 실행
    → File
    → Open Folder
    → git-demo 폴더 선택
    → 작업 공간 열기

## 15. VS Code에서 터미널 열기

VS Code에서는 내부 터미널을 사용할 수 있다.

터미널을 열면 현재 프로젝트 폴더 위치에서 명령어를 실행할 수 있다.

VS Code에서 터미널을 여는 흐름은 다음과 같다.

    VS Code 실행
    → 프로젝트 폴더 열기
    → Terminal 메뉴 선택
    → New Terminal 클릭

터미널이 열리면 해당 프로젝트 폴더에서 Git 명령어를 실행할 수 있다.

예를 들어 다음 명령어로 Git 버전을 확인할 수 있다.

    git --version

## 16. Git Bash 터미널 선택

VS Code 터미널에서는 PowerShell, Command Prompt, Git Bash 등 여러 종류의 터미널을 선택할 수 있다.

Git 실습에서는 Git Bash를 사용하면 편리하다.

Git Bash는 Git 명령어를 사용하기에 적합하고, Linux 스타일 명령어에도 익숙해질 수 있기 때문이다.

터미널 선택 흐름은 다음과 같다.

    VS Code 터미널 열기
    → 터미널 우측 드롭다운 선택
    → Git Bash 선택

이후 Git Bash 환경에서 Git 명령어를 입력하면 된다.

## 17. Git 설치 및 설정 전체 흐름

Git 설치와 초기 설정 흐름은 다음과 같이 정리할 수 있다.

    Git 다운로드
    → Git 설치
    → git --version으로 설치 확인
    → Git 사용자 이름 설정
    → Git 사용자 이메일 설정
    → 기본 브랜치 이름 main으로 설정
    → 실습 폴더 생성
    → VS Code에서 폴더 열기
    → Git Bash 터미널 실행

사용하는 명령어는 다음과 같다.

    git --version
    git config --global user.name "사용자이름"
    git config --global user.email "이메일주소"
    git config --global user.name
    git config --global user.email
    git config --global init.defaultBranch main

## 18. 초기 설정에서 주의할 점

Git 초기 설정을 할 때 주의할 점은 다음과 같다.

첫 번째, Git이 정상적으로 설치되었는지 반드시 확인해야 한다.

    git --version

이 명령어가 정상적으로 실행되지 않으면 Git 명령어를 사용할 수 없다.

두 번째, 사용자 이름과 이메일을 설정해야 한다.

커밋을 남길 때 작성자 정보가 필요하기 때문이다.

세 번째, GitHub와 연동할 계획이라면 이메일을 GitHub 계정과 맞춰두는 것이 좋다.

네 번째, 기본 브랜치 이름을 `main`으로 설정해두면 이후 GitHub와 연결할 때 혼선을 줄일 수 있다.

다섯 번째, 실습용 폴더와 실제 프로젝트 폴더를 구분해서 관리하는 것이 좋다.

## 19. 정리

이번 학습에서는 Git을 사용하기 위한 설치와 초기 설정 과정을 정리했다.

핵심 개념은 다음과 같다.

- Git을 사용하려면 로컬 환경에 Git이 설치되어 있어야 한다.
- Windows에서는 Git 설치 파일을 다운로드하여 설치할 수 있다.
- Mac은 기본적으로 Git이 설치되어 있는 경우가 많다.
- `git --version`으로 Git 설치 여부를 확인할 수 있다.
- Git은 CLI 방식과 GUI 방식으로 사용할 수 있다.
- Git Bash는 Windows에서 Git 명령어를 사용할 수 있는 터미널 도구이다.
- SourceTree는 Git을 시각적으로 다룰 수 있는 GUI 도구이다.
- Git을 처음 사용할 때는 사용자 이름과 이메일을 설정해야 한다.
- `git config --global user.name`은 커밋 작성자 이름을 설정한다.
- `git config --global user.email`은 커밋 작성자 이메일을 설정한다.
- `git config --global init.defaultBranch main`은 기본 브랜치 이름을 main으로 설정한다.
- VS Code에서 실습 폴더를 열고 Git Bash 터미널을 사용하면 Git 실습을 진행할 수 있다.