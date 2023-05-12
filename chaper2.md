---
marp: true
theme: gaia
title: Session#2
_class: lead
backgroundColor: #fff
---
# HeXA-Beginner-Study #2
## Shell(`bash`)와 Vim 에디터
---
# Before Get Started
## What is *Shell*?
- 
---
# Before Get Started
## SSH
- **S**ecure **S**hell **H**ost
- Secure: Use Secure Connection
- Shell: Connect via Shell
- Host: To Host
---
## Host?
---
## Use SSH
- Using Shell
```bash
 ssh username@host -p [port_number]
```
- Using Application
    - For example, PuTTY
---
# Shell
- :shell:
- 껍데기
- 커널을 **보호**
- 유저와 컴퓨터 사이의 **상호작용**을 관리

---
## If You Are Connected Successfully...
```bash
username@host:~$
```
Describing this,
```bash
username: Current user name
@host: Current host name
~: Current Working Directory
$: privilege (# stands for root)
```
---
## Command to the Shell
```bash
ausername@host:~$ [실행 경로]실행 파일 [-[옵션]..[옵션] | --[긴 옵션]] [명령 인자]..[명령 인자]

#참고1: []안 내용은 생략 가능합니다.
#참고2: ..는 N개를 의미합니다.
```   
- `-` option vs. `--` option?
---
## Command to the Shell
```bash
username@host:~$ ls
#ls라는 파일을 호출
username@host:~$ ls -a
#ls라는 파일을 a옵션으로 호출
username@host:~$ ls -al
#ls라는 파일을 a와 l옵션을 사용하여 호출
username@host:~$ ls -all
#ls라는 파일을 a, l, l 옵션을 사용하여 호출
#(l 중복, 따라서 -al 사용과 같은 결과)
username@host:~$ ls --all
#ls라는 파일을 all 옵션을 사용하여 호출
username@host:~$ ls ~/Desktop
#ls라는 파일을 ~/desktop이라는 인자를 사용하여 호출
username@host:~$ ls -al ~/Desktop
#ls라는 파일을 a와 l 옵션을 사용하여 ~/desktop 인자와 함께 호출
```
---
## Path
- `~/HeXA-Beginner-Study`??
- `/home/username/HeXA-Beginner-Study`???
---
## Path
- `.`: 현재 디렉토리
- `..`: 상위(부모 디렉토리)
- `/`: 폴더간 구분문자(단, 경로 맨 앞에 위치할 경우 최상위(root) 폴더)
- `~`: 홈 폴더
```bash
./hexa #현재 폴더 하위에 있는 hexa 폴더 혹은 파일
./hexa1/hexa2 #현재 폴더 하위에 있는 hexa1 폴더 속 hexa2 폴더 혹은 파일
../hexa0 #현재 폴더 상위에 있는 hexa0 폴더 혹은 파일
~/hexa #홈폴더 속 hexa 파일 혹은 폴더
/hexa #Root(최상위) 폴더 속 hexa 파일 혹은 폴더
```
---
## PWD
- Print Working Derectory
- 상대경로 vs. 절대경로

```bash
~/HeXA-Beginner-Study <--??
/home/username/HeXA-Beginner-Study <--???
```
---
## `>`, `<`, `|`
```bash
echo hello #실행 결과: hello
           #echo: 뒤의 내용을 그대로 표시
echo hello > hello.txt #echo hello의 결과를 hello.txt에 넣기
cat < hello.txt #cat 명령어에 hello.txt의 내용을 넣기
##cat <(echo hello) # cat 명령어에 echo hello의 결과를 넣기
echo hello | echo hi #echo hello를 실행한 후, echo hi를 실행
```
---
## USEFUL COMMANDS
- ls
- cd
- mkdir
- rm
- alias
- cat
- jobs
- kill
- ...
--- 
## Vim
- CLI(Command Line Interface) 환경에서는 Vim(**Vi**, i**m**proved) 에디터를 사용하는 것이 일반적

---
## History of Vim
### Teletype
- 전신타자기
- 모니터x
- **줄** 단위 정보 교환
    -  Command **Line** Environment
- `\r\n`

---
## History of Vim
### Visual Editor(Vi)
- 모니터의 등장
### Vi &rarr; Vim
- Vi 호환 에디터
- 커스터마이징

---
## Vim
```bash
username@host:~$ vi             # 빈 vim 에디터를 실행합니다.
username@host:~$ vi [파일 이름] # 해당 파일을 vim 에디터로 실행합니다.
                               # 해당 파일이 존재하지 않는 경우, 새 파일을 만들고 엽니다
```
---
## Vim Modes
- Insert
- Command
- Replace
- Visual
- ...