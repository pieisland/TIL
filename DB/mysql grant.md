mysql 8 버전에 대해서 grant 권한을 주는 문법이 변경됐다.     
자세한 사항은 홈페이지를 보면 된다.   
https://dev.mysql.com/doc/refman/8.0/en/grant.html

# 데이터베이스에 권한 주기
> grant all on mydb.* to 'someone'@'somehost';   

데이터베이스 mydb에 대해서 모든 권한을 준다.
someone의 somehost에 대해서...

부분적 권한을 준다면 all을 주는 게 아니라 주려는 것을 언급하면 된다.
> grant select, insert on mydb.* to 'someone'@'somehost';

# 테이블에 권한 주기
> grant all on mydb.mytbl to 'someone'@'somehost';
> 
마찬가지다. 특정 테이블에 대해 일부 권한만 주고 싶다면

> grant select, insert on mydb.mytbl to 'someont'@'somehost';

하지만 슬픈 것은 내가 원하는 대로 되지 않았다는 점이다.    
저번에 본 거는 grant all privileges on... 했었는데 privilege 안 붙여도 되는가봄..   
ㅜㅜ

## flush privileges란?
flush privileges는 grant 테이블을 reload 하여 변경사항을 바로 적용해주는 명령어이다.   
grant 명령어를 사용해 사용자를 추가하거나 권한 등을 변경했다면 굳이 실행할 필요가 없다고 한다.
(insert, update와 같이 유저를 추가할 수도 있으니까.)
