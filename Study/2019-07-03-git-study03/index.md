---
layout: post
title:  "Git을 공부해보자!"
subtitle: "Git 주요 명령어 및 사용법"
type: "Git"
study: true
text: true
author: "Song LEEE"
---

<p class="txt_point">Git 은 아무리 이론적으로 공부를 해봐도 정말 모르겠다ㅠㅠ 계속 부딪혀보고 여러번 해봐야 아 이 명령어가 이때 쓰이는구나, 이 원리구나 하고 알 수 있다. </p>
<p class="txt_point">오죽하면 계속 충돌 나서 도와주시는 분이 이정도면 면허취소 수준이라고 했을까... 따흐흑 아직도 갈길이 멀다.</p>

<br>

<strong>환경설정</strong>

1. <p class="txt_point02">git config --global --list</p> 현재 설정 정보를 조회할 수 있다. --global 옵션은 전역 설정에 대한 옵션이며 현재 프로젝트에만 적용할 때는 주지 않는다.
2. <p class="txt_point02">git config --global user.name "사용자명"</p> 사용자 명을 등록한다 (필수)
3. <p class="txt_point02">git config --global user.email "이메일 주소"</p> 이메일 주소를 등록한다 (필수)
4. <p class="txt_point02">git config --global color.ui "auto"</p> 터미널에 표시되는 메세지에 컬러를 표시해줌

<br>
<br>
<br>

<strong>git 에 대해 사전에 알아야 될 부분들</strong>

1. git 의 저장소는 3가지 단계로 나누어 진다. 커밋한 소스가 보관되는 저장소와 현재 프로젝트 파일이 있는 작업트리 저장소와 작업트리 사이의 버퍼영역으로 커밋될 대상이 저장되는 스테이징 영역이다.
2. git 은 빈 디렉토리는 추적하지 않는다.
3. 형상관리를 하지 안히을 파일은 git ignore 파일에 추가한다.
4. HEAD는 현재 브랜치의 가장 최신 커밋을 의미한다.
5. 기본 원격 저장소를 origin 이라고 부른다.

<br>
<br>
<br>

<strong>기본적인 명령어</strong>

1. <p class="txt_point02">git --version</p> 현재 git 의 버전을 확인한다.
2. <p class="txt_point02">git init</p> 현재 디렉토리에 git 저장소를 생성한다.
4. <p class="txt_point02">git add 파일명</p> git add 는 두가지를 하는데 untracked files 의 파일들을 git 이 추적하도록 하거나 파일은 수정했지만 아직 스테이징 영역에 올라가지 않은 <br> (Changed but not updated) 파일들을 스테이징 영역에 올린다. -i 옵션을 주면 대화형 모드가 시작되어 파일의 일부분만 선택해서 스테이징 하는게 가능하다. -p 옵션을 사용하면 -i 대화형 모드없이 <br> 바로 패치모드를 사용할 수 있다.
5. <p class="txt_point02">git commit -m '커밋 메세지'</p> 스테이징 영역에 올라가 있는 파일들을 커밋한다. -m 은 커밋 메세지를 주는 옵션으로 여러줄의 커밋메세지를 쓸 경우 -m을 여러개 사용할 수 있다. -a 옵션을 사용하면 스테이징에 올리는 작업과 커밋을 동시에 할 수 있다. (추적되지 않는 파일은 추가하지 않는다.) -m을 사용하지 않을때 -v 옵션을 사용하면 편집기에 커밋을 하려는 변경사항의 다른점을 보여준다. 특정파일만 커밋하려면 마지막에 파일명을 추가해주면 된다.
6. <p class="txt_point02">git commit -C HEAD -a --amend</p> 지정한 커밋의 로그메세지를 다시 사용하여 기존커밋을 수정한다. -c를 사용하면 기존 메세지를 수정할 수 있는 편집기를 실행해준다.
7. <p class="txt_point02">git status</p> 커밋되지 않은 변경사항을 조회한다.
8. <p class="txt_point02">git diff</p> 스테이징 영역과 현재 작업트리의 차이점을 보여준다. --cached 옵션을 추가하면 스테이징 영역과 저장소의 차이점을 볼 수 있다. git diff HEAD 를 입력하면 저장소, 스테이징영역, 작업트리의 차이점을 모두볼 수 있다. 파라미터로 log 와 동일하게 범위를 지정할 수 있으면 --stat를 추가하면 변경사항에 대한 통계를 볼 수 있다. 
9. <p class="txt_point02">git mv 파일명 새 파일명</p> 기존에 존재하는 파일을 새 파일로 이동한다. 변경이력은 그대로 유지한다.
10. <p class="txt_point02">git checkout --파일명</p> 아직 스테이징이나 커밋을 하지 않은 파일의 변경내용을 취소하고 이전 커밋 상대로 돌린다. svn에서 revert 와 동일!

