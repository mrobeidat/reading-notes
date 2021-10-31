# In Tests We Trust - TDD with Python

### Unit tests and TDD ?  

**Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code.** 

**Test-Driven Development is a strategy to think and write** 

### Important aspects about the unit test 

**Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.** 

* Arrange: you need to organize the data needed to execute that piece of code 
    
* Act: here you will execute the code being tested 
    
* Assert: after executing the code, you will check if the result  is the same as you were expecting. 

# If name equals main 

> What does the if __name__ == “__main__”: do ? 

***Before executing code, Python interpreter reads source file and define few special variables/global variables. 
If the python interpreter is running that module (the source file) as the main program, it sets the special __name__ variable to have a value “__main__”. If this file is being imported from another module, __name__ will be set to the module’s name. Module’s name is available as value to __name__ global variable.*** 

> What is Module ? 

***A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended.*** 

> Advantages :  

* Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions. 

* If you import this script as a module in another script, the __name__ is set to the name of the script/module.

* Python files can act as either reusable modules, or as standalone programs.

* if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported. 

![](https://www.thinktocode.com/wp-content/uploads/2018/02/red-green-refactor.png)

# Recursion 

> What is Recursion ?

**The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily.** 

> How a particular problem is solved using recursion ?

**The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion.** 

> What are the disadvantages of recursive programming over iterative programming ?

1. Note that both recursive and iterative programs have the same problem-solving powers. 
1. every recursive program can be written iteratively and vice versa is also true. 
1. The recursive program has greater space requirements than iterative program as all functions will remain in the stack until the base case is reached. 
1. It also has greater time requirements because of function calls and returns overhead. 

> What are the advantages of recursive programming over iterative programming ?

1. Recursion provides a clean and simple way to write code. 
1. Some problems are inherently recursive like tree traversals, Tower of Hanoi. For such problems, it is preferred to write recursive code.

![](https://cdn.educba.com/academy/wp-content/uploads/2019/11/Recursive-Function-in-Python.png)
