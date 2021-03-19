https://m.blog.naver.com/10hsb04/221659315804

여기가 제일 많이 도움이 됐다.

ini가 어디 있나 해는데 exe 있는 위치에 있다.   
초기에 확장자명 보이는 게 아니라서 없는 줄 알았다.

아무튼 간에,    
-vmargs
-Xbotclasspath/a:lombok.jar
-javaagent:lombok.jar

이거를 추가해주면 된다.

솔직히 이걸 추가해서 된 건지, import를 해서 된 건지 모르겠음.

빨간 줄 떠서 뭐임? 했는데 저장하니까 자동 import 되면서 됐음...

하지만 data를 쓰는 건 좋지 않다고 했기 때문에 결국 바꿔야 한다는 소리겠지. 
