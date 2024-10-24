# Section-30 – Functional Pgm
# 416. Step-1 Functional Pgm
![alt text](image-108.png)
### FP01Structured.java
```java
package programming;

import java.util.List;

public class FP01Structured {

	public static void main(String[] args) {
		
		//Method to print All number in list
		printAllNumberInListStructured(List.of(12,9,13,4,6,2,4,12,15));
	}

	private static void printAllNumberInListStructured(List<Integer> numbers) {		
		
		for(int number : numbers) {
			System.out.println(number);
		}		
	}

}
```
# 417. Step-2
![alt text](image-109.png)![alt text](image-110.png)
### FP01Functional.java
```java
package programming;

import java.util.List;

public class FP01Functional {

	public static void main(String[] args) {

		// Method to print All number in list
		printAllNumberInListFunctional(List.of(12, 9, 13, 4, 6, 2, 4, 12, 15));
	}

	private static void print(int number) {
		System.out.println(number);
	}

	private static void printAllNumberInListFunctional(List<Integer> numbers) {

		numbers.stream().forEach(FP01Functional::print);

	}

}
```
# 418. Step-3 via filter
![alt text](image-111.png)![alt text](image-112.png)![alt text](image-113.png)
### FP01Functional.java
```java
package programming;

import java.util.List;

public class FP01Functional {

	public static void main(String[] args) {

		// Method to print All number in list
		printAllNumberInListFunctional(List.of(12, 9, 13, 4, 6, 2, 4, 12, 15));
	}

	private static void printAllNumberInListFunctional(List<Integer> numbers) {

		numbers.stream().forEach(System.out::println);

	}

}
```
### FP01Structured.java
```java
package programming;

import java.util.List;

public class FP01Structured {

	public static void main(String[] args) {

		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);
//		printAllNumberInListStructured(numbers);
		printEvenNumberInListStructured(numbers);
	}

	private static void printAllNumberInListStructured(List<Integer> numbers) {

		for (int number : numbers) {
			System.out.println(number);
		}
	}

	private static void printEvenNumberInListStructured(List<Integer> numbers) {

		for (int number : numbers) {
			if (number % 2 == 0)
				System.out.println(number);
		}
	}

}
```
### FP01Functional.java
```java
package programming;

import java.util.List;

public class FP01Functional {

	public static void main(String[] args) {

		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);
//		printAllNumberInListFunctional(numbers);
		printEvenNumberInListFunctional(numbers);
	}

	private static boolean isEven(int number) {
		return number % 2 == 0;
	}

	private static void printAllNumberInListFunctional(List<Integer> numbers) {

		numbers.stream().forEach(System.out::println);
	}

	private static void printEvenNumberInListFunctional(List<Integer> numbers) {

		numbers.stream().filter(FP01Functional::isEven).forEach(System.out::println);
	}
}
```
# 419. Step-4 Using lambda
![alt text](image-114.png)![alt text](image-115.png)
### FP01Functional.java
```java
package programming;

import java.util.List;

public class FP01Functional {

	public static void main(String[] args) {

		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);
		printEvenNumberInListFunctional(numbers);
	}

	private static void printEvenNumberInListFunctional(List<Integer> numbers) {

		numbers.stream().filter(number -> number % 2 == 0).forEach(System.out::println);
	}
}
```
# 420. Step-5
![alt text](image-116.png)![alt text](image-117.png)![alt text](image-118.png)![alt text](image-119.png)![alt text](image-120.png)![alt text](image-121.png)
### FP01Exercises.java
```java
package programming;

import java.util.List;

public class FP01Exercises {

	public static void main(String[] args) {

		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);

		// Print odd number list
		printOddNumberInListFunctional(numbers);
	}

	private static void printOddNumberInListFunctional(List<Integer> numbers) {

		numbers.stream().filter(number -> number % 2 != 0).forEach(System.out::println);
	}
}
```
### FP01Exercises.java
```java
package programming;

import java.util.List;

public class FP01Exercises {

	public static void main(String[] args) {

		// Exercise-1
		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);
//		printOddNumberInListFunctional(numbers);

		List<String> courses = List.of("Spring", "Spring Boot", "API", "Microservices", "AWS", "PCF", "Azure", "Docker",
				"Kubernate");

		//// Exercise-3
		courses.stream().filter(course -> course.contains("Spring")).forEach(System.out::println);
	}

}
```
###  FP01Exercises.java
```java
package programming;

import java.util.List;

public class FP01Exercises {

	public static void main(String[] args) {	

		List<String> courses = List.of("Spring", "Spring Boot", "API", "Microservices",
				"AWS", "PCF", "Azure", "Docker",
				"Kubernate");

		courses.stream()
		 .filter(course -> course.length() >= 4)
		 .forEach(System.out::println);
	}

}
```
# 421. Step-6 Using map
![alt text](image-122.png)![alt text](image-123.png)![alt text](image-124.png)
### FP01Exercises.java
```java
package programming;

import java.util.List;

public class FP01Exercises {

	public static void main(String[] args) {	

		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);
		
		List<String> courses = List.of("Spring", "Spring Boot", "API", "Microservices",
				"AWS", "PCF", "Azure", "Docker",
				"Kubernate");

		printCubesOfOddNumber(numbers);
	}

	private static void printCubesOfOddNumber(List<Integer> numbers) {
		
		numbers.stream()
		 .filter(number -> number%2 != 0)
		 .map(number -> number * number * number)
		 .forEach(System.out::println);
		
	}	

}
```
### FP01Exercises.java
```java
package programming;

import java.util.List;

public class FP01Exercises {

	public static void main(String[] args) {	

		List<Integer> numbers = List.of(12, 9, 13, 4, 6, 2, 4, 12, 15);
		
		List<String> courses = List.of("Spring", "Spring Boot", "API", "Microservices",
				"AWS", "PCF", "Azure", "Docker",
				"Kubernate");

//		printCubesOfOddNumber(numbers);
		
		printLengthOfCourses(courses);
	}

	private static void printLengthOfCourses(List<String> courses) {
		
		courses.stream()
		 .map(course ->  (course + " : " +course.length()))
		 .forEach(System.out::println);
		
	}

	private static void printCubesOfOddNumber(List<Integer> numbers) {
		
		numbers.stream()
		 .filter(number -> number%2 != 0)
		 .map(number -> number * number * number)
		 .forEach(System.out::println);
		
	}	

}
```
# 422. Step-7 Optional
![alt text](image-125.png)![alt text](image-126.png)![alt text](image-127.png)![alt text](image-128.png)
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
# 30. Step-14-02 primary and qualifier annotation
![alt text](image-129.png)![alt text](image-130.png)![alt text](image-131.png)![alt text](image-132.png)![alt text](image-133.png)![alt text](image-134.png)![alt text](image-135.png)![alt text](image-136.png)![alt text](image-137.png)![alt text](image-138.png)![alt text](image-139.png)![alt text](image-140.png)![alt text](image-141.png)
# Quiz-5
![alt text](image-142.png)![alt text](image-143.png)![alt text](image-144.png)
# Section-7
# 31. Step-15 -01
![alt text](image-145.png)![alt text](image-146.png)![alt text](image-147.png)
# 32. Step-15-02
![alt text](image-148.png)![alt text](image-149.png)![alt text](image-150.png)
###  GamingConfiguration.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Primary;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.GamingConsole;
import com.in28minutes.learn_spring_framework.game.PacmanGame;

@Configuration
public class GamingConfiguration {

	@Bean
	public GamingConsole game() {
		var game = new PacmanGame();
		return game;
	}

