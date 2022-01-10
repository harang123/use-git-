# first - use gitkraken

- Open a repo => 내가 만들어 놓은 레포지토리를 열때 사용
- Clone a repo => 리모트(깃 허브 서버)에서 레포지토리를 gitKraken으로 가져오고 싶을때 사용
- Start a local repo => 로컬 레포지토리를 생성할때 사용

Start a local repo를 눌러서 로컬 레포지토리를 만들때 
- .gitignore Remplate(optional)이 뜻은 깃 허브에 올리고 싶지 않은 파일들을 관리할때가 있다. 각각의 언어마다 기본적으로 올리지 않는 파일들이 있다.(설정 파일 같은 것들) 
   여기서 언어를 선택하면 그런 설정 파일들을 디폴트로 다 잡아준다. -> ignore 파일을 생성해서 그 파일 안에다가 기본적으로 이 프로젝트에서 뭐가 필요한지, 필요없는지를 전부 설정해준다.

- License => 만약에 내가 하는 프로젝트를 오픈소스로 공개하고 싶으면 라이센스가 필요한데 그럴때는 여기서 라이센스를 선택해줘야한다.

- initialize with LFS(선택 체크박스) 에서 LFS는 Large File Storage이다.
깃 허브에서 제공하고있는 큰 파일 보관소를 말한다.


이렇게 레포지토리를 생성하면 선택한 영역에 폴더가 생기고 폴더 안에는 .git폴더와 
README.md 파일이 생성되는 것을 알 수 있다.
git에서 해주는 모든 기능들이 .git디렉토리 안에 들어있다.

### 파일 커밋의 진행 과정

만약 처음 설정해준 디렉토리인 testKraken에 새로운 파일이 생기면 깃 히스토리의 맨 위에 +1이 생기고 그걸 클릭하면 생성된 파일이 어떤것인지 확인할 수 있다.
오른쪽을 보면 Unstaged Files라고 되있는데 이 뜻은 staging되기 전의 파일들이라는 뜻입니다. 여기서 staging이라는 뜻은 commit을 할 파일들을 임시로 저장하는 것을 뜻한다.
여기서 이제 commit을 하면 깃 히스토리에 새로운 히스토리들이 생성된다.
다음으로 gitKraken 디렉토리에서 하나의 파일을 추가로 생성하고 기존에 있던 파일을 수정해 보았더니 깃 히스토리 쨸 윗부분에 연필 모양 1, + 1 이렇게 2개가 표시되는 것을 알 수 있다. 
연필 모양에 숫자는 숫자만큼 수정되었다는 뜻이고 + 숫자는 숫자만큼 새로운 파일이 생겼다는 것을 알 수 있다. 
그 다음으로 쨸 윗부분을 선택하면(연필 1, + 1)또다시 위의 그림처럼 unstaged Files와 staged Files를 나타내주는 스테이지가 표시됩니다.
여기서 보여주는 스테이지는 내가 관리하고 있는 디렉토리에서 이런일이 벌어졌다는 것을 보여준다.
이제 위와 마찬가지로 staged Files로 옮겨준 후 commit을 하게되면 
이렇게 표시가 되는데 이 뜻은 지금 상태가 add test2와 Edit test까지 한 상태를 가리키고 있다는 뜻이다.
이렇게 파일을 수정하거나 생성하다가 빽업을 해놓고 싶으면 commit을 하여 관리를하면 된다.

### 리모트에 레포지토리 생성하기

