## 1. ajax로 post 보내기

```
let oReq = new XMLHttpRequest();
let data = {id:dbId, type:myType};

oReq.open("POST", "type");//parameter를 붙여서 보낼수있음. 
oReq.setRequestHeader('Content-Type', 'application/json');
oReq.send(JSON.stringify(data));
```

open에 쓰는 건 get인지 post인지랑 어떤 url로 보낼 것인가를 쓰는 것이다.   
/type 찾아가서 거기 있는 service를 실행하게 된다.   
setRequestHeader에는 저런 거 적어주는데.. 저렇게 하면 json으로 보내지는 듯 하다.   
근데 send할 때는 stringify를 꼭 해야되는 것 같음.   
string으로 보내지만 json 형태라는 걸 알려주는건지 뭔지.   
뭔지는 모르겠음. 일단 그렇게 보내니까 따라했다고..   

저렇게 보내면 request body에 내용이 들어가있다. network 탭을 보면 나올거다.

## 2. servlet에서 json data 읽어오기
이 분의 코드를 그대로 가져다 썼다.   
https://aljjabaegi.tistory.com/154   
request body로부터 json string을 추출해오는 코드이다.   

string으로 넘겼기 때문에 다시 json으로 변환을 해야하는데   
jsonparser랑 jsonobject를 사용했다.   
.. json array 뭐라는 것도 있기는 하던데 그냥 계속 오류나서   
이래저래 찾다가 되는 걸로 정착한 것 같음.   

참고했던 곳은    
https://mandlife.tistory.com/entry/Java-String-%EC%9D%84-json%EC%9C%BC%EB%A1%9C-%EC%89%BD%EA%B2%8C-%EB%B3%80%ED%99%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95
https://zzznara2.tistory.com/673
여기였다. parser, object를 사용해서 변환을 했다. 그리고 get으로 가져올 수 있다는 것도...

```
JSONParser parser = new JSONParser(); 
Object obj = parser.parse(json);
JSONObject jsonObj = (JSONObject) obj;		
						
Integer id = Integer.parseInt((String)jsonObj.get("id"));
String type = (String)jsonObj.get("type");
```

여기서는 try catch 안에 넣어야 빨간줄 안뜬다는 걸 알려줬었고
https://m.blog.naver.com/PostView.nhn?blogId=nateen7248&logNo=220564458532&proxyReferer=https:%2F%2Fwww.google.com%2F

https://kkgram.tistory.com/2
jsonarray도 소개하고있지만 나는 잘 안되어서 그냥 넘어간다.. 어휴

아직도 잘 모르겠는데.. import 한다고 다 되는건지 아니면   
pom.xml에 적어줘야 하는건지.. 모르겠음.   
jar 파일도 따로 받아서 lib 안에 넣어놓기도 했었는데.. 그래야 하는건지 뭔지...;   