	@Bean
	@Primary
	public GameRunner gameRunner(GamingConsole game) {
		var gameRunner = new GameRunner(game);
		return gameRunner;
	}

	@Bean
	public GameRunner gameRunner1() {
		var gameRunner = new GameRunner(game());
		return gameRunner;
	}
}
```
### App03GamingSpringBeans.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.GamingConsole;
public class App03GamingSpringBeans {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(GamingConfiguration.class)) {

			context.getBean(GamingConsole.class).up();

			System.out.println("-------------------");

			context.getBean(GameRunner.class).run();
		}
	}
}
```
# 33. Step-15 03. Code Review
![alt text](image-151.png)
# 34. Step-16. More questions
![alt text](image-152.png)
# 35. Step-17 Exploring 
![alt text](image-153.png)![alt text](image-154.png)
# Quiz-6
![alt text](image-155.png)![alt text](image-156.png)
# 36. Remembering Things for long time
![alt text](image-157.png)
# Section-8 (37 to 53)
# 37.  Step-1 -01 Spring Create your Object
![alt text](image-158.png)![alt text](image-159.png)![alt text](image-160.png)![alt text](image-161.png)![alt text](image-162.png)
### PacmanGame.java
```java
package com.in28minutes.learn_spring_framework.game;

import org.springframework.stereotype.Component;

@Component
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
### App03GamingSpringBeans.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.GamingConsole;

@Configuration
@ComponentScan("com.in28minutes.learn_spring_framework.game")
public class App03GamingSpringBeans {

	@Bean
	public GameRunner gameRunner(GamingConsole game) {
		System.out.println("Parameter : "+ game);
		var gameRunner = new GameRunner(game);
		return gameRunner;
	}

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(App03GamingSpringBeans.class)) {

			context.getBean(GamingConsole.class).up();

			System.out.println("-------------------");

			context.getBean(GameRunner.class).run();
		}

	}

}
```
# 38. Step-01 -02 
![alt text](image-163.png)![alt text](image-164.png)![alt text](image-165.png)![alt text](image-166.png)![alt text](image-167.png)![alt text](image-168.png)![alt text](image-169.png)![alt text](image-170.png)
# 39. Step-1 -03
![alt text](image-171.png)![alt text](image-172.png)![alt text](image-173.png)
### GameRunner.java
```java
package com.in28minutes.learn_spring_framework.game;

import org.springframework.stereotype.Component;

@Component
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
###  GamingAppLauncherApplication.java
```java
package com.in28minutes.learn_spring_framework;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.GamingConsole;

@Configuration
@ComponentScan("com.in28minutes.learn_spring_framework.game")
public class GamingAppLauncherApplication {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(GamingAppLauncherApplication.class)) {

			context.getBean(GamingConsole.class).up();

			System.out.println("-------------------");

			context.getBean(GameRunner.class).run();
		}

	}

}
```
# 40. Step1-04 Code Review
![alt text](image-174.png)
# 42. Step2 Exploring Primary and Qualifier annotation
![alt text](image-175.png)![alt text](image-176.png)![alt text](image-177.png)![alt text](image-178.png)![alt text](image-179.png)![alt text](image-180.png)![alt text](image-181.png)
# 43. Step-3 Primary and Qualifier which annotation you use.
![alt text](image-182.png)![alt text](image-183.png)![alt text](image-184.png)
# 44. Step4-01 Diff types of Dependencies
![alt text](image-185.png)![alt text](image-186.png)![alt text](image-187.png)
### SimpleSpringContextLauncher.java
```java
package com.in28minutes.learn_spring_framework.example.a0;

import java.util.Arrays;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.GamingConsole;

@Configuration
@ComponentScan
public class SimpleSpringContextLauncher {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(SimpleSpringContextLauncher.class)) {

			Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);
		}

	}

}
```
# 45. Field Injection
![alt text](image-188.png)![alt text](image-189.png)![alt text](image-190.png)![alt text](image-191.png)![alt text](image-192.png)![alt text](image-193.png)
## Field Injection
### DependencyInjectionLauncherInjection.java
```java
package com.in28minutes.learn_spring_framework.example.a1;

import java.util.Arrays;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

@Component
class YourBusinessClass {

	@Autowired
	Dependency1 dependency1;

	@Autowired
	Dependency2 dependency2;

	public String toString() {

		return "Using " + dependency1 + " and " + dependency2;
	}
}

@Component
class Dependency1 {

}

@Component
class Dependency2 {

}

@Configuration
@ComponentScan
public class DependencyInjectionLauncherInjection {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(DependencyInjectionLauncherInjection.class)) {

			Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);

			System.out.println(context.getBean(YourBusinessClass.class));
		}

	}

}
```
# 46. Step4. -03 Setter and Constructor Injection
![alt text](image-194.png)![alt text](image-195.png)![alt text](image-196.png)![alt text](image-197.png)![alt text](image-198.png)![alt text](image-199.png)![alt text](image-200.png)![alt text](image-201.png)
## Setter Injection
### DependencyInjectionLauncherInjection.java
```java
package com.in28minutes.learn_spring_framework.example.a1;

import java.util.Arrays;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

@Component
class YourBusinessClass {

	Dependency1 dependency1;

	Dependency2 dependency2;

	@Autowired
	public void setDependency1(Dependency1 dependency1) {
		System.out.println("Setter-Injection- setDependency1");
		this.dependency1 = dependency1;
	}

	@Autowired
	public void setDependency2(Dependency2 dependency2) {
		System.out.println("Setter-Injection- setDependency2");
		this.dependency2 = dependency2;
	}

	public String toString() {

		return "Using " + dependency1 + " and " + dependency2;
	}
}

@Component
class Dependency1 {

}

@Component
class Dependency2 {

}

@Configuration
@ComponentScan
public class DependencyInjectionLauncherInjection {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(DependencyInjectionLauncherInjection.class)) {

			Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);

			System.out.println(context.getBean(YourBusinessClass.class));
		}

	}

}
```
## Constructor Injection
### DependencyInjectionLauncherInjection.java
```java
package com.in28minutes.learn_spring_framework.example.a1;

import java.util.Arrays;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

@Component
class YourBusinessClass {

	Dependency1 dependency1;

	Dependency2 dependency2;

	@Autowired
	public YourBusinessClass(Dependency1 dependency1, Dependency2 dependency2) {
		super();
		System.out.println("Constructor Injection");
		this.dependency1 = dependency1;
		this.dependency2 = dependency2;
	}

	public String toString() {

		return "Using " + dependency1 + " and " + dependency2;
	}
}

@Component
class Dependency1 {

}

@Component
class Dependency2 {

}

@Configuration
@ComponentScan
public class DependencyInjectionLauncherInjection {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(DependencyInjectionLauncherInjection.class)) {

			Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);

			System.out.println(context.getBean(YourBusinessClass.class));
		}

	}

}
```
# 47. Step5 Imp Terminology
![alt text](image-202.png)![alt text](image-203.png)![alt text](image-204.png)![alt text](image-205.png)
# 49. Step6. Comparing @Component vs @Bean
![alt text](image-206.png)![alt text](image-207.png)
# 50. Step7 Why do we have dependency in Java Spring App.
![alt text](image-208.png)
# 51. step8 Exercise solution
![alt text](image-209.png)![alt text](image-210.png)![alt text](image-211.png)![alt text](image-212.png)
### DataService.java
```java
package com.in28minutes.learn_spring_framework.example.c1;

public interface DataService {

