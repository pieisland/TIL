# 부스트코스 웹 프로그래밍 Spring JDBC 실습_21.03.24

## ApplicationConfig
import annotation은 설정 파일을 여러 개로 나눠서 작성할 수 있게 해준다.   
설정 파일 하나에 모든 것을 넣는 게 아니라 db 연결관한 설정은 따로 뺴고 싶어서   
ApplicationConfig에서 DBConfig를 Import 해올거라는 의미겠지.   

## DBConfig
DBConfig class를 새로 만들어서  
마찬가지로 @Configuration 해주고   
트랜잭션 관련해서 @EnableTransactionManagement 도 붙여줬다.

## 여러개 select
jdbc.query(쿼리문, Collections.emptyMap(), rowMapper);   
셀렉트 한 건 한 건의 결과를 dto에 저장하는 목적으로 rowMapper를 사용한다.   
BeanPropertyRowMapper   
컬럼의 값을 자동으로 dto에 담아준다.     
결과가 여러 건일 때 내부적으로 반복하면서 dto 생성하고 list에 담아주고 반환함.   
dbms와 java 이름 규칙을 맞춰준다.   
그래서 select 할 때 rowMapper 쓰면 된다는 거죠?
```
	public List<Role> selectAll(){
		return jdbc.query(SELECT_ALL, Collections.emptyMap(), rowMapper);
	}
```

@ComponentScan
으로 @Repository가 붙어있는 걸 등록해준다.

## insert, update
sqlParameterSurce가 값 들어가야 하는 부분을 map으로 바꿔준다...?   
아무튼 update할 때 : 한 부분에 맞게 넣어준다.

insert할 때는 simpleJdbcInsert라는 걸 사용한거고   
update는 그냥 NamedParameterJdbcTemplate를 사용했다.

```
@Repository
public class RoleDao {
	private NamedParameterJdbcTemplate jdbc;
	private SimpleJdbcInsert insertAction;
	private RowMapper<Role> rowMapper = BeanPropertyRowMapper.newInstance(Role.class);

	public RoleDao(DataSource dataSource) {
		this.jdbc = new NamedParameterJdbcTemplate(dataSource);
		this.insertAction = new SimpleJdbcInsert(dataSource)
                .withTableName("role");

	}
	
	public int insert(Role role) {
		SqlParameterSource params = new BeanPropertySqlParameterSource(role);
		return insertAction.execute(params);
	}

	public int update(Role role) {
		SqlParameterSource params = new BeanPropertySqlParameterSource(role);
		return jdbc.update(UPDATE, params);
	}
	

}
```

## delete
delete 문에서는 SqlParameterSource 객체를 사용하는 대신(어차피 map으로 변환을 해주는데)   
파라미터가 하나 뿐이기 때문에 바로 Map을 사용했다고 하는 것 같다.      
그리고 쓸 때는 마찬가지로 namedParameterJdbcTemplate의 update를 사용한다. delete 자체는 없는 듯 하다.  

```
	public int deleteById(Integer id) {
		Map<String, ?> params = Collections.singletonMap("roleId", id);
		return jdbc.update(DELETE_BY_ROLE_ID, params);
	}
```

## 한 건 select
여러 건을 select 하는 게 아닌, 한 건을 select 할 때는 야간 다르게 한다.   
소개해준 방법은 singletonMap을 사용했다.. key 값인 id를 사용하고 queryForObject를 썼다. 하나만 return 해주나봄.   
select 했을 때 값이 없으면 EmptyResultDataAccessException이 발생하게 된다.       
그래서 try catch로 잡아줘야 한다.   

```
	public Role selectById(Integer id) {
		try {
			Map<String, ?> params = Collections.singletonMap("roleId", id);
			return jdbc.queryForObject(SELECT_BY_ROLE_ID, params, rowMapper);		
		}catch(EmptyResultDataAccessException e) {
			return null;
		}
	}

```
