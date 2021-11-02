
# Classes and Objects 

### Objects 

**are an encapsulation of variables and functions into a single entity.** 

**Objects get their variables and functions from classes.** 

### Classes 

**are essentially a template to create your objects.** 

* *the variable holds an object of the class that contains the variable and the function defined within the class.* 

### Accessing Object Variables 

**You can create multiple different objects that are of the same class. However, each object contains independent copies of the variables defined in the class.**

### Accessing Object Functions 

**To access a function inside of an object you use notation similar to accessing a variable** 

# Pytest Fixtures and Coverage 

## Fixtures 

**When you're writing tests, you're rarely going to write just one or two. Rather, you're going to write an entire "test suite", with each test aiming to check a different path through your code. In many cases, this means you'll have a few tests with similar characteristics, something that pytest handles with "parametrized tests".** 

**In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition.** 

### Coverage

**100% code coverage doesn't mean that your code is perfect or that it lacks bugs. But it does give you a greater degree of confidence in the code and the fact that it has been run at least once.** 