	int[] retrieveData();
}
```
### MongoDbDataService.java
```java
package com.in28minutes.learn_spring_framework.example.c1;

import org.springframework.context.annotation.Primary;
import org.springframework.stereotype.Component;

@Component
@Primary
public class MongoDbDataService implements DataService{

	@Override
	public int[] retrieveData() {
		return new int[] {11,22,33,44,55};
	}

}
```
### MySqlDataService
```java
package com.in28minutes.learn_spring_framework.example.c1;

import org.springframework.stereotype.Component;

@Component
public class MySqlDataService implements DataService{

	@Override
	public int[] retrieveData() {
		return new int[] {1,2,3,4,5};
	}

}
```
### BusinessCalculationService
```java
package com.in28minutes.learn_spring_framework.example.c1;

import java.util.Arrays;

import org.springframework.stereotype.Component;

@Component
public class BusinessCalculationService {

	private DataService dataService;

	public BusinessCalculationService(DataService dataService) {
		super();
		this.dataService = dataService;
	}

	public int findMax() {

		return Arrays.stream(dataService.retrieveData()).max().orElse(0);
	}

}
```
### RealWorldSpringContextLauncher
```java
package com.in28minutes.learn_spring_framework.example.c1;

import java.util.Arrays;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

import com.in28minutes.learn_spring_framework.game.GameRunner;
import com.in28minutes.learn_spring_framework.game.GamingConsole;

@Configuration
@ComponentScan
public class RealWorldSpringContextLauncher {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(RealWorldSpringContextLauncher.class)) {

			Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);
			
			System.out.println(context.getBean(BusinessCalculationService.class).findMax());
		}

	}

}
```
# 52. Step9
![alt text](image-213.png)![alt text](image-214.png)
# Quiz-7
![alt text](image-215.png)![alt text](image-216.png)
# 53.  Consistent
![alt text](image-217.png)
 # Section -9 Advance Feature
# 55. 01 Lazy and Eager Initialization
![alt text](image-218.png)![alt text](image-219.png)![alt text](image-220.png)![alt text](image-221.png)![alt text](image-222.png)![alt text](image-223.png)
## Concept of Eager Initialization
### LazyInitializationContextLauncher.java
```java
package com.in28minutes.learn_spring_framework.example.d1;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

@Component
class ClassA {

}

@Component
class ClassB {

	private ClassA classA;

	public ClassB(ClassA classA) {
		System.out.println("Some Initialization logic");
		this.classA = classA;
	}
}

@Configuration
@ComponentScan
public class LazyInitializationContextLauncher {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(LazyInitializationContextLauncher.class)) {

		}
	}
}
```
##  Concept of Lazy Initialization
### LazyInitializationContextLauncher.java
```java
package com.in28minutes.learn_spring_framework.example.d1;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Lazy;
import org.springframework.stereotype.Component;

@Component
class ClassA {

}

@Component
@Lazy
class ClassB {

	private ClassA classA;

	public ClassB(ClassA classA) {
		System.out.println("Some Initialization logic");
		this.classA = classA;
	}

	public void doSomething() {
		System.out.println("Do Something.");
	}
}

@Configuration
@ComponentScan
public class LazyInitializationContextLauncher {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(LazyInitializationContextLauncher.class)) {

			System.out.println("Initialization of context is completed.");

			context.getBean(ClassB.class).doSomething();
		}
	}
}
```
# 56. Compare Lazy vs Eager Initialization
![alt text](image-224.png)
# 57. Bean Scopes- Prototype and Singelton
![alt text](image-225.png)![alt text](image-226.png)![alt text](image-227.png)
### BeanScopeLauncherApplication
```java
package com.in28minutes.learn_spring_framework.example.e1;

import org.springframework.beans.factory.config.ConfigurableBeanFactory;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Component;

@Component
class NormalClass {

}

@Scope(value = ConfigurableBeanFactory.SCOPE_PROTOTYPE)
@Component
class PrototypeClass {

}

@Configuration
@ComponentScan
public class BeanScopeLauncherApplication {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(BeanScopeLauncherApplication.class)) {

			System.out.println(context.getBean(NormalClass.class));
			System.out.println(context.getBean(NormalClass.class));

			System.out.println(context.getBean(PrototypeClass.class));
			System.out.println(context.getBean(PrototypeClass.class));
			System.out.println(context.getBean(PrototypeClass.class));

		}

	}

}
```
# 58. Step-4 Comparing Prototype vs Singleton
![alt text](image-228.png)![alt text](image-229.png)
# 59. Step-5 Spring Beans – Post-Construct and Pre-Destroy
![alt text](image-230.png)![alt text](image-231.png)![alt text](image-232.png)![alt text](image-233.png)![alt text](image-234.png)![alt text](image-235.png)![alt text](image-236.png)![alt text](image-237.png)![alt text](image-238.png)
### PrePostContextLauncherApplication
```java
package com.in28minutes.learn_spring_framework.example.f1;

import java.util.Arrays;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

import jakarta.annotation.PostConstruct;
import jakarta.annotation.PreDestroy;

@Component
class SomeClass {

	private SomeDependency someDependency;

	public SomeClass(SomeDependency someDependency) {
		super();
		this.someDependency = someDependency;
		System.out.println("All Dependency are ready");
	}

	@PostConstruct
	public void initialize() {
		someDependency.getReady();
	}

	@PreDestroy
	public void cleanUp() {
		System.out.println("Clean UP");
	}

}

@Component
class SomeDependency {

	public void getReady() {
		System.out.println("Some logic using someDependency");
	}

}

@Configuration
@ComponentScan
public class PrePostContextLauncherApplication {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(PrePostContextLauncherApplication.class)) {

			Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);

		}

	}
}
```
# 60. Step-6 Evolution of Jakarta , comparing j2ee and java EE
![alt text](image-239.png)![alt text](image-240.png)
# 61. Step-7 Exploring Jakarta CDI
![alt text](image-241.png)![alt text](image-242.png)![alt text](image-243.png)![alt text](image-244.png)
## Without CDI concept
### CDIContextLauncherApplication
```java
package com.in28minutes.learn_spring_framework.example.g1;

import java.util.Arrays;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

@Component
class BusinessService {

	private DataService dataService;

	@Autowired
	public void setDataService(DataService dataService) {
		System.out.println("Setter Injection");
		this.dataService = dataService;
	}

	public DataService getDataService() {
		return dataService;
	}
}

@Component
class DataService {

}

@Configuration
@ComponentScan
public class CDIContextLauncherApplication {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(CDIContextLauncherApplication.class)) {

			Arrays.stream(context.getBeanDefinitionNames())
			   .forEach(System.out::println);
			
			System.out.println("=======================");
			
			System.out.println(context.getBean(BusinessService.class).getDataService());
		}
	}
}
```
## With CDI concept
### CDIContextLauncherApplication
```java
package com.in28minutes.learn_spring_framework.example.g1;

import java.util.Arrays;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

import jakarta.inject.Inject;
import jakarta.inject.Named;

@Named
class BusinessService {

	private DataService dataService;

	@Inject
	public void setDataService(DataService dataService) {
		System.out.println("Setter Injection");
		this.dataService = dataService;
	}

	public DataService getDataService() {
		return dataService;
	}
}

@Named
class DataService {

}

@Configuration
@ComponentScan
public class CDIContextLauncherApplication {

