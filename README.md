# Patterns Refresh
Real reason why I'm implementing this is to remember that patterns are not just for interviews!
This project to refresh a set of probable working solutions for particular recurring problems.
**Note** Download the code and search by labels as "//LD_MEDIATOR_002" to match description and code.

## Creational Patterns - Creation of objects and classes

### Abstract Factory
Abstract Factory, Creates an instance of several families of classes

### Builder
Separates object construction from its representation

### Factory
It is used to create objects.
In Factory pattern, we create object without exposing the creation logic. 
In this pattern, an interface is used for creating an object, but let subclass 
decide which class to instantiate.

The benefit is that the client code(calling code) can just say "give me an object that 
can do XYZ" without knowing what is the actual class that can do "XYZ". 

EXAMPLE:
the factory method that returns a product(a distributor).  Each of the distributor implements 
the IDistributor interface, which has the ShipBook method. The client code just say 
"give me a distributor that can ShipBook" without having to know which distributor you 
are going to return.

RESOURCES
- http://www.dofactory.com/net/factory-method-design-pattern
- http://www.dotnetlead.com/design-patterns/factory-method

### Prototype
A fully initialized instance to be copied or cloned

### Singleton - //LD_SINGLETON_000
Ensure a class has only one instance and provide a global point of access to it.
Singleton pattern creates a class which can have a single object throughout the application, so that whenever any other object tries to access the object of the class, it will access the same object always.

## Structural Patterns - Class and Object Composition

### Adapter
Match interfaces of different classes

### Bridge
Separates an object�s interface from its implementation

### Composite
A tree structure of simple and composite objects

### Decorator
Add responsibilities to objects dynamically

### Facade
A single class that represents an entire subsystem

### Flyweight
A fine-grained instance used for efficient sharing

### Proxy
An object representing another object

## Behavioral Patterns - Communication between class and objects

### Chain of Responsability
A way of passing a request between a chain of objects

### Command
Encapsulate a command request as an object

### Interpreter
A way to include language elements in a program

### Iterator
Sequentially access the elements of a collection

### Mediator //LD_MEDIATOR_000
This pattern allows multiple objects to communicate with each other�s without knowing each other�s structure. 
The mediator pattern is a behavioral design pattern that promotes loose coupling between objects and helps to organize the code for inter-object communications.

Imagine an application in which there are many objects that are communicating with each other. The mediator design pattern is useful when the number of objects grows so large that it becomes difficult to maintain the references to the objects. The mediator is essentially an object that encapsulates how one or more objects interact with each other. The mediator design pattern controls how these objects communicate, and helps to reduce the number of dependencies among them that you have to manage.

Project Structure:
IMediator
  - This is an interface that defines operations which can be called by colleague objects for communication.
  - //LD_MEDIATOR_001 the Mediator has the ability to send the specific message "msg" created by a caller. The caller will be a concrete "Colleague"

Mediator
  - This is a class that implement the communication operations of the Mediator interface.
  - //LD_MEDIATOR_002 the concrete "Mediator" has referiment to the objects that need to communicate
  - //LD_MEDIATOR_003 the concrete "Mediator" cointain the logic to distribute the messages

ColleagueAbstract
  - This is a class that defines a single, protected field that holds a reference to a mediator.
  - //LD_MEDIATOR_004 this class has a reference to the "Mediator"

Colleague One/Two/Three
  - These are the classes that communicate with each other via the mediator.
  - //LD_MEDIATOR_005 any concrete "Colleague" class can "Send" and "Receive" messages from the "Mediator". The class use a referement to "Mediator" 

Execution of the test:
  - //LD_MEDIATOR_006

Example to Implement in .net Core --> https://www.stevejgordon.co.uk/cqrs-using-mediatr-asp-net-core

### Memento
Capture and restore an object's internal state

### Observer
A way of notifying change to a number of classes

### State
Alter an object's behavior when its state changes

### Strategy
Encapsulates an algorithm inside a class

### Template Method
Method	Defer the exact steps of an algorithm to a subclass

### Visitor
Defines a new operation to a class without change
