# 21.03.27.
## gitignore 반영 안 될 때
```
git rm -r --cached
git add .
git commit 
```

gitignore를 초기에 설정해두지 않고 나중에 추가하면 원래 tracking 하던 파일은 캐시에 저장되어 있어서 반영되지 않는 듯 하다.   
그래서 캐시를 지우고 모두 반영해주면 된다.   
고 본 것 같다.
