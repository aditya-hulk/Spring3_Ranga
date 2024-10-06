# Section-1
# 1. Getting Started
![alt text](image.png)![alt text](image-1.png)![alt text](image-2.png)![alt text](image-3.png)
# 4. Installing java and Ide
![alt text](image-4.png)
# Section-2 (6-10)
# 7. Understanding the need of Java Framework
![alt text](image-5.png)![alt text](image-6.png)![alt text](image-7.png)![alt text](image-8.png)
# 8. Getting Started.
![alt text](image-9.png)![alt text](image-10.png)![alt text](image-11.png)
# 9. Step-3 Create new Spring Framework
![alt text](image-12.png)![alt text](image-13.png)
# 10. Intro to Spring Initializer and Maven
![alt text](image-14.png)
# 11. Quiz
![alt text](image-15.png)![alt text](image-16.png)
# Section-3 (11 to 14)
# 11. Step-4. Java Gaming Application
![alt text](image-17.png)![alt text](image-18.png)![alt text](image-19.png)![alt text](image-20.png)![alt text](image-21.png)
### AppGamingBasicJava.java
```java
package com.in28minutes.learn_spring_framework;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.MarioGame;

public class AppGamingBasicJava {

	public static void main(String[] args) {
	
		var marioGame = new MarioGame();
		var gameRunner = new GameRunner(marioGame);	
		gameRunner.run();
	}
}
```
### MarioGame.java
```java
package com.in28minutes.learn_spring_framework.game;

public class MarioGame {

}
```
### GameRunner.java
```java
package com.in28minutes.learn_spring_framework.game;

public class GameRunner {

	MarioGame game;

	public GameRunner(MarioGame game) {
		this.game = game;
	}

	public void run() {		
		System.out.println("Running game: " + game);		
	}	
}
```
# 12. Step-4 Adding button to our Gaming App.
![alt text](image-22.png)![alt text](image-23.png)![alt text](image-24.png)
### MarioGame.java
```java
package com.in28minutes.learn_spring_framework.game;

public class MarioGame {

	public void up() {
		System.out.println("Jump");
	}

	public void down() {
		System.out.println("Go into a hole");
	}

	public void left() {
		System.out.println("Go back");
	}

	public void right() {
		System.out.println("Accelerate");
	}
}
```
### GameRunner.java
```java
package com.in28minutes.learn_spring_framework.game;

public class GameRunner {

	MarioGame game;

	public GameRunner(MarioGame game) {
		this.game = game;
	}

	public void run() {
		System.out.println("Running game: " + game);
		game.up();
		game.down();
		game.left();
		game.right();
	}
}
```
# 13. Step-4 Introduction to var – Java10 feature
![alt text](image-25.png)
# 14. Step-5 Understanding Loose coupling and tight coupling
![alt text](image-26.png)![alt text](image-27.png)![alt text](image-28.png)![alt text](image-29.png)![alt text](image-30.png)![alt text](image-31.png)![alt text](image-32.png)
### SuperContraGame.java
```java
package com.in28minutes.learn_spring_framework.game;

public class SuperContraGame {

	public void up() {
		System.out.println("up");
	}

	public void down() {
		System.out.println("Sit down");
	}

	public void left() {
		System.out.println("Go back");
	}

	public void right() {
		System.out.println("Shoot a bullet");
	}
}
```
### GameRunner.java
```java
package com.in28minutes.learn_spring_framework.game;

public class GameRunner {

	private SuperContraGame game;

	public GameRunner(SuperContraGame game) {
		this.game = game;
	}

	public void run() {
		System.out.println("Running game: " + game);
		game.up();
		game.down();
		game.left();
		game.right();
	}
}
```
### AppGamingBasicJava.java
```java
package com.in28minutes.learn_spring_framework;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.SuperContraGame;

public class AppGamingBasicJava {

	public static void main(String[] args) {
	
		var superContraGame = new SuperContraGame();		
		var gameRunner = new GameRunner(superContraGame);	
		gameRunner.run();
	}
}
```
# Quiz- 2
![alt text](image-33.png)![alt text](image-34.png)![alt text](image-35.png)![alt text](image-36.png)
# Section-4
# 15. Step-6  Java Interface to make loosely coupled.
![alt text](image-37.png)![alt text](image-38.png)![alt text](image-39.png)![alt text](image-40.png)![alt text](image-41.png)![alt text](image-42.png)![alt text](image-43.png)![alt text](image-44.png)![alt text](image-45.png)![alt text](image-46.png)
### GamingConsole.java
```java
package com.in28minutes.learn_spring_framework.game;

public interface GamingConsole {
	
	void up();
	void down();
	void left();
	void right();
}
```
### SuperContraGame.java
```java
package com.in28minutes.learn_spring_framework.game;

public class SuperContraGame implements GamingConsole{

	public void up() {
		System.out.println("up");
	}

	public void down() {
		System.out.println("Sit down");
	}

	public void left() {
		System.out.println("Go back");
	}

	public void right() {
		System.out.println("Shoot a bullet");
	}
}
```
### MarioGame.java
```java
package com.in28minutes.learn_spring_framework.game;

public class MarioGame implements GamingConsole {

	public void up() {
		System.out.println("Jump");
	}

	public void down() {
		System.out.println("Go into a hole");
	}

	public void left() {
		System.out.println("Go back");
	}

	public void right() {
		System.out.println("Accelerate");
	}
}
```
### GameRunner.java
```java
package com.in28minutes.learn_spring_framework.game;

public class GameRunner {

	private GamingConsole game;

	public GameRunner(GamingConsole game) {
		this.game = game;
	}

	public void run() {
		System.out.println("Running game: " + game);
		game.up();
		game.down();
		game.left();
		game.right();
	}
}
```
### AppGamingBasicJava.java
```java
package com.in28minutes.learn_spring_framework;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.MarioGame;
import com.in28minutes.learn_spring_framework.game.SuperContraGame;

public class AppGamingBasicJava {

	public static void main(String[] args) {
	
//		var game = new SuperContraGame();	
		var game = new MarioGame();	
		var gameRunner = new GameRunner(game);	
		gameRunner.run();
	}

}
```
# 16. Step-6 -02 Code Review
![alt text](image-47.png)![alt text](image-48.png)
# 17. Step-6 03 Exercise Adding Pacman Game
![alt text](image-49.png)![alt text](image-50.png)
### PacmanGame.java
```java
package com.in28minutes.learn_spring_framework.game;

public class PacmanGame implements GamingConsole {

	@Override
	public void up() {
		System.out.println("up");
	}

	@Override
	public void down() {
		System.out.println("down");
	}

	@Override
	public void left() {
		System.out.println("left");
	}

	@Override
	public void right() {
		System.out.println("right");
	}

}
```
### AppGamingBasicJava.java
```java
package com.in28minutes.learn_spring_framework;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.MarioGame;
import com.in28minutes.learn_spring_framework.game.PacmanGame;
import com.in28minutes.learn_spring_framework.game.SuperContraGame;

public class AppGamingBasicJava {

	public static void main(String[] args) {
	
//		var game = new SuperContraGame();	
//		var game = new MarioGame();	
		var game = new PacmanGame();	
		var gameRunner = new GameRunner(game);	
		gameRunner.run();
	}

}
```
# 18. Step-7 Bringing in Java framework to make java app  loosely coupled.
![alt text](image-51.png)![alt text](image-52.png)
# 19. Step-8 Launching Java Spring Configuration
![alt text](image-53.png)![alt text](image-54.png)![alt text](image-55.png)![alt text](image-56.png)
# 20. Step-8 02 – Your first Java Spring Bean
![alt text](image-59.png)![alt text](image-60.png)![alt text](image-61.png)![alt text](image-62.png)![alt text](image-63.png)![alt text](image-64.png)
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}
}
```
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {
	
	public static void main(String[] args) {

	
		  var context = 
			 new  AnnotationConfigApplicationContext(HelloWorldConfiguration.class); 
		  
		 System.out.println(context.getBean("name"));
	}

}
```
# 21. Step-8 03 Code Review. Java Spring Configuration and Spring Bean
![alt text](image-65.png)
# Quiz-3
![alt text](image-66.png)![alt text](image-67.png)![alt text](image-68.png)![alt text](image-69.png)
# Section-5 (22 to 25)
# 22. Step-9 Creating more java Spring Bean
![alt text](image-70.png)![alt text](image-71.png)![alt text](image-72.png)
## Regarding Custom Bean
![alt text](image-73.png)![alt text](image-74.png)![alt text](image-75.png)
## Another object
![alt text](image-76.png)![alt text](image-77.png)
###  HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}
	

	@Bean
	public int age() {
		return 15;
	}
}
```
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {
	
	public static void main(String[] args) {

	
		  var context = 
			 new  AnnotationConfigApplicationContext(HelloWorldConfiguration.class); 
		  
		 System.out.println(context.getBean("name"));
		 
		 System.out.println(context.getBean("age"));
	}

}
```
## Custom Object
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

