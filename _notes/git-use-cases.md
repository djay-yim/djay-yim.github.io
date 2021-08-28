---
title: "GIT Commands"
permalink: /notes/gitusecases/
toc: true
toc_sticky: true
categories:
  - notes 
tags:
  - tips
---

## #GIT #Commands
> 노트해두고 사용 하던
> \+ 노트해두고 사용 하고싶은 Commands

👇 참고
- 내 머리속에 각인되어있는건 노트하지않음
- 각인 되어 있어도 중요한것 같으면 노트함
- 결국 내맘대로
{: .notice--info}

### ⭐ merge
> merge - from branch(밑에 예제에선 master) commits를 가져와 **새로운 commit 을 만들어 병합**한다.  
> 👉 conflict 영역이 있다면 **merge commit 에 resolve** 한다.
- 
```shell
# If you want merge master branch into current branch.
git merge master
```

### ⭐ rebase (use like merge)
> rebase - from branch(밑에 예제에선 master) **commits를 모두 내 브랜치에 가져오고 그 위에(다음에) 내 commit을 add**한다.
> 👉 conflict 영역이 있다면 현재 브랜치의 **conflict 발생한 commit에 resolve** 한다.
```shell
# If you want rebase master branch into current branch.
git rebase master
git rebase -i master
```

### ⭐ rebase interactive mode
> rebase - commit을 정리할때 사용한다.
> 👉 git rebase -i [변경하고싶은 commit 직전(하나앞)의 commit id]
> e.g.
- commit 합치기
- commit 삭제
- commit 메세지 수정
- commit 내용 수정
```shell
# If you want rebase master branch into current branch.
git rebase -i 7a7c11c4eb5daf3a75d3a087e4af8b5535255317
```