	public static void main(String[] args) {

		try (var context = new AnnotationConfigApplicationContext(CDIContextLauncherApplication.class)) {

			Arrays.stream(context.getBeanDefinitionNames())
			   .forEach(System.out::println);
			
			System.out.println("=======================");
			
			System.out.println(context.getBean(BusinessService.class).getDataService());
		}
	}
}
```
### pom.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.3.4</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.in28minutes</groupId>
	<artifactId>learn-spring-framework</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>learn-spring-framework</name>
	<description>Demo project for Spring Boot</description>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>17</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter</artifactId>
		</dependency>

		<dependency>
			<groupId>jakarta.inject</groupId>
			<artifactId>jakarta.inject-api</artifactId>
			<version>2.0.1.MR</version>
		</dependency>
		
		
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```
# 63. Step8 - Xml Configuration
![alt text](image-245.png)![alt text](image-246.png)![alt text](image-247.png)![alt text](image-248.png)![alt text](image-249.png)![alt text](image-250.png)![alt text](image-251.png)![alt text](image-252.png)![alt text](image-253.png)
### contextConfiguration.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd"> 
        
        <!-- bean definitions here -->

	<bean id="name" class="java.lang.String" >
		<!-- Here we use Constructor injection -->
		<constructor-arg  value="Ranga"/>
	</bean>
	
	<bean id="age" class="java.lang.Integer" >
		<constructor-arg  value="35"/>
	</bean>
	
	<!-- 
			<context:component-scan base-package="com.in28minutes.learn_spring_framework.game"/>
	 -->
	 
	 <!--  Create individual Pacman Game -->
	 <bean id="gameOfPacman" class="com.in28minutes.learn_spring_framework.game.PacmanGame" />
	 
	 <bean id="gameRunner" class="com.in28minutes.learn_spring_framework.game.GameRunner">
	 	
	 	<constructor-arg ref="gameOfPacman" />
	 </bean>
	
</beans>
```
### XmlConfigurationContextLauncherApplication.java
```java
package com.in28minutes.learn_spring_framework.example.h1;

import java.util.Arrays;

import org.springframework.context.support.ClassPathXmlApplicationContext;

import com.in28minutes.learn_spring_framework.game.GameRunner;

public class XmlConfigurationContextLauncherApplication {

	public static void main(String[] args) {

		try (var context = new ClassPathXmlApplicationContext("contextConfiguration.xml")) {
			
			System.out.println("Created Bean Name******************");

			Arrays.stream(context.getBeanDefinitionNames())
			  .forEach(System.out::println);
			
			System.out.println("***************************");
			
			System.out.println("Value for Created Bean*************");
			
			System.out.println(context.getBean("name"));
			
			System.out.println(context.getBean("age"));
			
			context.getBean(GameRunner.class).run();
		}

	}

}
```
# 64. Step-09 Java Annotation Config Vs Xml Config
![alt text](image-254.png)![alt text](image-255.png)
# 65. Step-10 About Stereotype annotation
![alt text](image-256.png)![alt text](image-257.png)
# 66. Step11. Spring Annotation
![alt text](image-258.png)![alt text](image-259.png)
# 67. Step12. Review
![alt text](image-260.png)
# 68. Step13 Big Picture
![alt text](image-261.png)![alt text](image-262.png)![alt text](image-263.png)![alt text](image-264.png)
 # Quiz-8
 ![alt text](image-265.png)![alt text](image-266.png)![alt text](image-267.png)![alt text](image-268.png)![alt text](image-269.png)![alt text](image-270.png)![alt text](image-271.png)![alt text](image-272.png)
 # 69. Stay Up to date with technology changes
 ![alt text](image-273.png)
# Section 10: Maven
# 71. Step 01: Intro
![alt text](image-274.png)![alt text](image-275.png)
# 72. Step2. Creating Spring boot project with Maven
![alt text](image-276.png)
# 73. Step3
![alt text](image-277.png)![alt text](image-278.png)![alt text](image-279.png)![alt text](image-280.png)![alt text](image-281.png)![alt text](image-282.png)![alt text](image-283.png)![alt text](image-284.png)![alt text](image-285.png)![alt text](image-286.png)![alt text](image-287.png)![alt text](image-288.png)![alt text](image-289.png)![alt text](image-290.png)
# 74. Step-04
![alt text](image-291.png)![alt text](image-292.png)![alt text](image-293.png)![alt text](image-294.png)![alt text](image-295.png)![alt text](image-296.png)![alt text](image-297.png)![alt text](image-298.png)![alt text](image-299.png)![alt text](image-300.png)![alt text](image-301.png)![alt text](image-302.png)![alt text](image-303.png)![alt text](image-304.png)
# 75. Step5
![alt text](image-305.png)![alt text](image-306.png)![alt text](image-307.png)![alt text](image-308.png)![alt text](image-309.png)
# 76. Step-6
![alt text](image-310.png)![alt text](image-311.png)![alt text](image-312.png)![alt text](image-313.png)![alt text](image-314.png)![alt text](image-315.png)![alt text](image-316.png)![alt text](image-317.png)
# 77.Step-07 Maven Works
![alt text](image-318.png)![alt text](image-319.png)![alt text](image-320.png)![alt text](image-321.png)![alt text](image-322.png)![alt text](image-323.png)![alt text](image-324.png)![alt text](image-325.png) 
 # 78. Play with Maven Commands
 ![alt text](image-326.png)![alt text](image-327.png)![alt text](image-328.png)![alt text](image-329.png)![alt text](image-330.png)![alt text](image-331.png)![alt text](image-332.png)![alt text](image-333.png)![alt text](image-334.png)![alt text](image-335.png)
 # 79. Step9 How are spring project versioned?
 ![alt text](image-336.png)![alt text](image-337.png)![alt text](image-338.png)![alt text](image-339.png)![alt text](image-340.png)![alt text](image-341.png)
 # Quiz-9
 ![alt text](image-342.png)![alt text](image-343.png)![alt text](image-344.png)
 # 80. How to decide your goal
![alt text](image-345.png)
# Section-11 Getting started with Spring boot
# 82. Step1
![alt text](image-346.png)![alt text](image-347.png)
# 83. step-2  
![alt text](image-348.png)![alt text](image-349.png)![alt text](image-350.png)![alt text](image-351.png)
# 84. Step-3 Setting up new spring boot project
![alt text](image-352.png)![alt text](image-353.png)![alt text](image-354.png)
# 85. Step-4 Build it
![alt text](image-355.png)![alt text](image-356.png)![alt text](image-357.png)![alt text](image-358.png)![alt text](image-359.png)
### CourseController
```java
package com.in28minutes.springboot.learn_spring_boot;

import java.util.Arrays;
import java.util.List;

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class CourseController {

	@RequestMapping("/courses")
	public List<Course> retrieveAllCourses() {

		return Arrays.asList(
				new Course(1, "Learn AWS", "in28minutes"), 
				new Course(2, "Learn DevOps", "in28minutes")
				);
	}
}
```
### Course
```java
package com.in28minutes.springboot.learn_spring_boot;

public class Course {

	private long id;
	private String name;
	private String author;

	public Course(long id, String name, String author) {
		super();
		this.id = id;
		this.name = name;
		this.author = author;
	}

	public long getId() {
		return id;
	}

	public String getName() {
		return name;
	}

	public String getAuthor() {
		return author;
	}

