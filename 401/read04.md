

  
# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

### Classes and Objects


A class is a user-defined blueprint or prototype from which objects are created. Classes provide a means of bundling data and functionality together. Creating a new class creates a new type of object, allowing new instances of that type to be made. Each class instance can have attributes attached to it for maintaining its state. Class instances can also have methods (defined by their class) for modifying their state.

Class Objects

An Object is an instance of a Class. A class is like a blueprint while an instance is a copy of the class with actual values. It’s not an idea anymore, it’s an actual dog, like a dog of breed pug who’s seven years old. You can have many dogs to create many different instances, but without the class as a guide, you would be lost, not knowing what information is required.
An object consists of : 

+ State: It is represented by the attributes of an object. It also reflects the properties of an object.
+ Behavior: It is represented by the methods of an object. It also reflects the response of an object to other objects.
+ Identity: It gives a unique name to an object and enables one object to interact with other objects.

The self

Class methods must have an extra first parameter in the method definition. We do not give a value for this parameter when we call the method, Python provides it.
If we have a method that takes no arguments, then we still have to have one argument.

## Thinking Recursively
A recursive function is a function defined in terms of itself via self-referential expressions. This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result.

## Pytest Fixtures and Coverage 
Coverage.py is a tool for measuring code coverage of Python programs. It monitors your program, noting which parts of the code have been executed, then analyzes the source to identify code that could have been executed but was not.

Coverage measurement is typically used to gauge the effectiveness of tests. It can show which parts of your code are being exercised by tests, and which are not.

pytest fixtures are functions attached to the tests which run before the test function is executed. Fixtures are a set of resources that have to be set up before and cleaned up once the Selenium test automation execution is completed.

