## 😈git from the hell😈 __ From Youtube channel '생활코딩'
## 파일 및 폴더 조작을 위한 명령어

pwd : 현재 내가 위치한 디렉토리의 주소를 알려줌

mkdir 'folder name' : 디렉토리를 생성

cd 'folder name' : 해당 폴더로 이동

ls -al : 현재 위치한 폴더 하위의 파일 및 폴더를 보여줌

cat 'file name' : 파일의 내용을 출력함

cp 'existing file name' 'new name want to make' : 현재 존재하는 파일을 복사하여 이름만 다른 새로운 파일을 생성함
-> copy를 활용하더라도 내용이 같으면 같은 위치에 저장됨.(같은 내용의 중복 저장을 피하기 위함)

---
## git을 활용하기 위한 명령어

git init : git을 사용하기 위한 폴더를 지정 (.git 이라는 디렉토리가 생성됨)

git clone : git hub 등의 온라인 환경에서 clone하여 로컬 환경과 연동

git clone 'url' . : 별도의 디렉토리를 선정하지 않고 현 위치에 clone

git clone 'url' 'dir name want to make' : github에서 fork 후 관련 자료를 자신의 로컬 디렉토리에 저장함

git status : 현재 폴더의 관리 상태를 보여주는 명령어

---

## About 'add'
vim 'file name want to make' : vim 을 활용하여 파일 생성 및 내용 수정 -> 현재 존재하는 파일 이름을 입력할 경우 파일 내용 수정할 떄 사용
-> 입력모드로 바꿀때는 'i' 모드를 종료할떄는 'esc' 내용을 저장하고 vim에서 나갈때는 ':wq'를 입력

git add 'file name' : 특정 파일을 stage 영역으로 ( git을 활용해 관리하기 시작한다! -> 파일의 변화에 대해서 트래킹[추적]이 시작됨!)

#### 주의할 점 : 같은 파일이라도 변화가 생겼을 떄는 새로운 버전이기 떄문에 git add를 해줘야함!

---

## About 'commit'

git commit : 파일의 버전(의미있는 변화가 완결된 상태)  만들기,  vim이 실행됨 -> 변화된 내용이 어떤 내용인지 간단히 명시해줌
-> add를 통해 stage에 올라온 파일들만  commit되는 것이기 때문에, 필요한 파일만 stage에 올려서 commit하면 되는것이다!

git log : 변화된 내용들의 log를 출력함

git log -p : 모든 commit과 commit 사이사이 달라진 점을 표시해줌! (어떤점이 달라졌니?)

git log 'commit id' : 해당 commit 이전의 commit의 log만 출력

git log --reverse : log의 출력 순서를 반대로!

git diff : 현재 실시한 작업이 이전 commit과 어떻게 다른지 출력

git diff 'commit id1'..'commit id2' : 두 commit 사이의 차이점을 출력해줌 

git reset 'commit id' --hard: log에서 commit id를 확인한 뒤 이 명령어를 사용하면 해당 commit 시점으로 복귀!
#### reset과 같은 기능을 하는 revert도 있으니 나중에 추가로 공부합시다! reset과 revert보다는 commit들간의 차이를 확인하는게 더 중요

git commit -a : 수정된 파일을 add 후 commit

git commit -m 'message' : 별도의 에디터 실행 없이 메세지를 입력함

git commit -am 'message' : -a와 -m옵션 동시에 실행함
#### 주의할 점 : 새로운 파일이 아니라 한 번 이상 commit 된 파일에 한해서만 이 옵션 사용 가능?

## About 'branch'
git brach : 현재 사용하고 있는 branch를 보여줌

git branch 'name' : 새로운 'name'의 branch가 생성됨 -> 원 위치의 branch와 내부 구성이 동일함

git checkout 'branch name' : 입력한 브랜치로 변경

git log --branches --decorate --graph --oneline
 -- branches : 현재 위치한 branch 외의 다른 branch도 표시
 -- decorate : 각 branch별 최신 commit 표시?
 -- graph : 그림 형태로 branch 분기 시각화
 -- oneline : 간단하게 한줄로 분기를 시각화해줌
 
 git log 'branch name 1'..'branch name 2' : branch 1에는 없고 branch 2에는 있는것 -> 두 branch의 입력 순서를 달리하면 출력 결과가 달라짐 
 
 git log -p 'branch name 1'..'branch name 2' : branch 1에는 없고 branch 2에는 있는것을 정확한 소스코드까지 알고싶을 때
 
git diff 'branch name 1'..'branch name 2' : branch 1에는 없고 branch 2에는 있는 두 branch사이의 차이를 알고싶을 때
