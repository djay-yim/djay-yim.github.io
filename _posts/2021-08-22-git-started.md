---
title: "GIT? started?"
last_modified_at: 2021-08-22
toc: true
toc_sticky: true
categories:
  - git
tags:
  - git
  - github
  - gitlab
---

# #GIT
## 2021.08.22
> GIT ? 나는 원래 SVN으로 형상관리를 해왔었다.  

그당시에 나는, GIT? 알고는 있었다. 근데 쓰고 있진 않았다.   
프로젝트 진행시 필요한 형상관리 기능은 SVN으로도 다 할 수 있었다.  
그때의 나: 굳이 새로운걸 써야될까??? 지금도 다 되는데..?

**지금의 나** : 다들 총들고 싸우는데 혼자 🏹들고 싸우실..?
{: .notice--info}

> GIT을 써야하는데는 몇 가지 이유가 있다.  

- (총 쏘는게) 어렵지 않다. 
- (총 쏘는걸) 배우는것도 어렵지 않다.
- 총 못쏘는 사람과 같이 싸우고 싶은가? 
- 그렇지 않다. 🏹로만 백발백중인 명사수라면 😔

---

### [GIT ?](https://ko.wikipedia.org/wiki/%EA%B9%83_(%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4)){:target="_blank"}
> GIT = History  

- GIT is the history of your codes.
- 요즘에는 대부분의 프로젝트가 GIT으로 관리한다.
- 보편적으로 많이 쓰는건 보편적으로 좋은거다.
- GIT을 아직 안쓴다? 시작하자

#### Features
> 내가 생각하는 제일 큰 장점은 2개다.

- 빠르다.
- local 작업이 가능하다.

---

### ⭐️ How to use?
> 개념? 그냥 한번 써보면 느낌이 온다.  

아, 기존에 나처럼 SVN같은 형상관리툴을 쓰던 사람이라면 이개념 하나는 장착하고 시작하자.

⭐️ **Please Note!**   
👉 기록되는 단위는 **commit**이다.  
👉 ~~file단위~~가 아니다. **commit** 단위다!
{: .notice--danger}

### Commands 👇
- git init
- git add
- git commit
- git remote
- git push
- git stash
- git merge
- git rebase
- git pull
- git reset
- git log
- git branch
- git checkout
- git switch

#### 👉 Using
##### git저장소 세팅(원격저장소=github)
```shell
git init
git add .
git commit -m "commit message"
git remote add origin https://github.com/angelsocer-g/test.git
git push -u origin master
```

##### commit(원격저장소 push까지 할 경우)
```shell
git add .
git commit -m "[update] for test"    
git status
git push
```

##### 원격 저장소 확인
```shell
git remote -v
```

##### branch 생성
```shell
git checkout -b feature/branchA
git push --set-upstream origin feature/branchA
```

##### branch 삭제
```shell
git branch -d feature/branchA
git push origin --delete feature/branchA
```

##### local config - 추가/수정
```shell
git config --local user.name "djay.yim"
git config --local user.email "angelsocer@gmail.com"
```

##### local config - 삭제
```shell
git config --unset --local user.name
git config --unset --local user.email
```

##### reset (hard: commit취소/변경내용삭제)
```shell
git reset --hard
```

##### git log
```shell
git log --pretty=oneline
```

##### git stash
```shell
git stash
git stash list
git stash pop
git stash apply stash@{0}
git stash clear
```

### 🛬 마무리
> 갑자기 마무리한다. 쓰려고 보니 쓸게 너무많다. 나눠서 포스트하자..

## References
- [https://git-scm.com/](https://git-scm.com/){:target="_blank"}
- [위키 - 깃(소프트웨어)](https://ko.wikipedia.org/wiki/%EA%B9%83_(%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4)){:target="_blank"}