<br>
<br>
<br>

<strong>branch 와 tag</strong>

1. <p class="txt_point02">git branch</p> 현재 존재하는 브랜치를 조회한다. -r 옵션을 사용하면 원격저장소의 브랜치를 확인할 수 있다.
2. <p class="txt_point02">git branch 브랜치명B 브랜치명A</p> 브랜치명A에서 새로운 브랜치 브랜치명B를 만든다. (git에서 기본 브랜치는 master 라는 이름을 사용한다.)
3. <p class="txt_point02">git branch 브랜치명</p> 브랜치명의 새로운 브랜치를 만든다.(체크아웃은 하지 않음)
4. <p class="txt_point02">git branch -d 브랜치명</p> 브랜치를 삭제한다.
5. <p class="txt_point02">git branch -m 존재하는 브랜치명 새로운 브랜치명</p> 존재하는 브랜치를 새로운 브랜치로 변경한다. 이미 존재하는 브랜치명이 있을 경우에는 에러가 나는데 -m 옵션을 사용하면 이미 있는 브랜치의 경우에도 덮어 쓴다.
6. <p class="txt_point02">git tag 태그명 브랜치명</p> 브랜치명의 현재 시점에 태그명으로 된 태그를 붙인다. git tag 만 입력하면 현재 존재하는 태그 목록을 볼 수 있다.
7. <p class="txt_point02">git checkout 브랜치명/태그명</p> 해당 브랜치나 캐그로 작업 트리를 변경한다.
8. <p class="txt_point02">git checkout -b 브랜치명B 브랜치명A</p> 브랜치명A에서 브랜치명B라는 새로운 브랜치를 만들어서 체크아웃을 한다.
9. <p class="txt_point02">git rebase 브랜치명</p> 브랜치명의 변경사항을 현재 브랜치에 적용한다.
10. <p class="txt_point02">git merge 브랜치명</p> 브랜치명의 브랜치를 현재 브랜치로 합친다. --squash 옵션을 주면 브랜치명의 모든 커밋을 하나의 커밋으로 만든다.
11. <p class="txt_point02">git cherry-pick 커밋명</p> 커밋명의 특정 커밋만을 선택해서 현재 브랜치에 커밋으로 만든다. -n 옵션을 주면 작업 트리에 합치지만 커밋은 하지 않기 때문에 여러개의 커밋을 합쳐서 커밋할 수 있다.

<br>
<br>
<br>

<strong>로그관리</strong>

1. <p class="txt_point02">git log</p> 커밋 로그들을 볼 수 있으면 -1나 -2같은 옵션을 주어 출력할 커밋로그의 갯수를 지정할 수 있다. --pretty=oneline 옵션을 주면 한줄로 간단히 보여주고 __pretty=format"%h %s"처럼 형식을 정해줄 수 있다. -p 옵션을 사용하면 변경된 내용을 같이 보여준다. --since="5 hours"나 --before="5hours" 같은 옵션도 사용 가능하다. --graph 옵션을 주면 브랜치 트리를 볼 수 있다.
2. <p class="txt_point02">git log 커밋명</p> 해당 커밋명의 로그를 볼 수 있다. 커밋명A..커밋명B (마침표2개)와 같이 입력하면 커밋명A 이후부터 커밋명B 까지의 로그를 볼 수 있다. ^은 -1과 동일해서 HEAD^ 라고 하면 최신 바로 이전 커밋이고 HEAD^^^와 같이 쓸 수 있으며 HEAD~3을 하면 HEAD의 3개 이전의 커밋을 뜻한다. 
3. <p class="txt_point02">git blame 파일명</p> 해당 파일의 수정이력을 볼 수 있고, 커밋해시값, 수정한 사람, 수정 이력이 남겨진 시간, 커밋 메세지를 확인할 수 있다. 
4. <p class="txt_point02">git blame -L 10,15 파일명</p> -L 옵션을 사용하면 10줄부터 15줄로 범위를 지정해서 볼 수 있고 15대신 +5와 같이 사용할 수 있다. 숫자의 범위 대신 정규식도 사용이 가능하다.
5. <p class="txt_point02">git blame -M 파일명</p> -M 옵션을 사용하면 반복되는 패턴을 찾아서 복사하거나 이동된 내용을 찾아준다. -C -C 옵션을 사용하면 파일간의 본사한 경우를 찾아준다. -C -C는 git log 에서도 사용가능 하며 내용의 복사를 찾을때는 git log 에서 -p 옵션을 사용한다.
6. <p class="txt_point02">git revert 커밋명</p> 기존의 커밋에서 변경한 내용을 취소해서 새로운 커밋을 만든다. -n 옵션을 사용하면 바로 커밋하지 않기 때문에 revert 를 여러번 한 다음에 커밋할 수 있다.(항상 최신의 커밋으로부터 revert 해야한다.)
7. <p class="txt_point02">git reset 커밋명</p> 이전 커밋을 수정하기 위해서 사용한다. --soft 옵션을 사용하면 이전 커밋읋 스테이징 하고 커밋은 하지 않으며 --hard 옵션은 저장소와 작업트리에서 커밋을 제거한다. git reset HEAD^ 와 같이 입력하면 최근 1개의 커밋을 취소할 수 있다.
8. <p class="txt_point02">git rebase -i 커밋범위</p> -i 옵션으로 대화형 모드로 커밋 순서를 변경하거나 합치는 등의 작업을 할 수 있다.

