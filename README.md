# Git

- Git 은 파일의 버전을 관리하는 툴

## Git 설치

-https://git-scm.com/

![Image](https://github.com/user-attachments/assets/f23538a4-ae76-46b3-9fb4-d0aff00ae280)
![Image](https://github.com/user-attachments/assets/7e6597fc-6799-4e6e-876c-85a93902b597)
![Image](https://github.com/user-attachments/assets/0bbd8f15-2607-4997-a4f5-ec4b35192ff3)

- `아래는 반드시 VSCode 설치하고 나서 진행하여야 함. (목록 확인 필요)`
  ![Image](https://github.com/user-attachments/assets/af440607-41a3-4279-991d-bb2bc73a8654)
- 나머지는 기본값으로 설치완료함.

## Git 사용자 설정

- VSCode 에서 기본 터미널을 `Git Bash` 로 설정함.
- 터미널 실행 단축키 : `Ctrl + ~`
- 세팅 아이콘 선택 > Setting 메뉴 선택
  ![Image](https://github.com/user-attachments/assets/091e9c0e-c397-446b-a1d0-db3adce5da7b)
- 검색에 `Terminal Default` 입력 > `Git Bash` 목록 선택
  ![Image](https://github.com/user-attachments/assets/d6de7f28-d65d-4040-ab43-2d85d97be3da)

## Git 정보 확인 및 세팅 (터미널에서 진행함)

- Git 버전 확인

```bash
git --version
```

- 기본 브랜치명을 main 으로 설정하기(초기 설치시 master 로 되어있음.)

```bash
git config --global init.defaultBranch main
```

- Enter 키를 통일시킴(맥, 윈도우, 리눅스가 Enter키, 줄변경이 달리 처리됨)

```bash
git config --global core.autocrlf true
```

- 깃 수정내역, 즉 commit 시 메세지 상세 남기기(VSCode 로 작성하도록 세팅)

```bash
git config --global core.editor "code --wait"
```

- 사용자 설정(아이디, 이메일 : 구글 계정과 깃허브 아이디 추천)

```bash
git config --global user.name "아이디"
git config --global user.email "아이디@gmail.com"
```

# GitHub

- 회원가입(https://github.com/) : 구글계정
- 예제) til_basic_git 저장소 생성 (생략)

## GitHub 사용자 계정 보안 설정

- 초기 설정시 다음 내용을 필수로 확인한다.

  - `자격 증명 관리자` > Windows 자격증명 관리 탭 > Git 관련 제거
    ![Image](https://github.com/user-attachments/assets/8e707626-bf16-4731-b13b-d816c5d83fe3)

- 깃허브 자격증명 등록은 git push 진행되면 자동으로 로그인 팝업이 출력됨.

## Git 작업 및 GitHub 연결 작업 진행

### 1. 최초 프로젝트 관리를 Git 으로 설정

```bash
git init
```

### 2. 현재 프로젝트 상태보기

```bash
git status
```

### 3. git 으로 파일 추적하기

```bash
git add README.md
```

### 4. git 으로 모든 파일 추적하기

```bash
git add .
```

### 5. 작업히스토리 남기기

- 간단하게 한줄로 메모 남기기

```bash
git commit -m "메세지"
git commit -m "깃허브 사용법 정리중"
```

- 여러줄 작업내역 작성하기

```bash
git commit
```

### 6. commit 내역 컨벤션 알아보기

```
[커밋타입] 커밋 메시지(옵션)

커밋 상세내역
```

- 커밋 타입 : 업무의 분류

```
[feat] 새로운 기능추가함
[fix] 버그 수정
[docs] 문서 수정(README.nd)
[style] 코드의 스타일(띄워쓰기, 세미콜론 등)
[refactor] 코드 리팩토링(기능변경, 코드 정리 등)
[test] 테스트 코드 추가한 경우
[chore] 기타(빌드 설정, 패키지 설정 등의 개발환경 변경시)
```

- 옵션 : 23 번 이슈를 해결했고, 회원가입 로그인 기능을 추가했다.

```
[feat] 회원가입 로그인 기능 추가(#23)
```

### 7. commit 전체 내역 살펴보기

- 간략하게 살펴보기

```bash
git log
```

- 간략하게 보기

```bash
git log --pretty=oneline
```

- 하나의 commit 을 상세하게 보기(종료시 `q` 키보드 누르기 quit)

```bash
git show 커밋아이디
```

### 8. commit 내용 수정하기

- 바로 전 commit 내용 수정하기

```bash
git commit --amend
```

### 9. `깃허브의 온라인 주소 연결`하기(로컬 : main = 리모트 : origin)

- 등록하기

```bash
git remote add 별명 주소
git remote add origin https://github.com/suha720/til_basic_git.git
```

- 목록보기

```bash
git remote -v
```

- 삭제하기

```bash
git remote remove 별명
```

### 10. 깃허브로 push 하기

```bash
git push -u 별명 로컬브랜치
git push -u origin main

git push // 위의 명령과 같음, -u 가 별명, 로컬브랜치를 생략하게 만듦
```

### 11. 최소 알아야 하는 git 명령

```bash
git add .
git commit
git push
```

# Git 으로 브랜치 관리하기

## Branch 란?

- 개발에서 구현해야 하는 각각의 기능이 있습니다.
- 하나의 기능을 구현 완료하였다면 소스를 버전으로 보관하는 것.
- 다음 기능을 구현한다면 새로운 소스 버전을 만들어서 진행하는 것.

## Branch 초기 이름 세팅

```bash
git config --global init.defaultBranch main
```

## Branch 생성하는 법

```bash
git branch 브랜치명
git branch trip
git checkout -b 브랜치명
```

## Branch 목록 보는 법

```bash
git branch
```

## 원하는 Branch 로 이동하는 법

```bash
git switch 브랜치명
git switch trip
```

## 원하는 Branch 삭제하는 법

```bash
git branch -d 브랜치명

git branch // 목록 필수 확인
git switch 브랜치명 // 다른 브랜치로 이동
```

## 작업이 완료되면 Branch 합치기

```bash
git merge 대상브랜치명
```

## `깃허브 브랜치 삭제`하기(상당히 조심하셔야 해요)
```bash
git push 리모트별칭 --delete 브랜치명
git push origin --delete 브랜치명
```

# Git commit 관리하기

## 1. 바로 이전 커밋 수정하기

- 커밋을 실행 후 바로 내용을 수정하는 경우

```bash
git commit --amend
내용수정 진행, 저장

git log --oneline 또는 git log --pretty=oneline
수정된 것 확인용
```

## 2. 오래전 커밋 내용 수정하기 (권장 X)

- 협업에서 문제 발생 소지
- 커밋 히스토리 통해서 `해시값` 알아보기

```bash
git log --pretty=oneline

예시
$ git log --oneline
d1c3309 (HEAD -> main, origin/main) [docs] 브랜치의 이해
b69b523 [docs] 깃허브 기본 사용 및 연결법
189efb5 [docs] 깃허브 명령어를 공부하고 있음.
bd3256d [커밋타입] 커밋 타이틀
fea3e3b 깃허브 사용법 정리중
```

- 해시값 파악 후 실행(^ 기호는 시작이라는 뜻)

```bash
git rebase -i 해시값^

// 290 안되면 아래 코드 실행
git rebase -i --root

pick bd3256d [커밋타입] 커밋 타이틀
pick 189efb5 [docs] 깃허브 명령어를 공부하고 있음.
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
pick d1c3309 [docs] 브랜치의 이해
pick 8459f84 진행중
```

- 위 처럼 나온 곳에서 `pick b69b523` 을 `edit b69b523` 으로 수정
- `pick` 을 `edit` 으로 수정 후 저장

```bash
pick bd3256d [커밋타입] 커밋 타이틀
pick 189efb5 [docs] 깃허브 명령어를 공부하고 있음.
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
edit d1c3309 [docs] 브랜치의 이해
pick 8459f84 진행중
```

- 실제 내용 수정 진행

```bash
git commit --amend
수정 및 저장
```

- 마무리해서 메인으로 이동

```bash
git rebase --continue
```

## 3. 깃허브에 commit 수정 내용 반영하기

### 3.1. 바로 커밋 수정 후 바로 push 하기

```bash
// 강제로 push 하기 `--force`
git push origin 브랜치명 --force
```

### 3.2. 이전 커밋 수정 후 push 하기

## 4. Clone 하기

### 4.1. https 로 클론하기

```bash
// 뒤에 `.` 폴더 생성없이 clone 생성
git clone 주소 .
```

### 4.2. 깃허브 `특정 브랜치` 클론하기

- 이미 특정 저장소를 클론을 한 상태에서 브랜치를 가져오고 싶다면

```bash
// 리모트별칭 = origin
git fetch 리모트별칭 브랜치명
git checkout 브랜치명


git fetch origin 브랜치명
git checkout 브랜치명

```

- Clone 과 함께 동시에 브랜치 지정하여 Clone 하기
```bash
git clon -b 브랜치명 --single-branch https주소 .
```

## 5. 깃허브 협업 과정
- 팀장(깃허브 관리자)과 팀원(fork 진행)으로 구성권장

### 5.1. 1번 과정
- 팀장 : GitHub 저장소 프로젝트 생성 진행
- 팀장 : PC 에 프로젝트 폴더 만듦
- 팀장 : 프로젝트 폴더에 README.md 파일 만듦
- 팀장 : 프로젝트 기본 구조를 생성 및 세팅 합니다.
- 팀장 : `git init` 초기화
- 팀장 : `git add remote origin 주소`
- 팀장 : `git add .`
- 팀장 : `git commit -m "메세지"`
- 팀장 : `git push origin main`
- 팀장 : 깃허브 주소를 공유하시면서 `fork 받으세요` (메신저는 Slack 추천)

### 5.2. 2번 과정
- 팀원 : 깃허브 주소로 접근 후 `fork` 버튼을 눌러서 깃허브 프로젝트 복사
- 팀원 : 본인의 깃허브로 이동함.
- 팀원 : 본인의 깃허브 주소를 미리 파악해 둠.
- 팀원 : PC 에 폴더 생성 후 VSCode 등록
- 팀원 : `git clone 주소 .` (띄워쓰기 조심)

### 5.3. 3번 과정
- 공통 : `git branch 이름`
- 공통 : `git switch 이름`
- 공통 : 각자 역할에 맞게 작업 진행
- 공통 : `git add .`
- 공통 : `git commit` 메시지를 컨벤션 지키기
- 공통 : `git push origin 이름`

### 5.4. 4번 과정
- 팀원 : 각자 Pull Request 를 작성합니다.
- 팀원 : 팀장에게 PR 보냈음을 알린다.
- 팀원 : 대기함

### 5.5. 5번 과정
- `팀장` : 본인이 본인에게 `Pull Request` 를 작성합니다.

### 5.6. 6번 과정
- 팀장 : PR 을 보고 소스를 보고 Conflict 가 발생하면 팀원 호출
- 팀장 : 꼭 칭찬해 주세요.
- 위 과정 반복해서 소스를 전체 main 에 merge 함

### 5.7. 7번 과정 : main 소스 Synch 요청
- 팀장 : `main sync` 해주세요. 메세지 보내기
- 팀원 : 반드시 `main` 에서 `sync > update` 진행함.

### 5.8. 8번 과정 : 재작업 반복
- 팀원 : `git switch main`
- 팀원 : `git fetch`
- 팀원 : `git pull`
- 팀원 : `git branch -d 이름` // 브랜치 삭제
- 팀원 : `git push origin --delete 이름` // 리모트 브랜치 삭제
- 팀원 : `git branch 이름`
- 팀원 : `git switch 이름`

### 5.9. 9번 과정 : 재작업 반복
- 팀장 : `git switch main`
- 팀장 : `git fetch`
- 팀장 : `git pull`

- 팀장 : 가끔 `소스 오류` 또는 `최신 내용이 안나오는 경우` 존재
- 팀장 : git ` mergin origin/main`

- 팀장 : `git branch -d 이름` // 브랜치 삭제
- 팀장 : `git push origin --delete 이름` // 리모트 브랜치 삭제
- 팀장 : `git branch 이름`
- 팀장 : `git switch 이름`장