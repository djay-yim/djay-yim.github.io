---
title: "CLI Commands"
permalink: /notes/cliusecases/
toc: true
toc_sticky: true
categories:
  - notes 
tags:
  - tips
---

## #Command #Line #Interface
> 노트해두고 사용 하던
> \+ 노트해두고 사용 하고싶은 Commands

👇 참고
- 내 머리속에 각인되어있는건 노트하지않음
- 각인 되어 있어도 중요한것 같으면 노트함
- 결국 내맘대로
{: .notice--info}

### ⭐ whatis (MAC OS)
> 어떤 명령어인지 확인
```shell
# 재귀호출가능 ㅋㅋㅋㅋㅋㅋㅋㅋㅋ
whatis whatis
```

### ⭐ find
> find 가 1등인건 누구도 부정할 수 없지않지않을수도있지않을까?
```shell
# 현재경로(./)에서 file명에 something 들어가 있는거 찾기
find ./ -name "*something*"
# 30일 이상된것 삭제
find . -name "*something*" -mtime +30 -exec rm -r {} ';';
```

### ⭐ grep, egrep
> egrep 이 or연산이 됬었던것 같음
```shell
ps -ef | grep grepword | grep -v grep
ps -ef | egrep '\-D.*Server'
```

### ⭐ awk
> pattern-directed scanning and processing language
```shell
ps -ef | grep grepword | awk '{print $2}'
```

### ⭐ cp, mv, rm
> copy, move, remove
```shell
#cp 시간 변경없이하기
cp -p [소스파일] [타겟파일]
```

### ⭐ gzip, tar
> 압축, 풀기
```shell
# gzip 압축
gzip test.txt
# gzip 풀기
gzip -d test.txt.gz
# tar 묶기
tar -cvf test.tar *.txt
# tar 풀기
tar -xvf test.tar
```

### ⭐ touch
> touch my body
```shell
# 다른파일 timestamps 동일하게 맞추기(-r옵션)
touch -r [시간을 가져올파일] [시간을 수정할 파일]
```

### ⭐ nc
> arbitrary TCP and UDP connections and listens
```shell
# 방화벽확인(telnet 대신)
nc -z -v 218.238.92.171 9050
```

### ⭐ chmod, chgrp, chown 
> change access control, change group, change owner
```shell
#※ -R 은 하위파일 모두 변경
chmod -R 755 test.txt
chown -R [계정id] *
chgrp -R [그룹id] *
```

### ⭐ df, du
> display free disk space, display disk usage statistics
```shell
df -h
du -h
```
