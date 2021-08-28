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
> merge - commit을 가져와 **새로운 commit 을 만들어 병합**한다.  
> 👉 conflict? **merge commit 에 resolve**
```shell
# If you want merge master branch into current branch.
git merge master
```

### ⭐ rebase (use like merge)
> rebase - **commit을 먼저 가져오고**, 그 위에 작업 commit을 add한다.  
> 👉 conflict? conflict 발생한 **작업 commit에 resolve**
```shell
# If you want rebase master branch into current branch.
git rebase master
git rebase -i master
```

### ⭐ rebase interactive mode
> rebase - 주로 commit을 정리할때 사용한다.  
> 👉 git rebase -i [변경하고싶은 commit 직전(=하나앞)의 commit id]
```shell
# If you want rebuild branch 
# from commit(7a7c11c4eb5daf3a75d3a087e4af8b5535255317)
git rebase -i 7a7c11c4eb5daf3a75d3a087e4af8b5535255317
```
> Using cases e.g.
- commit 합치기
- commit 삭제
- commit 메세지 수정
- commit 내용 수정  