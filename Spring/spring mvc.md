# Spring MVC를 이용한 웹 페이지 작성 실습

## controller
- @Controller
- @GetMapping
- @PostMapping
  - @RequestParam: 파라미터 쉽게 받아올 수 있다. 이름 설정 가능.

이렇게 form이 있을 때, name이 value1, value2이다.
```
<form method="post" action="plus">  
value1 : <input type="text" name="value1"><br>
value2 : <input type="text" name="value2"><br>
<input type="submit" value="확인"> 
```

PostMapping의 RequestParam에서 name 값에 form에서의 name가 동일하게 해주면 알아서 가져오는 듯 하다.
```
@Controller
public class PlusController {
	@GetMapping(path = "/plusform")
	public String plusform() {
		return "plusForm";
	}

	@PostMapping(path = "/plus")
	public String plus(@RequestParam(name = "value1", required = true) int value1,
			@RequestParam(name = "value2", required = true) int value2, ModelMap modelMap) {
		int result = value1 + value2;

		modelMap.addAttribute("value1", value1);
		modelMap.addAttribute("value2", value2);
		modelMap.addAttribute("result", result);
		return "plusResult";
	}
}

```

해보면 알겠지.