처음시작할때 뜨는 창인 New Tab부분에서 
왼쪽 메뉴바에서 밑부분에 on GitHub란이 있다. 
그걸 눌러서 들어가면 GitHub.com과
GitHub Enterprise이거 2개만 사용하면 된다. * Local Only는 1강에서 해봣듯이 로컬에서 디렉토리를 만들고 작업할때 사용하는 것이다.
GitHub Enterprise는 기업을 뜻하는 것이므로 사용하지 않고 GitHub.com을 사용한다.
이제 리모트에 새로운 레퍼지토리를 생성하는 것은 로컬과 거의 똑같은데 
Clone after init 체크박스가 있는데 이 뜻은 리모트(깃 허브 서버)에 만드는 레포지토리를 로컬(내 컴퓨터)에도 만든다는 뜻이다.  
2개가 같이 움직일 수 있게 해준다는 뜻이다(동기화) 로컬에서 작업하다가 푸쉬로 올려줄 수 있다는 뜻
push란 리모트에다가 commit한 파일을 올린다는 뜻이다.
반대로 pull은 리모트(깃 서버)에서 파일을 내려 받는 다는 뜻이다.

## git 명렁어 정리

#### 설정과 초기화
1) 전역 사용자명/이메일 구성하기
- git config --global user.name “Your name”
- git config --global user.email “Your email address”

전역 설정 정보 조회
- git config --global - -list

2) 저장소별 사용자명/이메일 구성하기 (해당 저장소 디렉터리로 이동후)
- git config user.name “Your name”
- git config user.email “Your email address”

* 참고로 user 설정이 되어 있지 않으면 Github에 있는 repository에 변경사항을 푸시 한다고 해도 commit count 집계도 안되고 해당 커밋의 작성자 프로필 아이콘도 ? 로 표시되기 때문에 웬만하면 name과 email 주소를 설정하길 추천한다.

3) 저장소별 설정 정보 조회
- git config --list

4) Git의 출력결과 색상 활성화하기
- git config --global color.ui “auto”

5) 새로운 저장소 초기화하기
mkdir /path/newDir
cd /path/newDir
git init

6) 저장소 복제하기
- git clone <저장소 url>

7) 새로운 원격 저장소 추가하기
- git remote add <원격 저장소> <저장소 url>

#### 기본적인 사용법
아래 명령어에서 [ ]는 선택적인 매개변수를 의미한다.
새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기
- git add <파일>
- git commit -m “<메시지>”

파일의 일부를 스테이징하기
- git add -p [<파일> [<파일> [기타 파일들…]]]

add 명령에서 Git 대화 모드를 사용하여 파일 추가하기
- git add -i

수정되고 추적되는 파일의 변경 사항 스테이징하기
- git add -u [<경로> [<경로>]]

수정되고 추적되는 모든 파일의 변경 사항 커밋하기
- git commit -m “<메시지>” -a

작업 트리의 변경 사항 돌려놓기
- git checkout HEAD <파일> [<파일>]

커밋되지 않고 스테이징된 변경 사항 재설정하기
- git reset HEAD <파일> [<파일>]

마지막 커밋 고치기
- git commit -m “<메시지>” - -amend

이전 커밋을 수정하고 커밋 메시지를 재사용하기
- git commit -C HEAD - -amend

#### 브랜치

지역 브랜치 목록 보기
- git branch

원격 브랜치 목록 보기
- git branch -r

지역과 원격을 포함한 모든 브랜치 목록 보기
- git branch -a

현재 브랜치에서 새로운 브랜치 생성하기
- git branch <새로운 브랜치>

다른 브랜치 체크아웃하기
- git checkout <브랜치>

현재 브랜치에서 새로운 브랜치 생성하고 체크아웃하기
- git checkout -b <새로운 브랜치>

다른 시작 지점에서 브랜치 생성하기
- git branch <새로운 브랜치> <브랜치를 생성할 위치>

기존의 브랜치를 새로운 브랜치로 덮어쓰기
- git branch -f <기존 브랜치> [<브랜치를 생성할 위치>]

브랜치를 옮기거나 브랜치명 변경하기
- git checkout -m <기존 브랜치> <새로운 브랜치>
 - <새로운 브랜치>가 존재하지 않을 경우
- git checkout -M <기존 브랜치> <새로운 브랜치>
 - 무조건 덮어쓰기

다른 브랜치를 현재 브랜치로 합치기
- git merge <브랜치>

커밋하지 않고 합치기
- git merge - -no-commit <브랜치>

선택하여 합치기
- git cherry-pick <커밋명>