	@Override
	public String toString() {
		return "Course [id=" + id + ", name=" + name + ", author=" + author + "]";
	}
}
```
### LearnSpringBootApplication
```java
package com.in28minutes.springboot.learn_spring_boot;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class LearnSpringBootApplication {

	public static void main(String[] args) {
		SpringApplication.run(LearnSpringBootApplication.class, args);
	}

}
```
# 86. Step-05 Understanding the goal of Spring boot
![alt text](image-360.png)
# 87. Step-6 Understanding Spring boot starter project
![alt text](image-361.png)![alt text](image-362.png)![alt text](image-363.png)![alt text](image-364.png)![alt text](image-365.png)
# 88. Step-7 Spring boot magic AutoConfiguration
![alt text](image-366.png)![alt text](image-367.png)![alt text](image-368.png)![alt text](image-369.png)![alt text](image-370.png)![alt text](image-371.png)![alt text](image-372.png)![alt text](image-373.png)![alt text](image-374.png)![alt text](image-375.png)
### application.properties
```properties
spring.application.name=learn-spring-boot

logging.level.org.springframework=debug
```
# 89. Dev tools
![alt text](image-376.png)![alt text](image-377.png)
### pom.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.3.4</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.in28minutes.springboot</groupId>
	<artifactId>learn-spring-boot</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>learn-spring-boot</name>
	<description>Demo project for Spring Boot</description>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>17</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```
### CourseController
```java
package com.in28minutes.springboot.learn_spring_boot;

import java.util.Arrays;
import java.util.List;

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class CourseController {

	@RequestMapping("/courses")
	public List<Course> retrieveAllCourses() {

		return Arrays.asList(
				new Course(1, "Learn AWS", "in28minutes"), 
				new Course(2, "Learn DevOps", "in28minutes"),
				new Course(3, "Learn Azure", "in28minutes"),
				new Course(4, "Learn GCP", "in28minutes")
				);
	}
}
```
# 90. Step9 Get Production ready with Profiles
![alt text](image-378.png)![alt text](image-379.png)![alt text](image-380.png)![alt text](image-381.png)![alt text](image-382.png)![alt text](image-383.png)![alt text](image-384.png)
### application-prod.properties
```properties
logging.level.org.springframework=info
```
###  application-dev.properties
```properties
logging.level.org.springframework=trace
```
###  application-.properties
```properties
spring.application.name=learn-spring-boot

logging.level.org.springframework=debug
# spring.profiles.active=prod
spring.profiles.active=dev
```
# 91. Step10 Configuration Properties
![alt text](image-385.png)![alt text](image-386.png)![alt text](image-387.png)![alt text](image-388.png)![alt text](image-389.png)![alt text](image-390.png)
### CurrencyServiceConfiguration
```java
package com.in28minutes.springboot.learn_spring_boot;

import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.stereotype.Component;

@ConfigurationProperties(prefix = "currency-service")
@Component
public class CurrencyServiceConfiguration {

	private String url;
	private String userName;
	private String key;

	public String getUrl() {
		return url;
	}

	public void setUrl(String url) {
		this.url = url;
	}

	public String getUserName() {
		return userName;
	}

	public void setUserName(String userName) {
		this.userName = userName;
	}

	public String getKey() {
		return key;
	}

	public void setKey(String key) {
		this.key = key;
	}

}
```
### CurrencyConfigurationController
```java
package com.in28minutes.springboot.learn_spring_boot;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class CurrencyConfigurationController {

	@Autowired
	private CurrencyServiceConfiguration configuration;
	
	@RequestMapping("/currency-configuration")
	public CurrencyServiceConfiguration  retrieveAllCourses() {

		return configuration;
	}
}
```
### application.properties
```properties
spring.application.name=learn-spring-boot

logging.level.org.springframework=debug
# spring.profiles.active=prod
spring.profiles.active=dev

currency-service.url=http://default1.in28minutes.com
currency-service.userName=defaultUserName
currency-service.key=defaultKey
```
### application-dev.properties
```properties
logging.level.org.springframework=trace

currency-service.url=http://dev.in28minutes.com
currency-service.userName=devUserName
currency-service.key=devKey
```
# 92. Step11. Embedded Server
![alt text](image-391.png)![alt text](image-392.png)![alt text](image-393.png)![alt text](image-394.png)![alt text](image-395.png)![alt text](image-396.png)
# 93. Step12 Actuator
![alt text](image-397.png)![alt text](image-398.png)![alt text](image-399.png)![alt text](image-400.png)![alt text](image-401.png)![alt text](image-402.png)![alt text](image-403.png)![alt text](image-404.png)![alt text](image-405.png)![alt text](image-406.png)![alt text](image-407.png)![alt text](image-408.png)![alt text](image-409.png)![alt text](image-410.png)
### pom.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.3.4</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.in28minutes.springboot</groupId>
	<artifactId>learn-spring-boot</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>learn-spring-boot</name>
	<description>Demo project for Spring Boot</description>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>17</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>
		
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```
### application.properties
```properties
spring.application.name=learn-spring-boot

logging.level.org.springframework=debug
# spring.profiles.active=prod
spring.profiles.active=dev

currency-service.url=http://default1.in28minutes.com
currency-service.userName=defaultUserName
currency-service.key=defaultKey

# management.endpoints.web.exposure.include=*

management.endpoints.web.exposure.include=health,metrics
```
# 94. Step 13  Spring vs Spring Mvc vs Spring boot
![alt text](image-411.png)
# 95. Step14 Review
![alt text](image-412.png)
# Quiz-10
![alt text](image-413.png)![alt text](image-414.png)![alt text](image-415.png)
# 96. Story of in28minutes
![alt text](image-416.png)
# Section-12 JPA & Hibernate with Spring
# 98. Step-01
![alt text](image-417.png)![alt text](image-418.png)
# 99. Step-2 Setup
![alt text](image-419.png)![alt text](image-420.png)
# 100. Step-3 Launch H2 console & Creating table in H2
![alt text](image-421.png)![alt text](image-422.png)![alt text](image-423.png)![alt text](image-424.png)![alt text](image-425.png)![alt text](image-426.png)![alt text](image-427.png)![alt text](image-428.png)![alt text](image-429.png)
# 101. Step-4 Spring Jdbc
![alt text](image-430.png)![alt text](image-431.png)![alt text](image-432.png)![alt text](image-433.png)![alt text](image-434.png)![alt text](image-435.png)
# 102. Step-5 Inserting hardcoded data using Spring JDBC
![alt text](image-436.png)![alt text](image-437.png)![alt text](image-438.png)
### application.properties
```properties
spring.application.name=learn-jpa-and-hibernate
spring.h2.console.enabled=true
spring.datasource.url=jdbc:h2:mem:testdb
```
### schema.sql
```sql
create table course
(
	id bigint not null,
	name varchar(255) not null,
	author varchar(255) not null,
	primary key(id)
);
```
### CourseJdbcRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.stereotype.Repository;

@Repository
public class CourseJdbcRepository {

	@Autowired
	private JdbcTemplate springJdbcTemplate;

	private static String INSERT_QUERY = 
			"""
			  insert into course(id,name,author)
			  values (1,'Learn AWS','in28minutes')
		    """;

	public void insert() {
		springJdbcTemplate.update(INSERT_QUERY);
	}
}
```
### CourseJdbcCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

@Component
public class CourseJdbcCommandLineRunner implements CommandLineRunner{

	@Autowired
	private CourseJdbcRepository repository;
	