record Person(String name,int age) {};

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}
	

	@Bean
	public int age() {
		return 15;
	}
	
	@Bean
	public Person person() {
		var person = new Person("Ravi",20);
		return person;
	}
}
```
###  App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {
	
	public static void main(String[] args) {

	
		  var context = 
			 new  AnnotationConfigApplicationContext(HelloWorldConfiguration.class); 
		  
		 System.out.println(context.getBean("name"));
		 
		 System.out.println(context.getBean("age"));
		 
		 System.out.println(context.getBean("person"));
		 
	}
}
```
## Other object
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

record Person(String name, int age) {};

record Address(String firstLine, String city) {};

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}

	@Bean
	public int age() {
		return 15;
	}

	@Bean
	public Person person() {
		var person = new Person("Ravi", 20);
		return person;
	}

	@Bean
	public Address address() {
		return new Address("Baker Street", "London");
	}
}
```
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {

	public static void main(String[] args) {

		var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);

		System.out.println(context.getBean("name"));

		System.out.println(context.getBean("age"));

		System.out.println(context.getBean("person"));

		System.out.println(context.getBean("address"));

	}
}
```
# 23. Step-10 -1 Implementing Autowiring in configuration file.
![alt text](image-78.png)
## Can we change it?  Yes i.e. by Name
![alt text](image-79.png)![alt text](image-80.png)![alt text](image-81.png)![alt text](image-82.png)
## U can also getBean() by type.
![alt text](image-83.png)
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

