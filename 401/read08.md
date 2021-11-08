
 
## List Comprehensions 

***List comprehensions provide a concise way to create lists. It consists of brackets containing an expression followed by a for clause, then zero or more for or if clauses. The expressions can be anything, meaning you can put in all kinds of objects in lists. The result will be a new list resulting from evaluating the expression in the context of the for and if clauses which follow it. The list comprehension always returns a result list.*** 

*Example :-*

     new_list = []
      for i in old_list:
       if filter(i):
        new_list.append(expressions(i)) 

> Syntax 

**The list comprehension starts with a ‘[‘ and ‘]’, square brackets, to help you remember that the result is going to be a list.** 

**The basic syntax uses square brackets.** 

* new_list

*The new list (result).*

* expression(i)

*Expression is based on the variable used for each element in the old list.*

* for i in old_list

*The word for followed by the variable name to use, followed by the word in the old list.*

* if filter(i)

*Apply a filter with an If-statement.* 

* new_range = [i * i for i in range(5) if i % 2 == 0]

*Which corresponds to:*

*result* = [*transform* *iteration* *filter* ]

*The * operator is used to repeat. The filter part answers the question if the item should be transformed.*

> Examples :  

* Create a simple list 

      x = [i for i in range(10)]
      print x

      # This will give the output:
      [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] 

* Create a list using loops and list comprehension

      # You can either use loops:
      squares = []

      for x in range(10):
      squares.append(x**2)
 
      print squares
      [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

      # Or you can use list comprehensions to get the same result:
      squares = [x**2 for x in range(10)]

      print squares
      [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

* Multiplying parts of a list 

      list1 = [3,4,5]
 
       multiplied = [item*3 for item in list1] 
 
      print multiplied 
       [9,12,15] 
