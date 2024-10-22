
# 120
### login.jsp
```jsp
<html>
	<head>
		<title> Login Page</title>
	</head>
	<body>
		Welcome to the login page!123
	</body>
</html>
```
### LoginController
```java
package com.in28minutes.springboot.myfirstwebapp.login;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;

@Controller
public class LoginController {
	
	@RequestMapping("login")
	public String getLoginPage() {
		return "login";
	}

}
```






