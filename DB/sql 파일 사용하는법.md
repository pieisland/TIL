https://semtax.tistory.com/46

ddl.sql, dml.sql을 받았는데, 복붙해서 붙이니까 에러가 좀 났다.   
그래서 몇몇 데이터들이 제대로 안 들어감..

방법을 찾아봐야겠다 싶어 검색을 해봤고 해당 블로그를 발견했다.   
소개해주는 방법이 두 가지가 있었고 첫 번쨰 방법으로 문제 없이 임포 했다.


## 1. mysql 로그인 후 source 파일경로 쳐주기 
`mysql> source 파일경로`

## 2. mysql 로그인 시에 같이 하기
`mysql -h hostname -u user database < 파일경로`

1번이 더 쉬운듯.
