# 21.03.27.
## gitignore 반영 안 될 때
https://medium.com/@kwoncharles/git-gitignore-%EB%B3%80%EA%B2%BD-%EB%B0%98%EC%98%81%ED%95%98%EA%B8%B0-3f0559947c2b
```
git rm -r --cached .
git add .
git commit 
```

gitignore를 초기에 설정해두지 않고 나중에 추가하면 원래 tracking 하던 파일은 캐시에 저장되어 있어서 반영되지 않는 듯 하다.   
그래서 캐시를 지우고 모두 반영해주면 된다.   
고 본 것 같다.

그렇다면 git rm -r --cached가 무슨 의미인지는 아나?   
https://mygumi.tistory.com/103
--cached 옵션은 로컬 저장소에 있는 걸 삭제하지 않을 때 쓴다. 원격 저장소에만 올라가지 않을 뿐이다.  
작업 시에만 쓰는 파일이나 로그 등을 github에 올리지 않기 위해 사용한다.

그러면 git rm --cached target 이렇게 하면 되는걸까??   
폴더에 대해서는 -r 옵션을 붙여줘야 하는 듯 하다.  
그래서 maven 프로젝트에서 target 폴더는 github에 올리지 않아도 되기 때문에   
git rm -r cached target 이라 했다.

근데.. 지금 잘 안되고 있는 중이다.  

추가로 이클립스에서 설정할 수 있는 방법도 있는 것 같다만   
내 이클립스에서는 Team 이 안보인다.. ^0^...   
https://rimkongs.tistory.com/215


