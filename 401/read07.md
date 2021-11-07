# Game of Greed 2

## Python Scope

### Understanding Scope

***In programming, the scope of a name defines the area of a program in which you can unambiguously access that name, such as variables, functions, objects, and so on. A name will only be visible to and accessible by the code in its scope. Several programming languages take advantage of scope for avoiding name collisions and unpredictable behaviors.***

> Most commonly, you’ll distinguish two general scopes:
* Global scope:

*The names that you define in this scope are available to all your code.*

* Local scope:

*The names that you define in this scope are only available or visible to the code within the scope.*

### Names and Scopes in Python
***Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value. On the other hand, functions and classes are available after you define them using def or class, respectively. Finally, modules exist after you import them.***

| Operation | Statement |
|-----------|-----------|
| Assignments | x = value |
| Import operations | import module or from module import name |
| Function definitions | def my_func(): ... |
| Argument definitions in the context of functions | def my_func(arg1, arg2,... argN): ... |
| Class definitions | class MyClass: ... |

**if you assign a value to a name inside a function, then that name will have a local Python scope.**

**if you assign a value to a name outside of all functions—say, at the top level of a module—then that name will have a global Python scope.**

### Python Scope vs Namespace

***In Python, the concept of scope is closely related to the concept of the namespace. As you’ve learned so far, a Python scope determines where in your program a name is visible. Python scopes are implemented as dictionaries that map names to objects. These dictionaries are commonly called namespaces. These are the concrete mechanisms that Python uses to store names. They’re stored in a special attribute called .__dict__.***

### Using the LEGB Rule for Python Scope

**Python resolves names using the so-called LEGB rule, which is named after the Python scope for names. The letters in LEGB stand for :**

* Local (or function) scope

*is the code block or body of any Python function or lambda expression. This Python scope contains the names that you define inside the function. These names will only be visible from the code of the function.*

* Enclosing (or nonlocal) scope

*is a special scope that only exists for nested functions. If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function. This scope contains the names that you define in the enclosing function.*

* Global (or module) scope

*is the top-most scope in a Python program, script, or module. This Python scope contains all of the names that you define at the top level of a program or a module.*

* Built-in scope

*is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python.*

### Modifying the Behavior of a Python Scope

**Python provides two keywords that allow you to modify the content of global and nonlocal names. These two keywords are:**

1. global
2. nonlocal

> The global Statement
**you can define a list of names that are going to be treated as global names.**

**The statement consists of the global keyword followed by one or more names separated by commas. You can also use multiple global statements with a name. All the names that you list in a global statement will be mapped to the global or module scope in which you define them.**

> The nonlocal Statement
**Similarly to global names, nonlocal names can be accessed from inner functions, but not assigned or updated. If you want to modify them, then you need to use a nonlocal statement. With a nonlocal statement, you can define a list of names that are going to be treated as nonlocal.**

**The nonlocal statement consists of the nonlocal keyword followed by one or more names separated by commas. These names will refer to the same names in the enclosing Python scope.**

### Discovering Unusual Python Scopes

**You’ll find some Python structures where name resolution seems not to fit into the LEGB rule for Python scopes. These structures include:**

* Comprehensions

*A comprehension is a compact way to process all or part of the elements in a collection or sequence. You can use comprehensions to create lists, dictionaries, and sets.*

* Exception blocks

*The exception variable is a variable that holds a reference to the exception raised by a try statement.*

* Classes and instances

*Unlike functions, the class local scope isn’t created at call time, but at execution time. Each class object has its own .__dict__ attribute that holds the class scope or namespace where all the class attributes live.*