커밋하지 않고 선택하여 합치기
- git cherry-pick -n <커밋명>

브랜치의 이력을 다른 브랜치에 합치기
- git merge - -squash <브랜치>

브랜치 삭제하기
- git branch -d <삭제할 브랜치>
 - 삭제할 브랜치가 현재 브랜치에 합쳐졌을 경우에만
git branch -D <삭제할 브랜치>
 - 삭제할 브랜치가 현재 브랜치에 합쳐지지 않았어도

#### Git 이력

모든 이력 보기
- git log

변경 사항을 보여주는 패치와 함께 로그 표시하기
- git log -p

1개의 항목만 보이도록 로그 개수 제한하기
- git log -1

20개의 항목과 패치만 보이도록 로그 제한하기
- git log -20 -p

6시간 동안의 커밋 로그 보기
- git log - -since=”6 hours”

이틀 전까지의 커밋 로그 보기
- git log - -before=”2 days”

HEAD보다 세 개 이전의 커밋 로그 보기
- git log -1 HEAD-3
- git log -1 HEAD^^^
- git log -1 HEAD~1^^

두 지점 사이의 커밋 로그 보기
- git log <시작 지점>…<끝 지점>

시작 지점이나 끝 지점은 커밋명, 브랜치명, 혹은 태그명이 될 수 있고 조합하여 사용 가능하다.

각 항목의 로그 이력 한 줄씩 보기
- git log - -pretty=oneline

각 항목마다 영향 받은 줄의 통계 보기
- git log - -stat

커밋할 시점의 파일 상태 보기
- git log - -name-status

현재 작업 트리와 인덱스의 차이점 보기
- git diff

인덱스와 저장소의 차이점 보기
- git diff - -cached

작업 트리와 저장소의 차이점 보기
- git diff HEAD

작업 트리와 특정 위치 간의 차이점 보기
- git diff <시작 지점>
 - 시작 지점은 커밋명 or 브랜치명 or 태그명이다.

저장소의 두 지점 사이의 차이점 보기
- git diff <시작 지점> <끝 지점>

차이점의 통계 보기
- git diff - -stat <시작 지점> [<끝 지점>]

파일의 커밋 정보 줄 단위로 보기
- git blame <파일>

파일의 줄 단위의 복사, 붙여 넣기, 이동 정보 보기
- git blame -M <파일>

파일의 줄 단위의 이동과 원본 파일 정보 보기
- git blame -C -C <파일>

로그에서 복사와 붙여 넣은 정보 보기
- git log -C -C -p -1 <특정 지점>

#### 원격 저장소
저장소 복제하기
- git clone <저장소>

마지막 200개의 커밋만 포함하여 저장소 복제하기
- git clone - -depth 200 <저장소>

새로운 원격 저장소 추가하기
- git remote add <원격 저장소> <저장소 url>

모든 원격 브랜치 목록 보기
- git branch -r

원격 브랜치에서 지역 브랜치 생성하기
- git branch <새로운 브랜치> <원격 브랜치>

원격 태그에서 지역 브랜치 생성하기
- git branch <새로운 브랜치> <원격 태그>

origin 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
- git fetch

원격 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
- git fetch <원격 저장소>

원격 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
- git pull <원격 저장소>

origin 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
- git pull

지역 브랜치를 원격 브랜치에 푸싱하기
- git push <원격 저장소> <지역 브랜치>:<원격 브랜치>

지역 브랜치를 동일한 이름의 원격 브랜치에 푸싱하기
- git push <원격 저장소> <지역 브랜치>

새로운 로컬 브랜치를 원격 저장소에 푸싱하기
- git push <원격 저장소> <지역 브랜치>

원격 저장소에서 쓸모가 없어진 원격 브랜치 제거하기
- git remote prune <원격 저장소>

원격 저장소를 제거하고 관련된 브랜치도 제거하기
- git remote rm <원격 저장소>

gitkraken 이후로는 매일 1시간 정도 명령어 써보면서 git 익히기 (명령어들 정의만 한번 읽어본 상황) 
****