record Person(String name, int age) {};

record Address(String firstLine, String city) {};

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}

	@Bean
	public int age() {
		return 15;
	}

	@Bean
	public Person person() {
		var person = new Person("Ravi", 20);
		return person;
	}

	@Bean(name = "address2")
	public Address address() {
		return new Address("Baker Street", "London");
	}
}
```
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {

	public static void main(String[] args) {

		var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);

		System.out.println(context.getBean("name"));

		System.out.println(context.getBean("age"));

		System.out.println(context.getBean("person"));

		System.out.println(context.getBean("address2"));

	}

}
```
## Fetching bean by type
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {

	public static void main(String[] args) {

		var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);

		System.out.println(context.getBean("name"));

		System.out.println(context.getBean("age"));

		System.out.println(context.getBean("person"));

		System.out.println(context.getBean("address2"));

		System.out.println(context.getBean(Address.class));

	}

}
```
# 24. Step-10 – 2 Reuse existing Spring Bean for Autowiring
![alt text](image-85.png)![alt text](image-86.png)
## via method call
![alt text](image-87.png)![alt text](image-88.png)
## 2nd Scenario
### Add Address parameter to the Person class/record
![alt text](image-89.png)![alt text](image-90.png)
## Observation:
- U can create beans, reusing existing beans, which are already managed by the
spring framework.
## Alternate Approach
### Calling via parameters
![alt text](image-91.png)![alt text](image-92.png)
## By Method Call
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

record Person(String name, int age) {};

record Address(String firstLine, String city) {};

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}

	@Bean
	public int age() {
		return 15;
	}

	@Bean
	public Person person() {
		var person = new Person("Ravi", 20);
		return person;
	}

	@Bean
	public Person person2MethodCall() {
		var person = new Person(name(), age());
		return person;
	}
	
	@Bean(name = "address2")
	public Address address() {
		return new Address("Baker Street", "London");
	}
}
```
###  App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {

	public static void main(String[] args) {

		var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);

		System.out.println(context.getBean("name"));

		System.out.println(context.getBean("age"));

		System.out.println(context.getBean("person"));

		System.out.println(context.getBean("address2"));

		System.out.println(context.getBean(Address.class));
		
		System.out.println(context.getBean("person2MethodCall"));

	}

}
```
## 2nd Scenario
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

record Person(String name, int age, Address address) {};

record Address(String firstLine, String city) {};

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}

	@Bean
	public int age() {
		return 15;
	}

	@Bean
	public Person person() {
		var person = new Person("Ravi", 20,new Address("Baker Street", "London") );
		return person;
	}

	@Bean
	public Person person2MethodCall() {
		var person = new Person(name(), age(), address() );
		return person;
	}
	
	@Bean(name = "address2")
	public Address address() {
		return new Address("Baker Street", "London");
	}
}
```
## Calling via parameters
### HelloWorldConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

