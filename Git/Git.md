# Git

### Git 이란? 

#### 특징

1. 가지 치기와 병합

   여러가지 버전, 테스트를 통해

2. 가볍고 빠르다

   |                   SVN                    | GIT  |
   | :--------------------------------------: | :--: |
   | 중앙시스템 코드 공유, 항상 네트워크 필요 | 로컬 |

3. 분산 작업

4. 데이터 보장

5. 준비 영역(Staging area)

6. 오픈소스

>  Git 호스팅 서비스
>
> - GitHub
> - Bitbucke
> - GitLab



##### 초기설정

```shell
git config user.name "name"
git config user.email email@email.com	

git config --list //설정 정보 확인
```



##### Git 저장소 생성

`Git init` 디렉토리 에 사용



### Git 시작하기

###### Staging Area

- Working Directory: 내가 작업하고 있는 프로젝트의 디렉토리
- Staging Area: 커밋을 하기 위해 $git add 명령어로 추가한 파일들이 모여있는 공간
- Repositiory: 커밋들이 모여있는 저장소

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FmtzJ7%2Fbtq9PUXFlUj%2FNAqKtGV9XIWHwhA1fq7BY1%2Fimg.png)

###### File status LifeCycle

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbYqijC%2Fbtq9MF1MxCE%2F05HbpzPuo2hk9Kn0dDt3mK%2Fimg.png)

**File** 관점에서는 다시 4가지 단계로 나뉜다.

- Untracked : Working Directory에 있는 파일이지만 Git으로 버전관리를 하지 않는 상태
- Unmodified : 신규로 파일이 추가되었을 때, new file 상태와 같다($ git add 상태)
- Modified : 파일이 추가된 이후 해당 파일이 수정되었을 때의 상태
- Staged : Staging Area에 반영된 상태



##### Git 저장소 반영

`sample.js` 파일 작업을 staging 하였으므로 이제 무엇을 수정하고 추가했는지 메시지를 남겨 저장소에 저장하는 작업을 진행합니다.

`git commit`  .git 저장소 내에 staging에 저장

`git commit --amend`  앞에서 적은 메세지에 오타가 있거나 누락된 파일 있을 경우 사용

`git log` 를 통해 **저장소 반영 내역**을 확인 할수 있습니다.

```shell
git log
commit 7sdf9sad9f9sa9d9fs9d9f
Author: ParkAward <parksangjun1363@gmail.com?
Date: Tue Dec 11 22:22:22 2022 +0900
```

`Commit` 에는 다음과 같은 내용이 들어갑니다.



<center>
    <p>Commit size</p>
    <p>Tree</p>
    <p>Parent</p>
    <p>Author</p>
    <p>Commit</p>
    <p><strong>Innital commit</strong></p>
</center>


##### Git 관리 상태

`git status` : Staging file들의 상태 확인

`git log` :  `.git repository` 에 존재하는 history 확인

`git diff`: commit 된 파일 중 변경된 사항을 비교할 때



###### git log

`git log -p -2`

> -p, patch : 각 commit의 수정 결과를 보여주는 diff와 같은 역할을 수행합니다. ex ) 
>
> -n : 상위 n개의 commit만 보여줍니다.

`git log --stat`

> --stat: 어떤 파일이 commit에서 수정되고 변경되었는지, <br>파일 내 라인이 추가되거나 삭제 되었는지 확인

`git log --pretty:onelone`

> --pretty = oneline : 각 commit 한 줄로 출력

**`git log --grahp`**

> --graph: commit간의 연결된 관계를 아스키 그래프로 출력한다.

`git log -S function_name`

-S : 코드에서 추가되거나 제거된 내용 중 특정 텍스트 <br> (위에서는 function_name)가 포함되어 있는지 검사



### Git 가지 치기

1. Git Branch

독립적으로 어떤 작업을 진행하기 위한 개념<br> 각각의 Banch는 다른 Branch의 영향을 받지 않음

