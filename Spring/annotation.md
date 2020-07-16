## Spring Annotation 정리
> 몰랐던 Annotation 발견 시 계속 기록하자!


* __DI__
```java
@Autowired
// 의존성 주입 시 사용한다.
// Type을 먼저 확인 후 못 찾으면 Name에 따라 의존성 주입한다.

@Required
// 꼭 필요하지 않은 요소들에 대해 정의한다.
```


* __component__
```java
@Component
// @Controller, @Service, Repository의 상위 개념!

@Controller
// Spring MVC에서 Controller class를 의미한다.

@Service
// Spring MVC에서 Service class를 의미한다.

@Repository
// Spring MVC에서 DAO class를 의미한다.
```


* __Controller__
```java
@PathVariable
// url에서 '/'로 구분되는 값(url mapping에서 {}안의 값)을 가져온다.
// 주로 REST API에서 주로 쓰인다.
// @PathVariable + @RequestParam 같이 사용 가능

@ResponseBody
// view말고 JSON/XML 형태로 반환할 때 사용.
// @RestController 사용 시 안 붙혀줘도 된다.
// 일반 Controller에서는 HttpResponse로 응답하게 한다.

@RequestBody
// HTTP POST 요청에 대해서만 처리한다.
// 요청에 대해 requestbody에 있는 requestmessage에서 값을 얻어와 매칭한다.

@RequestMapping
// url 정의 시 사용한다.
// 요청 받는 형식(method값)을 정의하지 않으면, GET 방식이 defualt로 설정된다.

@RequestParam
// HTTP GET 요청에 대해 파라미터 값을 가져온다.
// * url뒤의 파라미터 값
// ex)
public void test(@RequestParam("전달되는 실제 변수 이름") int id) {
    ...
}

@RestController
// = @ResponseBody + @Controller
// class 상단에 선언해주면 method마다 @ResponseBody를 붙여 주지 않아도 된다.
// view로 응답하지 않는 controller를 의미한다.
// 메소드 반환 결과를 JSON 형태로 반환한다.
```


* __Lombok__
```java
@Data
// getter, setter, tostring을 포함하는 필드와 관련된 코드를 생성한다.

@ToString
// 필드 값을 출력한다.
// @ToString(exclude = "data") => 'data' 필드를 출력에서 제외한다.
```