	@Override
	public void run(String... args) throws Exception {
		repository.insert();		
	}

}
```
# 103.Step-6 Inserting and Deleting Data
![alt text](image-439.png)![alt text](image-440.png)![alt text](image-441.png)![alt text](image-442.png)![alt text](image-443.png)![alt text](image-444.png)![alt text](image-445.png)
## Inserting Course Object
### Course
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course;

public class Course {

	private long id;
	private String name;
	private String author;
	
	
	public Course() {
		
	}
	public Course(long id, String name, String author) {
		super();
		this.id = id;
		this.name = name;
		this.author = author;
	}
	
	public long getId() {
		return id;
	}
	public String getName() {
		return name;
	}
	public String getAuthor() {
		return author;
	}

	@Override
	public String toString() {
		return "Course [id=" + id + ", name=" + name + ", author=" + author + "]";
	}
}
```
### CourseJdbcRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.stereotype.Repository;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

@Repository
public class CourseJdbcRepository {

	@Autowired
	private JdbcTemplate springJdbcTemplate;

	private static String INSERT_QUERY = 
			"""
			  insert into course(id,name,author)
			  values (?,?,?);
		    """;

	public void insert(Course course) {
		springJdbcTemplate.update(INSERT_QUERY,course.getId(),course.getName(),course.getAuthor());
	}
}
```
### CourseJdbcCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

@Component
public class CourseJdbcCommandLineRunner implements CommandLineRunner{

	@Autowired
	private CourseJdbcRepository repository;
	
	@Override
	public void run(String... args) throws Exception {
		repository.insert(new Course(1, "learn AWs Now!", "in28Min"));	
		repository.insert(new Course(2, "learn Azure Now!", "in28Min"));	
		repository.insert(new Course(3, "learn DevOps Now!", "in28Min"));	
	}
}
```
## Deleting Query
### CourseJdbcRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.stereotype.Repository;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

@Repository
public class CourseJdbcRepository {

	@Autowired
	private JdbcTemplate springJdbcTemplate;

	private static String INSERT_QUERY = 
			"""
			  insert into course(id,name,author)
			  values (?,?,?);
		    """;
	
	private static String DELETE_QUERY = 
			"""
			  delete from course
			    where id = ?;
		    """;

	public void insert(Course course) {
		springJdbcTemplate.update(INSERT_QUERY,course.getId(),course.getName(),course.getAuthor());
	}
	
	public void deleteById(long id) {
		springJdbcTemplate.update(DELETE_QUERY,id);
	}
}
```
###  CourseJdbcCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

@Component
public class CourseJdbcCommandLineRunner implements CommandLineRunner{

	@Autowired
	private CourseJdbcRepository repository;
	
	@Override
	public void run(String... args) throws Exception {
		repository.insert(new Course(1, "learn AWs Now!", "in28Min"));	
		repository.insert(new Course(2, "learn Azure Now!", "in28Min"));	
		repository.insert(new Course(3, "learn DevOps Now!", "in28Min"));	
		
		repository.deleteById(1);
	}
}
```
# 104. Querying Data using Spring JDBC
![alt text](image-446.png)![alt text](image-447.png)![alt text](image-448.png)![alt text](image-449.png)![alt text](image-450.png)![alt text](image-451.png)![alt text](image-452.png)
### Course
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course;

public class Course {

	private long id;
	private String name;
	private String author;
	
	
	public Course() {
		
	}
	public Course(long id, String name, String author) {
		super();
		this.id = id;
		this.name = name;
		this.author = author;
	}
	
	public long getId() {
		return id;
	}
	public String getName() {
		return name;
	}
	public String getAuthor() {
		return author;
	}
	
	public void setId(long id) {
		this.id = id;
	}
	public void setName(String name) {
		this.name = name;
	}
	public void setAuthor(String author) {
		this.author = author;
	}
	@Override
	public String toString() {
		return "Course [id=" + id + ", name=" + name + ", author=" + author + "]";
	}
}
```
### CourseJdbcRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jdbc.core.BeanPropertyRowMapper;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.stereotype.Repository;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

@Repository
public class CourseJdbcRepository {

	@Autowired
	private JdbcTemplate springJdbcTemplate;

	private static String INSERT_QUERY = 
			"""
			  insert into course(id,name,author)
			  values (?,?,?);
		    """;
	
	private static String DELETE_QUERY = 
			"""
			  delete from course
			    where id = ?;
		    """;
	
	private static String SELECT_QUERY = 
			"""
			  select * from course
			    where id = ?;
		    """;

	public void insert(Course course) {
		springJdbcTemplate.update(INSERT_QUERY,course.getId(),course.getName(),course.getAuthor());
	}
	
	public void deleteById(long id) {
		springJdbcTemplate.update(DELETE_QUERY,id);
	}
	
	public Course findById(long id) {
		return springJdbcTemplate.queryForObject(SELECT_QUERY,
								new BeanPropertyRowMapper<>(Course.class) ,id);
	}
}
```
### CourseJdbcCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

@Component
public class CourseJdbcCommandLineRunner implements CommandLineRunner{

	@Autowired
	private CourseJdbcRepository repository;
	
	@Override
	public void run(String... args) throws Exception {
		repository.insert(new Course(1, "learn AWs Now!", "in28Min"));	
		repository.insert(new Course(2, "learn Azure Now!", "in28Min"));	
		repository.insert(new Course(3, "learn DevOps Now!", "in28Min"));	
		
		repository.deleteById(1);
		
		System.out.println("=============>" +repository.findById(2));
		System.out.println("=============>" +repository.findById(3));
	}

}
```
# 105. Step8 Getting started with JPA and Entity Manager.
![alt text](image-453.png)![alt text](image-454.png)![alt text](image-455.png)![alt text](image-456.png)![alt text](image-457.png)![alt text](image-458.png)![alt text](image-459.png)![alt text](image-460.png)
### application.properties
```properties
spring.application.name=learn-jpa-and-hibernate
spring.h2.console.enabled=true
spring.datasource.url=jdbc:h2:mem:testdb
spring.jpa.show-sql=true
```
### Course
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course;

import jakarta.persistence.Entity;
import jakarta.persistence.Id;

@Entity
public class Course {

	@Id
	private long id;	

	private String name;
	private String author;
	
	
	public Course() {
		
	}
	public Course(long id, String name, String author) {
		super();
		this.id = id;
		this.name = name;
		this.author = author;
	}
	
	public long getId() {
		return id;
	}
	public String getName() {
		return name;
	}
	public String getAuthor() {
		return author;
	}
	
	public void setId(long id) {
		this.id = id;
	}
	public void setName(String name) {
		this.name = name;
	}
	public void setAuthor(String author) {
		this.author = author;
	}
	@Override
	public String toString() {
		return "Course [id=" + id + ", name=" + name + ", author=" + author + "]";
	}
}
```
### CourseJpaRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jpa;

import org.springframework.stereotype.Repository;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;

import jakarta.persistence.EntityManager;
import jakarta.persistence.PersistenceContext;
import jakarta.transaction.Transactional;

@Repository
@Transactional
public class CourseJpaRepository {

	@PersistenceContext
	private EntityManager entityManager;
	
	public void insert(Course course) {
		entityManager.merge(course);
	}
	
	public Course findById(long id) {
		return entityManager.find(Course.class, id); 
	}
	
