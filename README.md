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