잘 모르겠다만. 어떻게 만들기는 했다.

mdn transition을 보니까, transition에는 이러한 값들을 설정할 수 있다고 한다.   
`transition: property duration timing-function delay;`

css style은 문자열로 넣어줘야 된다고요?

target.style.transform = "scale(2)"; 이런식으로 하라고 하네요.   
target.style.left = "300px";

transition: all 2s;   
transition: transform 2s;

... ... 별 도움은 안 된 듯.

```
<css>

.outside {
	position:relative;
	transform:scale(1); //이거 지금은 없어도 되는 거 맞죠..?
	transition: left 1s ease-in;
}
```

```
<js>

const target = document.querySelector(".outside");
const btn = document.querySelector("button");
btn.addEventListener("click", ()=>{
	let pre = parseInt(target.style.left);
	target.stlye.left = pre + 100 + "px";
}); 
```

```
<html>
<div class="outside" style="left:100px">object</div>

inline으로 style을 넣어줘야 뽑힌다. 그래서 좀 넣어줌..

```


transform에 left를 주는 형식으로 했는데 translate를 쓰는 게 더 좋다고 합니다.   
  
하드웨어 가속 관련된 것도 있습니다.    
.... 네... 나중에 읽어보시거나 하세요.  

vendor prefix라는 게 있다고 한다. 뭔지는 모르겠다.   
 