	public void deleteById(long id) {
		Course course = entityManager.find(Course.class, id); 
		 entityManager.remove(course);; 
	}
}
```
### CourseJpaCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jdbc;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;
import com.in28minutes.springboot.learn_jpa_and_hibernate.course.jpa.CourseJpaRepository;

@Component
public class CourseJpaCommandLineRunner implements CommandLineRunner{

	@Autowired
	private CourseJpaRepository repository;
	
	@Override
	public void run(String... args) throws Exception {
		repository.insert(new Course(1, "learn AWs Now1!", "in28Min"));	
		repository.insert(new Course(2, "learn Azure Now1!", "in28Min"));	
		repository.insert(new Course(3, "learn DevOps Now1!", "in28Min"));	
		
		repository.deleteById(1);
		
		System.out.println("=============>" +repository.findById(2));
		System.out.println("=============>" +repository.findById(3));
	}

}
```
# 106. step9. Exploring Magic of Spring Data JPA
![alt text](image-461.png)![alt text](image-462.png)
# 107. Step-10 Spring Data JPA
![alt text](image-463.png)![alt text](image-464.png)![alt text](image-465.png)
### CourseSpringDataJpaRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course;

import org.springframework.data.jpa.repository.JpaRepository;

public interface CourseSpringDataJpaRepository extends JpaRepository<Course, Long> {

}
```
### CourseCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jpa;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;
import com.in28minutes.springboot.learn_jpa_and_hibernate.course.CourseSpringDataJpaRepository;

@Component
public class CourseCommandLineRunner implements CommandLineRunner {

	@Autowired
	private CourseSpringDataJpaRepository repository;

	@Override
	public void run(String... args) throws Exception {
		repository.save(new Course(1, "learn AWs Now! JPA", "in28Min"));
		repository.save(new Course(2, "learn Azure Now! JPA", "in28Min"));	
		repository.save(new Course(3, "learn DevOps Now! JPA", "in28Min"));	
		
		repository.deleteById(1L);
		
		System.out.println("---> "+repository.findById(2l));
		System.out.println("---> "+repository.findById(3L));
	}

}
```
# 108. Step11. Exploring features of SpringDataJPA
![alt text](image-466.png)![alt text](image-467.png)![alt text](image-468.png)![alt text](image-469.png)

# 108
### CourseSpringDataJpaRepository
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course;

import java.util.List;

import org.springframework.data.jpa.repository.JpaRepository;

public interface CourseSpringDataJpaRepository extends JpaRepository<Course, Long> {

	List<Course> findByAuthor(String author);

	List<Course> findByName(String name);

}
```
### CourseCommandLineRunner
```java
package com.in28minutes.springboot.learn_jpa_and_hibernate.course.jpa;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.in28minutes.springboot.learn_jpa_and_hibernate.course.Course;
import com.in28minutes.springboot.learn_jpa_and_hibernate.course.CourseSpringDataJpaRepository;

@Component
public class CourseCommandLineRunner implements CommandLineRunner {

	@Autowired
	private CourseSpringDataJpaRepository repository;

	@Override
	public void run(String... args) throws Exception {
		repository.save(new Course(1, "learn AWs Now! JPA", "in28Min"));
		repository.save(new Course(2, "learn Azure Now! JPA", "in28Min"));
		repository.save(new Course(3, "learn DevOps Now! JPA", "in28Min"));
		repository.deleteById(1L);
		System.out.println("---> " + repository.findById(2l));
		System.out.println("---> " + repository.findById(3L));
		System.out.println("**************************************");
		System.out.println("======>" + repository.findAll());
		System.out.println("======>" + repository.count());
		System.out.println("======>" + repository.findByAuthor("in28Min"));
		System.out.println("======>" + repository.findByAuthor(""));
		System.out.println("======>" + repository.findByName("learn DevOps Now! JPA"));
		System.out.println("======>" + repository.findByName(""));
		System.out.println("======>" + repository.findByName("learn AWs Now! JPA"));
	}
}
```
# 109. Step12 Understand diff between Hibernate and JPA
![alt text](image-470.png)![alt text](image-471.png)![alt text](image-472.png)
# 110.  What should I do, when I face challenge.
![alt text](image-473.png)
# Section-13 Web App
# 112. Step0
![alt text](image-474.png)![alt text](image-475.png)
# 113. Step1 
![alt text](image-476.png)
# 114. Step2 
![alt text](image-477.png)![alt text](image-478.png)![alt text](image-479.png)
# 115. Step-3 Return Simple HelloWorld response from our web app
![alt text](image-480.png)![alt text](image-481.png)![alt text](image-482.png)![alt text](image-483.png)![alt text](image-484.png)

### SayHelloController
```java
package com.in28minutes.springboot.myfirstwebapp.hello;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class SayHelloController {
	
	@RequestMapping("say-hello")
	@ResponseBody
	public String sayHello() {
		return "Hello! What are you learning today";
	}

}
```
# 116. Step4-1 Enhancing Controller to provide html response
![alt text](image-485.png)![alt text](image-486.png)![alt text](image-487.png)
### SayHelloController
```java
package com.in28minutes.springboot.myfirstwebapp.hello;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class SayHelloController {

	@RequestMapping("say-hello")
	@ResponseBody
	public String sayHello() {
		return "Hello! What are you learning today1";
	}
	
	@RequestMapping("say-hello-html")
	@ResponseBody
	public String sayHelloHtml() {
		
		StringBuffer sb = new StringBuffer();
		sb.append("<html>");
		sb.append("<head>");
		sb.append("<title>");
		sb.append("My first Html Page1");
		sb.append("</title>");
		sb.append("</head>");
		sb.append("<body>");
		sb.append("My first Html page with body1");
		sb.append("</body>");
		sb.append("</html>");
		
		return sb.toString();
	}
}
```
# 117. Step4-2 
https://github.com/in28minutes/spring-boot-master-class
![alt text](image-488.png)![alt text](image-489.png)![alt text](image-490.png)
# 119. Step5.  Redirect to Jsp
![alt text](image-491.png)![alt text](image-492.png)![alt text](image-493.png)![alt text](image-494.png)![alt text](image-495.png)![alt text](image-496.png)![alt text](image-497.png)![alt text](image-498.png)![alt text](image-499.png)![alt text](image-500.png)![alt text](image-501.png)![alt text](image-502.png)![alt text](image-503.png)
### pom.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.3.4</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.in28minutes.springboot</groupId>
	<artifactId>myfirstwebapp</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>myfirstwebapp</name>
	<description>Demo project for Spring Boot</description>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>17</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
			<scope>provided</scope>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
			<scope>runtime</scope>
			<optional>true</optional>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```
