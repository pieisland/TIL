commit 관련해서 global로 .gitmessage.txt를 해뒀더니   
모든 프로젝트에서 그걸 설정해야한다고 하더라.

그다지 필요 없는데 계속 만들어야둬야하는 것도 싫고 해서 없애려고 했다.

근데 설정하는 방법은 많이 나온다만, 수정이나 삭제에 대해서는 나오는 게 없음...

git config --list 로 어떤 설정들이 있는지 확인할 수 있었는데    
그래서 어떡하라고 하는 참에 경로로 가서 바로 삭제할 수 있는 방법을 찾았다.

이 분이 알려주심.   
https://leeborn.tistory.com/entry/git-config-%ED%8C%8C%EC%9D%BC-%ED%99%95%EC%9D%B8-%EB%B0%8F-%EB%B3%80%EA%B2%BD

`C:\Users\USER_NAME\.gitconfig 에 숨김 파일로 있다.`

그래서 그냥 거기 들어갔더니 commit 관련해서 돼있는 게 있어서 바로 삭제하고 나왔다.   
바로 commit이 된다 좋네.

이렇게 열어서 하는 것 말고 명령어로 하는 건 없는건가.

아무튼, 다음에 config 설정할 때 global로 하는 거 말고 따로 하는 거 또 찾아봐야 될 것 같다는 생각이 든다.
