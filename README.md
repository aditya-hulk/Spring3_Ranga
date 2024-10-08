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
 
 
 
 
 
 
 


 
 
 
 
 
 
 

