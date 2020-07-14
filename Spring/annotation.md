## Spring Annotation 정리


```java
@Autowired
// 의존성 주입 시 사용한다.

@Controller
// Spring MVC에서 Controller class를 의미한다.

@Required
// 꼭 필요하지 않은 요소들에 대해 정의한다.

@ResponseBody
// 

@RequestBody
// 

@RequestMapping
// url 정의 시 사용한다.
// 요청 받는 형식을 정의하지 않으면, GET 방식이 defualt로 설정된다.

@RequestParam
// 

@RestController
// = @ResponseBody + @Controller
// class 상단에 선언해주면 method마다 @ResponseBody를 붙여 주지 않아도 된다.
// view로 응답하지 않는 controller를 의미한다.

@Service
// Spring MVC에서 Service class를 의미한다.

@Repository
// Spring MVC에서 DAO class를 의미한다.
```