### sayHello.jsp
```jsp
<html>
	<head>
		<title>My first Html Page -Jsp1</title>
	</head>
	
	<body>
		My first Html page with body -Jsp12
	</body>
</html>
```
### SayHelloController
```java
package com.in28minutes.springboot.myfirstwebapp.hello;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class SayHelloController {

	@RequestMapping("say-hello")
	@ResponseBody
	public String sayHello() {
		return "Hello! What are you learning today1";
	}
	
	@RequestMapping("say-hello-html")
	@ResponseBody
	public String sayHelloHtml() {
		
		StringBuffer sb = new StringBuffer();
		sb.append("<html>");
		sb.append("<head>");
		sb.append("<title>");
		sb.append("My first Html Page1");
		sb.append("</title>");
		sb.append("</head>");
		sb.append("<body>");
		sb.append("My first Html page with body1");
		sb.append("</body>");
		sb.append("</html>");
		
		return sb.toString();
	}
	
	
	@RequestMapping("say-hello-jsp")
	public String sayHelloJsp() {
		return "sayHello";
	}
}
```
### application.properties
```properties
spring.application.name=myfirstwebapp

spring.mvc.view.prefix=/WEB-INF/jsp/
spring.mvc.view.suffix=.jsp

logging.level.org.springframework=debug
```
# 120. Step-6
![alt text](image-504.png)![alt text](image-505.png)
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
# 121. Step-7 How does Request Response work.
![alt text](image-506.png)![alt text](image-507.png)![alt text](image-508.png)![alt text](image-509.png)![alt text](image-510.png)![alt text](image-511.png)![alt text](image-512.png)![alt text](image-513.png)![alt text](image-514.png)
# 122. Step8 QueryParam and RequestParam
![alt text](image-515.png)![alt text](image-516.png)![alt text](image-517.png)![alt text](image-518.png)![alt text](image-519.png)![alt text](image-520.png)
### LoginController
```java
package com.in28minutes.springboot.myfirstwebapp.login;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class LoginController {

	@RequestMapping("login")
	public String getLoginPage(@RequestParam String name, ModelMap model) {

		model.put("name", name);

		System.out.println("Request param is ======>" + name);
		return "login";
	}
}
```
###
```jsp
<html>
	<head>
		<title> Login Page</title>
	</head>
	<body>
		Welcome to the login page ${name}!1
	</body>
</html>
```
# 123. Step9 Logging
![alt text](image-521.png)![alt text](image-522.png)![alt text](image-523.png)![alt text](image-524.png)![alt text](image-525.png)![alt text](image-526.png)![alt text](image-527.png)![alt text](image-528.png)![alt text](image-529.png)![alt text](image-530.png)![alt text](image-531.png)![alt text](image-532.png)![alt text](image-533.png)
# 124 Step10. Understanding Dispatcher Servlet, model1 etc
![alt text](image-534.png)![alt text](image-535.png)![alt text](image-536.png)![alt text](image-537.png)![alt text](image-538.png)![alt text](image-539.png)![alt text](image-540.png)![alt text](image-541.png)
# 125. Step11 Creating a login Form
![alt text](image-542.png)![alt text](image-543.png)![alt text](image-544.png)![alt text](image-545.png)![alt text](image-546.png)![alt text](image-547.png)
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
### login.jsp
```jsp
<html>
	<head>
		<title> Login Page</title>
	</head>
	<body>
		Welcome to the login page !
		<form method="post">
			Name: <input type="text" name="name">
			Password:<input type="password" name="password">
			<input type="submit">
		</form>
	</body>
</html>
```
# 126. Step12. Displaying login Credential in a Jsp using Model.
![alt text](image-548.png)![alt text](image-549.png)![alt text](image-550.png)![alt text](image-551.png)![alt text](image-552.png)![alt text](image-553.png)![alt text](image-554.png)![alt text](image-555.png)![alt text](image-556.png)![alt text](image-557.png)![alt text](image-558.png)
### LoginController
```java
package com.in28minutes.springboot.myfirstwebapp.login;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class LoginController {

	@RequestMapping(value = "login",method = RequestMethod.GET)
	public String getLoginPage() {

		return "login";
	}
	
	@RequestMapping(value = "login",method = RequestMethod.POST)
	public String gotoWelcomePage(@RequestParam String name,
			@RequestParam String password,
			ModelMap model) {
		
		model.put("name", name);
		model.put("password", password);
		
		return "welcome";
	}

}
```
### welcome.jsp
```jsp
<html>
	<head>
		<title> Welcome Page</title>
	</head>
	<body>
		<div> Welcome to in28minutes</div> 	
		<div>Your Name : ${name }</div>		
		<div>Your Password : ${password }</div>		
	</body>
</html>
```
# 127: Step13 Add harcoded validation of userId an Password.
![alt text](image-559.png)![alt text](image-560.png)![alt text](image-561.png)![alt text](image-562.png)![alt text](image-563.png)![alt text](image-564.png)![alt text](image-565.png)![alt text](image-566.png)![alt text](image-567.png)![alt text](image-568.png)
### AuthenticationService
```java
package com.in28minutes.springboot.myfirstwebapp.login;

import org.springframework.stereotype.Service;

@Service
public class AuthenticationService {
	
	
	public boolean authenticate(String userName,String password) {
		boolean isValidUserName = userName.equalsIgnoreCase("in28minutes");
		boolean isValidPassword = password.equalsIgnoreCase("dummy");
		
		return isValidUserName && isValidPassword;
	}

}
```
### LoginController
```java
package com.in28minutes.springboot.myfirstwebapp.login;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
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
### welcome.jsp
```jsp
<html>
	<head>
		<title> Welcome Page</title>
	</head>
	<body>
		<div> Welcome to in28minutes</div> 	
		<div>Your Name : ${name }</div>			
	</body>
</html>
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
# 128. Step14. ToDo Service
![alt text](image-569.png)![alt text](image-570.png)![alt text](image-571.png)![alt text](image-572.png)![alt text](image-573.png)![alt text](image-574.png)
# 129. Step15. Creating first version of List Todos page
![alt text](image-575.png)![alt text](image-576.png)![alt text](image-577.png)
# 128 and 129
### Todo
```java
package com.in28minutes.springboot.myfirstwebapp.todo;

import java.time.LocalDate;

public class Todo {

	private int id;
	private String username;
	private String description;
	private LocalDate targetDate;
	private boolean done;

	public Todo(int id, String username, String description, LocalDate targetDate, boolean done) {
		super();
		this.id = id;
		this.username = username;
		this.description = description;
		this.targetDate = targetDate;
		this.done = done;
	}

	public int getId() {
		return id;
	}

	public void setId(int id) {
		this.id = id;
	}

	public String getUsername() {
		return username;
	}

	public void setUsername(String username) {
		this.username = username;
	}

	public String getDescription() {
		return description;
	}

	public void setDescription(String description) {
		this.description = description;
	}

	public LocalDate getTargetDate() {
		return targetDate;
	}

	public void setTargetDate(LocalDate targetDate) {
		this.targetDate = targetDate;
	}

	public boolean isDone() {
		return done;
	}

	public void setDone(boolean done) {
		this.done = done;
	}

	@Override
	public String toString() {
		return "Todo [id=" + id + ", username=" + username + ", description=" + description + ", targetDate="
				+ targetDate + ", done=" + done + "]";
	}

}
```
### TodoService
```java
package com.in28minutes.springboot.myfirstwebapp.todo;

import java.time.LocalDate;
import java.util.ArrayList;
import java.util.List;

import org.springframework.stereotype.Service;

@Service
public class TodoService {

	private static List<Todo> todos = new ArrayList<>();

	static {
		todos.add(new Todo(1, "in28min", "Learn AWS", LocalDate.now().plusYears(1), false));
		todos.add(new Todo(2, "in28min", "Learn DevOps", LocalDate.now().plusYears(2), false));
		todos.add(new Todo(3, "in28min", "Learn Full Stack Development", LocalDate.now().plusYears(3), false));
	}
	
	public List<Todo> findByUsername(String username){
		return todos;
	}
}
```
### TodoController
```java
package com.in28minutes.springboot.myfirstwebapp.todo;

import java.util.List;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;

@Controller
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
### listTodo.jsp
```jsp
<html>
	<head>
		<title> Todo Page</title>
	</head>
	<body>
		<div> Welcome to in28minutes</div> 	
		<div>Your todos are ${todos }</div>			
	</body>
</html>
```
# 131. Step16. Session vs Model vs Request - @SessionAttributes
![alt text](image-578.png)![alt text](image-579.png)![alt text](image-580.png)![alt text](image-581.png)![alt text](image-582.png)![alt text](image-583.png)![alt text](image-584.png)![alt text](image-585.png)![alt text](image-586.png)![alt text](image-587.png)![alt text](image-588.png)![alt text](image-589.png)![alt text](image-590.png)
# aabcc

 

