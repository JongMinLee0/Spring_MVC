# Spring_MVC


#### 구조
- View (.jsp)
- Controller : Dispatcher에서 전달되 요청을 처리.
- Servlet-context.xml : Spring container 설정 파일.
- Web.xml : DispatcherServlet servlet mapping / Spring 설정 파일 위치 정의
- DispatcherServlet : cilent의 요청을 최촐 받아 controller에 전달



### Form data
#### controller.java
```java
@RequestMapping(“board/confirmid”)
Return “board/confirmid”;
```


#### board/confirmid.jsp
```java
ID : ${id}<br />
PW : ${pw}
```
경로 ->  http://localhost:8181/spring_mvc_pjt/board/confirmid?id=abc&pw=1234



### GET / POST
#### controller.java
```java
@RequestMapping(method = RequestMethod.GET, value = "/student")
```

#### index.jsp
```java
<form action = "student" method = "get">
```
-> POST 방식의 경우 GET을 POST로 변경시 주면 된다.


### @ModelAttribute

Annotation을 이용하면 Command 객체의 이름을 개발자가 변경할 수 있다.
Ex) StudentInformation studentInformation -> @ModelAttribute("studentInfo")StudentInformation studentInformation



### Redirect

다른 페이지로 이동할 때 사용
```java
return "redirect:studentid"; //studentid로 이동
``` 



### Validator interface

Data 검증을 하기 위해 사용한다.



#### @Valid / @InitBinder

pom.xml에 명시해줘 한다.
```xml
<dependency>
	<groupId>org.hibernate</groupId>
	<artifactId>hibernate-validator</artifactId>
	<version>4.2.0.Final</version>
</dependency>
```




