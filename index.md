# Git 사용법

- git init

        현재 디렉토리에 .git 폴더를 추가하고, git이 관리하도록 한다.

- git status

        현재 디렉토리의 변경점들을 표시해준다. 현재 디렉토리 파일들의 추가, 삭제, 내용의 변경 등을 표시한다. 
        크게 Tracked(관리대상), Untracked(비 관리대상)으로 나뉘는데, Tracked 파일은 이미 스냅샷에 포함돼 있는 파일이고, Tracked 파일은 Unmodified(수정하지 않음, 커밋된 상태), Modified(수정함) 그리고 Staged(커밋하기 전) 상태 중 하나이다. 쉽게 git이 알고있는 파일이다.

        그리고 나머지 파일은 모두 Untracked 파일이다. Untracked 파일은 working derectory에 있는 파일 중 스냅샷에도, Staging Area에도 포함되지 않은 파일이다. 처음 저장소를 Clone 하면 모든 파일은 Tracked이면서 Unmodified 상태이다. 파일을 Checkout 하고 나서 아무것도 수정하지 않았기 때문이다.
      

- git add

        git status에 있는 친구들을 커밋하기 바로 전단계로 만들어 준다. staged 상태로 만든다고 보면 된다. 커밋하기 전에 모든 파일들은 staged 상태에 있어야 한다.

- git commit

        staged 상태인 파일들을 커밋해준다. 커밋이란 작업 로그의 한 스냅샷이다. 프로젝트 진행 도중 언제든지 커밋을 통해 전 단계로 돌아갈 수 있다.

- git rm

        파일을 삭제하는 방법이다. 이 명령을 통해 Tracked 상태의 파일을 삭제하고, 물론 커밋해야 한다. 삭제 또한 작업의 변경이력중 하나이기 때문이다. 이렇게 삭제한다면 실제 파일 또한 지워진다. 만약 단순히 로컬에서 파일을 삭제하고 git status를 이용해 확인한다면 "Changes not staged for commit" (즉, Unstaged 상태)라고 표시해준다.

- git reset hashCode --hard

        git log 로 확인한 log의 해쉬코드 앞 6자리를 통해 그 시점으로 리셋한다. 이렇게 하면 그 시점으로 돌아가지만, 작업을 취소할 수 없다.

- git revert hashCode

        돌아간다는 표현보다 취소한다는 표현이 옳다. log를 실행하기 전의 상태로 돌리는 것 이다. 이 또한 커밋을 해줘야 한다. 작업 취소가 가능하다.

- git branch branchName


        작업 환경의 분기점을 만드는 것 이다. 현재 상태의 작업환경을 그대로 가져가며, 각각의 branch 들은 작업할 때 서로 영향을 주지 않는다. 물론 나중에 merge(병합) 작업을 해줄 수 도 있다.


- git merge branchName

        현재 작업 환경에 branchName의 작업환경을 병합시킨다. git log --graph --all --decorate 를 통해 그래프를 볼 수도 있다.
-git merge -D branchName

        다 쓴 브랜치를 제거한다.

- git merge conflict

        m 

- git rebase branchName

        작업환경을 병합할 때, merge와 다르게 한줄로 병합하는 기능

