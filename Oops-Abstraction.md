## Abstraction Defination:
Abstraction is an OOPS concept to construct the structure of the real world objects. 

During this construction only the general states and behaviors are taken and more specific states and behaviors are left aside for the implementers.
The abstraction provides a way to create user-defined data types for designing real-world objects having same properties.

Abstraction is primarily used to hide the complexity. It indicates the necessary characteristics of 
  an object that differentiates it from all other types of objects. An abstraction concentrates on the external aspect of an object. 

### Types of Abstraction:
- Procedural abstraction – It includes series of the instructions having the specified functions.
- Data abstraction – It is set of data that specifies and describes a data object.
- Control abstraction – It is program control mechanism where interior details are not specified.

Abstraction shows the relevant information and rejects the non-essential details.

- Abstraction solves the issues at the design level.
- Abstraction is about hiding unwanted details while showing most essential information.
- Abstraction allows focussing on what the information object must contain
- Abstract method can't be Private. 
- Data Member can be Private/Protected/Public but this can't be abstract.

`abstract class Day1 {

	protected Day1() {}
	protected abstract void testMe();
	public abstract void testMe1();
	abstract void testMe2();
	
	private void testMe3() {
		
	}
	
	public String name;
	private String name1;
	protected String name2;
	//abstract String name3;	//This is not a valid varibale declaration.
}`

# Questions:
### Can abstract class have constructors in Java?
Yes, abstract class can declare and define constructor in Java. Since you can not create instance of abstract class,  constructor can only be called during constructor chaining, i.e. when you create instance of concrete implementation class. 

Now some interviewer, ask what is the purpose of constructor, if you can not instantiate abstract class? Well, it can still be used to initialize common variables, which are declared inside abstract class, and used by various implementation. 

Also even if you don’t provide any constructor, compiler will add default no argument constructor in an abstract class, without that your subclass will not compile, since first statement in any constructor implicitly calls super(), default super class constructor in Java.
### Can abstract class implements interface in Java? does they require to implement all methods?
Yes, abstract class can implement interface by using implements keyword. Since they are abstract, they don’t need to implement all methods. It’s good practice to provide an abstract base class, along with an interface to declare Type. One example of this is java.util.List interface and corresponding java.util.AbstractList abstract class. Since AbstractList implements all common methods,  concrete implementations like LinkedList and ArrayList are free from burden of implementing all methods, had they implemented List interface directly. It’s best of both world, you can get advantage of interface for declaring type, and flexibility of abstract class to implement common behavior at one place. Effective Java has a nice chapter on how to use interface and abstract class in Java, which is worth reading.
### Can abstract class be final in Java?
No, abstract class can not be final in Java. Making them final will stop abstract class from being extended, which is the only way to use abstract class. They are also opposite of each other, abstract keyword enforces to extend a class, for using it, on the other hand, final keyword prevents a class from being extended. In real world also, abstract signifies incompleteness, while final is used to demonstrate completeness. Bottom line is, you can not make your class abstract and final in Java, at same time, it’s a compile time error.
### Can abstract class have static methods in Java?
Yes, abstract class can declare and define static methods, nothing prevents from doing that. But, you must follow guidelines for making a method static in Java, as it’s not welcomed in a object oriented design, because static methods can not be overridden in Java. It’s very rare, you see static methods inside abstract class, but as I said, if you have very good reason of doing it, then nothing stops you.
### Can you create instance of abstract class?
No, you can not create instance of abstract class in Java, they are incomplete. Even though, if your abstract class don’t contain any abstract method, you can not create instance of it. By making a class abstract,  you told compiler that, it’s incomplete and should not be instantiated. Java compiler will throw error, when a code tries to instantiate abstract class.
### Is it necessary for abstract class to have abstract method?
No, It’s not mandatory for an abstract class to have any abstract method. You can make a class abstract in Java, by just using abstract keyword in class declaration. Compiler will enforce all structural restriction, applied to abstract class, e.g. now allowing to create any instance. By the way, it’s debatable whether you should have abstract method inside abstract class or interface. In my opinion, abstract class should have abstract methods, because that’s the first thing programmer assumes, when he see that class. That would also go nicely along principle of least surprise.
### When do you favor abstract class over interface?
Since it’s almost impossible to add a new method on a published interface, it’s better to use abstract class, when evolution is concern. Abstract class in Java evolves better than interface. Similarly, if you have too many methods inside interface, you are creating pain for all it’s implementation, consider providing an abstract class for default implementation. This is the pattern followed in Java collection package, you can see AbstractList provides default implementation for List interface.
But from 8.0 we can do by using **default Method**
### What is abstract method in Java?
An abstract method is a method without body. You just declare method, without defining it and use abstract keyword in method declaration.  All method declared inside Java Interface are by default abstract. Here is an example of abstract method in Java

                public void abstract printVersion();

Now, In order to implement this method, you need to extend abstract class and override this method.
### Can abstract class contains main method in Java ?
Yes, abstract class can contain main method, it just another static method and you can execute Abstract class with main method, until you don’t create any instance.

### Can We Declare Abstract Method In Non-abstract Class?
No, we can't declare abstract method in non-abstract class.
For example:

`class Demo {
	// abstract void show();	//Above example will throw compile time error.
}`
### Can We Declare Abstract Method As Static?
No, we can't use static keyword with abstract method.
### Can We Declare Abstract Method As Final?
No, we cannot use final keyword with abstract class.
### Can We Declare Abstract Method As Private?
No, we cannot declare abstract method as private.
