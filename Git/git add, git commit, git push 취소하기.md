# git add, git commit, git push 취소하기_210323
https://gmlwjd9405.github.io/2018/05/25/git-add-cancle.html

## git add 취소하기
- `git reset HEAD [file]` 명령어로 취소 가능.
-  file을 작성하지 않으면 add한 모든 파일을 취소.

## git commit 취소하기
- `git reset HEAD^` 명령어로 취소 가능.
-  마지막 n개를 취소하고 싶다면 `git reset HEAD~n`
-  commit message를 변경하고 싶다면 `git commit --amend` 명령어로 변경 가능.
-  reset 옵션으로 soft, mixed, hard 가 있다. HEAD 앞에 작성한다.
   - --soft: index 보존(add한 상태, staged 상태), 워킹 디렉토리의 파일 보존.
   - --mixed: index 취소(add하기 전 상태, unstaged 상태), 워킹 디렉토리의 파일 보존. default 옵션이다.
   - --hard: index 취소(add하기 전 상태, usntaged 상태), 워킹 디렉토리의 파일 삭제.

## git push 취소하기
...