![](https://backlog.com/git-tutorial/kr/img/post/stepup/capture_stepup1_1_1.png)

| Main Branch  | 배포할 수 있는 수준의 안정적인 Branch                |
| ------------ | ---------------------------------------------------- |
| Topic Branch | 기능 추가나 버그 수정과 같은 단위 작업을 위한 Branch |

###### `git branch [branch name]` 이 명령어로 브랜치를 생성할 수 있습니다.

자동으로 생성되는 브랜치`master` 브랜치 입니다.

###### `git branch`를 이용하면 현재 브랜치를 알 수 있습니다.

###### `git checkout` 을 통해 브랜치를 확인할 수 있습니다.

checkout은 branch를 전환 하기도 하고 Snapshot을 이동할 수 있습니다. => 과거의 파일로 돌아갈 수 있습니다.

2. fast froward

   새로운 데이터 체크 보인트 생성

3. Merge
   1. `git checkout master` 
   2. `git merge [branch]`
   3.  => master 브랜치에 새로운 내용 없이 추가되는 것을 fast forward
   4. matser 따로 다른 브랜치 따로 내용을 추가했을 경우
   5.   **`git log --graph --all`** 을 사용해서  commit 그래프를 확인 할 수있습니다.
   6.  `git branch --merged` 를 통해 합쳐진 브랜치를 확인할 수 있습니다.
   7. 일반적으로 기능이 완성됐다면 삭제를 해주는게 일반적입니다.
   8. 사용을 마친 branch는 `git branch -d <branch name>`을 이용해 삭제 하세요

4. conflict 해결
   1. Merge한 두 Branch에서 같은 파일을 **변경**했을 때 **충돌**이 발생합니다.
   2. `git merge <branch>`를 사용하고 *CONFLICT* 가 발생하면 자동 Merge하지 못합니다. ( 같은 파일 동시에 건드림)
   3. `git status`를 통해 어느 파일에서 충돌 발생했는지 확인합니다.
   4. 충돌된 파일을 확인 후 `git` 에서 추가한 개행들은 삭제하고 다시 `Merge`를 해야합니다.
   5. `Git Merge 충돌 방지` Master Branch의 변화를 줄여야 합니다.!

###  Git 원격 저장소

1. 원격 저장소 받아오기

   네트워크 어딘가 있는 저장소 => GitJub, gitlab

   1. Git 원격 저장소 받아오기 `git clone` => 기존의 git repository를 복사 (원격이든 , 로컬이든)
   2. **원격 저장소 추가** `git remote add origin https:~~~~`
   3. **원격 저장소 한눈에 살펴보기**`git remote show origin`
   4. 원격 저장소 이름 변경 `git remote rename origin git_test`  origin 에서 git_test로 이름변경
   5. 원격 저장소 삭제 `git remote rm git_test` 

2. 원격 저장소 동기화

   1. `pull` 원격 저장소에서 데이터 가져오기 +  <span style="color:red;">병합(merge)</span>

      ​	원격 저장소에서 데이터를 가져와 **로컬 데이터와 병합**합니다.

   2. Fetch 원격 저장소에서 데이터 가져오기

      ​	`fetch`를 실행한 경우 `git merge origin/master` 로 병학을 완료해야합니다.

​		저장소 발생`git push origin master`

​			로컬 저장소에서 작업한 내용을 원격 저장소에 반영합니다.

​			다른 사람이 먼저 Push한 상태에서는 Push할 수 없어요.

​			다른 사람이 작업한 것을 Merge부터 해주세요

3. Origin?

     `git remote add origin https://githyb.com/gorup/project`

   origin은 주소를 간략하게 가리킵니다. 

### HEAD를 이용한 버젼 관리

`git reset --<option> HAED~`을 이용하여 HEAD를 전의 `snapshot`으로 이동시킬 수 있습니다.

> `--soft(default)`을 이용하여 예전 버전으로 돌아가 commit을 수정할 수 있습니다.

> `git reset --hard`을 이용하면 working directory에 존재하는 파일도 사라집니다. <head>가 사라집니다.

### Rebase

`git rebase master`

위 명령어를 요약하자면 <span style="color:red;">현재 위치해 있는 브랜치의 commit부터</span>

**matster의 공통된 부모 전까지의 commit을** master 옆에 이어 붙인다는 의미입니다.

### Pull/Push/set_upstream(트래킹)

1. **remote 저장소의 이름 지정** `git remote add **orgin** https://github.com/group/project`

2. **트래킹 브랜치를 설정해서 push 또는 pull을 합니다.**

   1. `git pull origin master`
   2. `git push --set-upstream origin master`
   3. `git push origin master`

3. **--set-upstream** 이게 뭘까

   > 앞에서 다룬 메시지는 원격저장소에 위치한 브랜치를 추적하기 위한 <br> 로컬 저장소의 브랜치가 정해지지 않았다는 의미입니다.

   `git branch -set-upstream-to=second/cat cat`

   다른 원격 저장소로부터 소스코드를 가져오는 방법입니다.

   트래킹 브랜치는 저장소에 존재하는 특정 브랜치의 위치를 알려줍니다.

   트래킹 브랜치를 정보를 이용해서 내가 원하는  브랜치와 서로 트래킹을<br>시켜주고 지속적으로 관리할 수 있습니다.

### Pull 오류해결

#### 1. `git clean -f -d -x`

​	git 추적중이지 않은 워킹 디렉토리에 존재하는 파일들과 <br> gitignore로 git의 관리 받지 않는 파일들까지 모두 깨끗하게 지워버리는 명령어입니다.<br> 따라서 수정중이던 내용 중 필요한 부분이 있다면<br>

<center> <strong>커밋으로 수정된 상태를 저장하거나 <br>아예 수정하고 있는 파일을 다른 디텍토리에 옮겨 저장하는 것이 <br>pull 오류를 해결하는 가장 확실한 방법입니다.</strong>

#### 2. `git stash`


1. git stash를 사용하여 작업한 내용을 커밋하지 않고 임시저장 한다.
2. 충돌되는 파일을 삭제 또는 다른 임시 디렉토리로 이동시킨다.

