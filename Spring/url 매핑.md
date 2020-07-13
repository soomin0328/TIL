## URL 매핑


#### web.xml
```xml
<servlet-mapping>
    <servlet-name>appServlet</servlet-name>
    <url-pattern>/</url-pattern>
</servlet-mapping>
```
모든 url을 서블릿이 처리하도록 하겠다.


#### servlet-context.xml
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
@RequestMapping("/mappingTest")
public void test() {
    ...
}
```
=> `"/mappingTest"`로 매핑


* __ex2__
```java
@Controller
@RequestMapping("/mappingTest/**")
public class TestController {
    @RequestMapping("/test1")
    public void test1() {
        ... 
    }
}
```
=> `"/mappingTest/test1"`로 매핑