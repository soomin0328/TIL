## URL 매핑


#### web.xml
```xml
<servlet-mapping>
    <servlet-name>appServlet</servlet-name>
    <url-pattern>/project/*</url-pattern>
</servlet-mapping>
```
`/project/` 경로의 하위 모든 url을 서블릿이 처리하도록 하겠다.




:warning: __주의__ :warning:
url-pattern을 `/*` 로& 설정 시 정적타입(html, js)등의 로딩 문제가 발생할 수 있다.  
이를 해결하기 위해 `servlet-context.xml` 파일에 아래 코드를 추가해야 한다.  
```xml
<beans:bean class="org.springframework.web.servlet.mvc.annotation.AnnotationMethodHandlerAdapter">
    <beans:property name="alwaysUseFullPath" value="true" />
</beans:bean>

<beans:bean class="org.springframework.web.servlet.mvc.annotation.DefaultAnnotationHandlerMapping">
    <beans:property name="alwaysUseFullPath" value="true" />
</beans:bean>
```




#### controller
* __ex1__
```java
@RequestMapping("/project/mappingTest")
public void test() {
    ...
}
```
=> `"/mappingTest"`로 매핑


* __ex2__
```java
@Controller
@RequestMapping("/project/mappingTest/**")
public class TestController {
    @RequestMapping("/test1")
    public void test1() {
        ... 
    }
}
```
=> `"/mappingTest/test1"`로 매핑