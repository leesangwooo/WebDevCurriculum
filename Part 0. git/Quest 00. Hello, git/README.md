# Quest 00. Hello, git


## Introduction
* git은 2018년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics
* git
  * `git clone`
  * `git add`
  * `git commit`
  * `git push`
  * `git pull`
  * `git branch`
  * `git stash`
* GitHub

## Resources
* [git, 분산 버전 관리 시스템](http://www.yes24.com/24/goods/3676100?scode=032&OzSrank=1), 인사이트
* [GitHub 사용 설명서](http://www.yes24.com/24/Goods/17638082?Acode=101), 교학사
* https://try.github.io
* http://pcottle.github.io/learnGitBranching
* \+) [git tutorial](http://www.dreamy.pe.kr/zbxe/CodeClip/95408) 

## Checklist
* 버전 관리 시스템은 왜 필요한가요?
* git 외의 버전관리 시스템에는 무엇이 있나요? git은 그 시스템과 어떤 점이 다르며, 어떤 장점을 가지고 있나요?
* git의 `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
    
    \+)
    ````
    # .gitconfig
    # Git에서 사용될 사용자 설정하기
    git config --global user.name "사용자이름"
     
    # 이메일 주소 설정.
    git config --global user.email "이메일@git-tutorial.com"
     
    # "matching": 모든 분기를 Push / "simple": 현재 분기만 Push
    git config --global push.default "matching"
    
    # .gitignore 특정 파일 커밋 무시하기
    
    # 저장소 생성하고 커밋하기
    # 지역 Git 저장소 초기화 하기
    git init
    
    # 깃 저장소 복제하기, 기존 워킹디렉토리가 없는 경우 --bare 플래그 삽입
    # clone 명령어는 git init 후 fetch와 같다.
    # 참고. https://git-scm.com/book/ko/v1/Git-서버-서버에-Git-설치하기 (bare 사용 및 그룹 쓰기 권한) 
    $ git clone --bare my_project my_project.git
    
    # 커밋 대상 파일을 Staging  
    git add *
     
    # 지역 저장소로 커밋하기
    git commit -m "커밋 메시지"
     
    # 마지막 커밋 내용과 차이 확인하기
    git diff
    
    # 변경사항 커밋하기, -a: 수정된 파일들에 대해 커밋, --amend: 커밋 메시지 수
    git commit -a -m "수정 내용 커밋"
    
    # 원격 저장소에 지역 저장소 커밋 내용을 push
    git push ../원격_저장소_url.git
    
    # 원격_저장소_url에 alias 주기: git remote add 별명 url 
    git remote add origin ../remote-repository.git
    
    # clone한 원격저장소(현 origin)에 커밋 내용을 push
    git push origin
    
    # 저장소로 이동하여 원격 저장소에 커밋된 변경내용을 pull한다.
    cd ~/저장소.git
    git pull ../원격_저장소_url.git/
    
    # 변경사항 되돌리기
    # 커밋 로그를 확인, commit 영문+숫자 암호코드(커밋 이름).
    git log
    git checkout 커밋_이름
    
    # commit 자체를 되돌리기
    git revert 커밋_이름
    
    # 분기 확인하기(-a: 원격 분기 포함)
    git branch -a
    
    # 분기 만들기: git branch 분기이름 <hash>
    # hash: 커밋 이름. 과거 커밋 중 분기로 만들 수 있다. 옵션사항.
    git branch 분기_이름
    
    # 분기 이동하기 
    git checkout 분기_이름 
    
    # 분기 합치기: git merge <branch-name>
    git merge 합칠_분기_이름
    
    # 하던 일을 Stash하기
    # 참고. https://blog.outsider.ne.kr/788
    # unstaged 상태인 변경사항을 일시적으로 백업하고 워킹디렉토리를 깨끗한 상태로 유지한다.
    git stash
    
    # stash 목록 조회
    git stash list
    
    # 워킹 디렉토리에 stash를 다시 적용하기 (pop: 적용 후 삭제, apply: 변경, stash유)
    git stash pop
    ````

## Quest
* github에 가입한 뒤, [이 커리큘럼의 github 저장소](https://github.com/KnowRe/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* [GitHub Desktop](https://desktop.github.com/)을 다운받아 설치합니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

\+) [Git 커밋 메시지 작성법](https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/)
1. 제목과 본문을 빈 행으로 분리한다
2. 제목 행을 50자로 제한한다
3. 제목 행 첫 글자는 대문자로 쓴다
4. 제목 행 끝에 마침표를 넣지 않는다
5. 제목 행에 명령문을 사용한다
6. 본문을 72자 단위로 개행한다
7. 어떻게 보다는 무엇과 왜를 설명한다
````
Summarize changes in around 50 characters or less (Title)

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here
   
Resolves: #123
See also: #456, #789
````