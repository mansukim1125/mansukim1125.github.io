---
title: Welcome
tags: TeXt
---

# GitHub용 코드 리뷰 설명서

## 하는 이유?

- Git이나 GitHub를 활용하는 방법을 익히기 위해
- 서로의 코드를 보면서 더 나은 방법에 대해 이야기하고 기존의 방법을 개선하기 위해

한다.

## 하는 방법?

### 용어 정리

- 공동 Repository: upstream
- upstream을 Fork한 Repository: origin
- origin을 개인 컴퓨터에 Clone한 Repository: Local Repo

### 시작

#### upstream Fork

upstream이 자신의 GitHub계정에 복사된다. 차후에 Pull Request를 할 목적으로 사용된다.

![image-20200607195408438](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200607195408438.png)

#### Fork된 Repository를 Local에 Clone

코드 작성을 위해 GitHub에 있는 저장소를 Local에 저장한다.

![image-20200607200347846](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200607200347846.png)

```bash
$ git clone https://github.com/<your-account-name>/study.git
```

#### Local Repo에 계정 이름으로 된 Branch 생성

계정 이름으로 된 Branch에는 (작업이 끝나고 코드 검토가 완료된)결과물이 저장된다.

```bash
$ git branch <your-account-name> origin/<your-account-name>
```

#### 작업 Branch 생성 후 작업 시작

계정 이름으로 된 Branch를 기준으로 새 작업 Branch를 생성한다.

```bash
$ git branch example01 <your-account-name>
```

생성 후, 이동한다.

```bash
$ git checkout example01
```

또는 생성과 이동을 한 번에 하는 방법도 있다.

```bash
$ git checkout -b example01 <your-account-name>
```

이 Branch에서 작업을 시작하면 된다.

#### 작업 완료 후, origin에 push하기

push를 하기 전, commit을 해야 한다. 먼저 변경/생성된 파일들을 보자.

```bash
$ git status
```

실행 결과:

```
On branch step01
Untracked files:
  (use "git add <file>..." to include in what will be committed)

   <your-file>

nothing added to commit but untracked files present (use "git add" to track)
```

이처럼 파일이 추가되지 않았음을 확인할 수 있다.

```bash
$ git add .
```

```bash
$ git status
```

실행 결과:

```
On branch example01
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

   new file:   <your-file>

```

이처럼 파일이 추가되었음을 확인할 수 있다. 이제 변경 사항을 commit해보자.

```bash
$ git commit -m "<your-commit-message>"
```

실행 결과:

```
[step01 4e168a7] <your-commit-message>
 1 file changed, 7 insertions(+)
 create mode 100644 <your-file>
```

commit이 완료되었다. 이제 origin에 push를 해보자.

```bash
$ git push origin example01
```

실행 결과:

```
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 352 bytes | 70.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for 'example01' on GitHub by visiting:
remote:      https://github.com/<your-account-name>/study/pull/new/example01
remote: 
To https://github.com/<your-account-name>/study.git
 * [new branch]      example01 -> example01
```

정상적으로 origin에 push되었다. (아래 사진)

![image-20200608133322700](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608133322700.png)

#### 코드 리뷰

##### 요청하기

코드 리뷰는 Pull Request로 한다. `origin`의 `example01`에서 `upstream`의 `<your-account-name>`으로 요청하면 된다.

![image-20200608133504062](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608133504062.png)

해당 Pull Request화면이다.

![image-20200608133607481](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608133607481.png)

##### 코드 리뷰 하기

Pull Request가 오면 메일로 전송된다. view it on GitHub를 누르면 된다.

![image-20200608133758245](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608133758245.png)

Pull Request페이지의 `Files changed`탭에서 가능하다.

![image-20200608134211395](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608134211395.png)

리뷰가 종료되면 `Finish your review`를 눌러 종료한다.

![image-20200608134512194](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608134512194.png)

##### 리뷰 확인하고 수정사항 반영

Pull Request페이지를 확인하면 여러 reviewer들이 남긴 의견이 있다. 이를 확인하고 수정한 뒤, 다시 commit과 push를 해주면 된다.

##### 수정된 내용 확인/Merge

reviewee가 수정해 올린 결과를 확인 후, reviewer의 의견이 Merge(Pull Request승인)하자는 의견으로 일치될 경우, Merge한다.

![image-20200608142443152](https://mansukim1125.github.io/assets/images/code-review-guide-for-github/image-20200608142443152.png)

#### 새 작업 시작

작업을 시작하려면, 완료된 작업 내역인 Branch를 기준으로 새 작업 Branch를 생성해야 한다. 그렇다면 Local Repo의 `<your-account-name>` Branch를 기준으로 새 작업 Branch를 생성해야 하는데, 현재 `<your-account-name>` Branch는 upstream의 `<your-account-name>`과 달리 작업 내역이 없는 상태이다.

##### 동기화

origin과 Local Repo의 `<your-account-name>` Branch를 upstream의 `<your-account-name>` Branch와 동기화해준다. 먼저 Local Repo의 remote repo를 확인해 보자.

```bash
$ git remote -v
```

실행 결과:

```
origin	https://github.com/officialmansu/study.git (fetch)
origin	https://github.com/officialmansu/study.git (push)
```

동기화할 upstream이 없다. 추가해보자.

```bash
$ git remote add upstream https://github.com/mansukim1125/study.git
```

실행 결과:

```
origin	https://github.com/officialmansu/study.git (fetch)
origin	https://github.com/officialmansu/study.git (push)
upstream	https://github.com/mansukim1125/study.git (fetch)
upstream	https://github.com/mansukim1125/study.git (push)
```

추가되었다. Local Repo의 `<your-account-name>` Branch로 이동하자. 그 후, upstream의 `<your-account-name>` Branch의 내용을 가져오자.

```bash
$ git fetch upstream <your-account-name>
```

그 후, rebase를 해보자.

```bash
$ git rebase upstream/<your-account-name>
```

실행 결과:

```
First, rewinding head to replay your work on top of it...
Fast-forwarded <your-account-name> to upstream/<your-account-name>.
```

이로써 upstream의 `<your-account-name>`과 Local Repo의 `<your-account-name>`은 같은 상태가 되었다. 이제 origin의 `<your-account-name>`만 동기화해주면 된다.

```bash
$ git push origin officialmansu
```

실행 결과:

```
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/officialmansu/study.git
   8b00a5d..52b99aa  officialmansu -> officialmansu
```

동기화가 완료되었다. 이제 Local Repo의 `<your-account-name>` Branch를 기준으로 새 작업 Branch를 만들어 작업을 시작하면 된다.