record Person(String name, int age, Address address) {};

record Address(String firstLine, String city) {};

@Configuration
public class HelloWorldConfiguration {

	@Bean
	public String name() {
		return "Ranga";
	}

	@Bean
	public int age() {
		return 15;
	}

	@Bean
	public Person person() {
		var person = new Person("Ravi", 20,new Address("Baker Street", "London") );
		return person;
	}

	@Bean
	public Person person2MethodCall() {
		var person = new Person(name(), age(), address() );
		return person;
	}
	
	@Bean
	public Person person3Parameters(String name,int age,Address address3){		
		return new Person(name, age, address3);
	}
	
	@Bean(name = "address2")
	public Address address() {
		return new Address("Baker Street", "London");
	}
	
	@Bean(name = "address3")
	public Address address3() {
		return new Address("MotiNagar", "Hyderabad");
	}
}
```
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {

	public static void main(String[] args) {

		var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);

		System.out.println(context.getBean("name"));

		System.out.println(context.getBean("age"));

		System.out.println(context.getBean("person"));

		System.out.println(context.getBean("address2"));

//		System.out.println(context.getBean(Address.class));
		
		System.out.println(context.getBean("person2MethodCall"));
		
		System.out.println(context.getBean("person3Parameters"));

	}
}
```
# 25. Step-10 03 Code review
![alt text](image-93.png)
# Quiz-4
![alt text](image-94.png)![alt text](image-95.png)
# Section-6  (26 to 30)
# 26. Step11- Question about Spring framework.
![alt text](image-96.png)
# 27. Step12- Spring IOC container – Application Context & Bean Factory
![alt text](image-97.png)![alt text](image-98.png)
# 28. Step-13 Exploring Java Bean vs Pojo vs Spring Bean
![alt text](image-99.png)![alt text](image-100.png)![alt text](image-101.png)![alt text](image-102.png)![alt text](image-103.png)![alt text](image-104.png)
# 29. Step-14 -01 Exploring Spring Framework Bean
![alt text](image-105.png)![alt text](image-106.png)![alt text](image-107.png)
## Listing All Bean
### App02HelloWorldSpring.java
```java
package com.in28minutes.learn_spring_framework;

import java.util.Arrays;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

public class App02HelloWorldSpring {

	public static void main(String[] args) {

		var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);

		System.out.println(context.getBean("name"));

		System.out.println(context.getBean("age"));
		System.out.println(context.getBean("person"));
		System.out.println(context.getBean("address2"));

//		System.out.println(context.getBean(Address.class));
		
		System.out.println(context.getBean("person2MethodCall"));
		
		System.out.println(context.getBean("person3Parameters"));
		
		System.out.println("***********************");
		
	
		System.out.println(context.getBeanDefinitionCount());
		

		Arrays.stream(context.getBeanDefinitionNames())
		 .forEach(System.out::println);
	}

}
```