<br>
<br>
<br>

<strong>원격 저장소</strong>

1. <p class="txt_point02">git clone 저장소주소 폴더명</p> 원격 저장소를 복제하여 저장소를 생성한다. 폴더명은 생략 가능하다.
2. <p class="txt_point02">git fetch</p> 원격 저장소의 변경사항 가져와서 원격 브랜치를 갱신한다. 
3. <p class="txt_point02">git pull</p> git fetch에서 하는 원격저장소의 변경사항을 가져와서 지역브랜치에 합치는 작업을 한꺼번에 한다. 파라미터로 풀링할 원격저장소와 반영할 지역 브랜치를 줄 수 있다.
4. <p class="txt_point02">git push</p> 파라미터를 주지 않으면 origin 저장소에 푸시하며 현재 지역브랜치와 같은 이름의 브랜치에 푸시한다. --dry-run 옵션을 사용하면 푸시된 변경사항을 확인할 수 있다. 로컬에서 tag를 달았을 경우에 기본적으로 푸시하지 않기 때문에 git push origin 태그명이나 모든 태그를 올리기 위해서 git push origin --tags를 사용해야 한다.\
5. <p class="txt_point02">git remote add 이름 저장소 주소</p> 새로운 원격 저장소를 추가한다.
6. <p class="txt_point02">git remote</p> 추가한 원격 저장소의 목록을 확인할 수 있다.
7. <p class="txt_point02">git remote show 이름</p> 해당 원격저장소의 정보를 볼 수 있다.
8. <p class="txt_point02">git remote rm 이름</p> 원격 저장소를 제거한다.

<br>
<br>
<br>

<strong>서브모듈</strong>

1. <p class="txt_point02">git submodule</p> 연관된 하위모듈을 확인할 수 있다.
2. <p class="txt_point02">git submodule add 저장소주소 서브모듈경로</p> 새로운 하위모듈을 해당경로에 추가한다. 추가만하고 초기화 하지는 않으며 커밋해쉬앞에 마이너스(-) 표시가 나타난다.
3. <p class="txt_point02">git submodule init 서브모듈경로</p> 서브모듈을 초기화 한다.
4. <p class="txt_point02">git submodule update 서브모듈경로</p> 서브모듈의 변경사항을 적용한다.(저장소의 최신커밋을 추적하지 않는다.)

<br>
<br>
<br>

<strong>기타명령어</strong>

<p class="txt_point02">git archive --format=tar --prefix=폴더명 / 브랜치 혹은 태그 | gzip > 파일명.tar.gz</p>
<p class="txt_point02">git archive --format=zip --prefix=폴더명 / 브랜치 혹인 태크 > 파일명.zip</p>
<p>해당 브랜치나 태그를 압축 파일로 만든다. --prefix를 주면 압축 파일이 해당 폴더안에 생성되도록 할 수 있다.</p>

1. <p class="txt_point02">git mergetool</p>설정에 merge.tool의 값에 있는 머지툴을 찾아서 실행한다.
2. <p class="txt_point02">git gc</p> 저장소의 로그를 최적화 한다.. 로그가 변경되지는 않고 저장하는 방식만 최적화 한다. --aggressive 옵션을 주면 더 자세하게 최적화 한다.
3. <p class="txt_point02">git rev-parse --show-toplevel</p> git 저장소내에서 입력하면 루트디렉토리를 알려준다.

<br>
<br>

<p>끝! 쓰면서도 어렵다 하하하</p>