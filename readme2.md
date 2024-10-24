# 133
### TodoController
```java
package com.in28minutes.springboot.myfirstwebapp.todo;

import java.util.List;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.SessionAttributes;

@Controller
@SessionAttributes("name")
public class TodoController {

	private TodoService todoService;

	public TodoController(TodoService todoService) {
		super();
		this.todoService = todoService;
	}
	
	@RequestMapping("list-todo")
	public String listAllTodo(ModelMap model) {
		
		List<Todo> todos = todoService.findByUsername("in28min");
		
		model.addAttribute("todos", todos);
		
		return "listTodo";
	}
}
```
###  LoginController
```java
package com.in28minutes.springboot.myfirstwebapp.login;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.SessionAttributes;

@Controller
@SessionAttributes("name")
public class LoginController {
	
	private AuthenticationService authenticationService;
	
	

	public LoginController(AuthenticationService authenticationService) {
		super();
		this.authenticationService = authenticationService;
	}

	@RequestMapping(value = "login",method = RequestMethod.GET)
	public String getLoginPage() {

		return "login";
	}
	
	@RequestMapping(value = "login",method = RequestMethod.POST)
	public String gotoWelcomePage(@RequestParam String name,
			@RequestParam String password,
			ModelMap model) {
		
		if(authenticationService.authenticate(name, password)) {
			model.put("name", name);
			model.put("password", password);
			
			return "welcome";
		}
		
		model.put("errorMessage", "Invalid Credentials! Please try again....");
		
		return "login";
	}

}
```
### pom.xml
```xml

		<dependency>
			<groupId>jakarta.servlet.jsp.jstl</groupId>
			<artifactId>jakarta.servlet.jsp.jstl-api</artifactId>
		</dependency>

		<dependency>
			<groupId>org.glassfish.web</groupId>
			<artifactId>jakarta.servlet.jsp.jstl</artifactId>
		</dependency>

```
### login.jsp
```jsp
<html>
	<head>
		<title> Login Page</title>
	</head>
	<body>
		Welcome to the login page !
		<pre>${errorMessage }</pre>
		<form method="post">
			Name: <input type="text" name="name">
			Password:<input type="password" name="password">
			<input type="submit">
		</form>
	</body>
</html>
```
### Welocme.jsp
```jsp
<html>
	<head>
		<title> Welcome Page</title>
	</head>
	<body>
		<div> Welcome ${name }</div> 	
		<hr>
		<div><a href="list-todo">Manage</a>Your Todos</div>
				
	</body>
</html>
```
### todo.jsp
```jsp
<%@ taglib prefix="c" uri="jakarta.tags.core"%>
<html>
	<head>
		<title> List Todos Page</title>
	</head>
	<body>
		<div> Welcome ${name }</div> 	
		<hr>
		<h1>Your Todos</h1>		
		<table>
			<thead>
				<tr>
					<th>id</th>
				  	<th>Description</th>
					<th>Target Date</th>
					<th>Is Done?</th>
				</tr>
			</thead>
			<tbody>
			  <c:forEach items="${todos}" var="todo">
				<tr>
					<td>${todo.id}</td>
					<td>${todo.description}</td>
					<td>${todo.targetDate}</td>
					<td>${todo.done}</td>
				</tr>
			   </c:forEach>
			</tbody>
		</table>
	</body>
</html>
```
# 135 & 136
### pom.xml
```xml
<dependency>
			<groupId>org.webjars</groupId>
			<artifactId>bootstrap</artifactId>
			<version>5.1.3</version>
		</dependency>

		<dependency>
			<groupId>org.webjars</groupId>
			<artifactId>jquery</artifactId>
			<version>3.6.0</version>
		</dependency>
```
### listTodo.jsp
```jsp
<%@ taglib prefix="c" uri="jakarta.tags.core"%>
<html>
<head>
<link href="webjars/bootstrap/5.1.3/css/bootstrap.min.css"
	rel="stylesheet">
<title>List Todos Page</title>
</head>
<body>

	<div class="container">
		<h1>Your Todos</h1>
		<table class="table">
			<thead>
				<tr>
					<th>id</th>
					<th>Description</th>
					<th>Target Date</th>
					<th>Is Done?</th>
				</tr>
			</thead>
			<tbody>
				<c:forEach items="${todos}" var="todo">
					<tr>
						<td>${todo.id}</td>
						<td>${todo.description}</td>
						<td>${todo.targetDate}</td>
						<td>${todo.done}</td>
					</tr>
				</c:forEach>
			</tbody>
		</table>
	</div>
	<script src="webjars/bootstrap/5.1.3/js/bootstrap.min.js"></script>
	<script src="webjars/jquery/3.6.0/jquery.min.js"></script>
</body>
</html>
```
### login.jsp
```jsp
<html>
<head>
<title>Login Page</title>
</head>
<body>
	<div class="container">
		<h1>Login</h1>
		<pre>${errorMessage }</pre>
		<form method="post">
			Name: <input type="text" name="name"> Password:<input
				type="password" name="password"> <input type="submit">
		</form>
	</div>
</body>
</html>
```
### welcome.jsp
```jsp
<html>
<head>
<title>Welcome Page</title>
</head>
<body>
	<div class="container">
		<h1>Welcome ${name }</h1>
		<a href="list-todo">Manage</a>Your Todos
	</div>
</body>
</html>
```



