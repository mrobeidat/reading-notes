
# Game of Greed 1 

## How to use Random Module 

***The random module provides access to functions that support many operations. Perhaps the most important thing is that it allows you to generate random numbers.*** 

### When to use it ? 

**We can use it when we want the computer to pick a random number in a given range Pick a random element from a list, pick a random card from a deck, flip a coin etc. When making your password database more secure or powering a random page feature of your website.** 

### Random functions 

***The Random module contains some very useful functions.*** 

* Randint 

*If we wanted a random integer, we can use the randint function Randint accepts two parameters: a lowest and a highest number.* 

> Example : 
           import random
           print random.randint(0, 5)

*This will output either 1, 2, 3, 4 or 5.* 

* Choice 

*Generate a random value from the sequence sequence.
The choice function can often be used for choosing a random element from a list.* 

> Example :  
      import random
      myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
      random.choice(myList) 

* Shuffle 

*The shuffle function, shuffles the elements in list in place, so they are in a random order.* 

> Example :  
     from random import shuffle
     x = [[i] for i in range(10)]
     shuffle(x)

*Output:*
 
 *print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]*

*of course your results will vary*

* Randrange 

*Generate a randomly selected element from range* 

> Example :   
      import random
      for i in range(3):
    print random.randrange(0, 101, 5) 

## What is Risk Analysis 

***The probability of any unwanted incident is defined as Risk. In Software Testing, risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.*** 

### Why use Risk Analysis ?

**In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.** 

> you might think what could be the possible risks that you could encounter? Well here is a list:
1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application 

> you must know there are certain risks that are unavoidable : 


1. The time that you allocated for testing
2. A defect leakage due to the complexity or size of the application
3. Urgency from the clients to deliver the project
4. Incomplete requirements

### Risk Identification

*There are different sets of risks included in the risk identification process. Those are as follows:* 



* Business Risks: 

*This risk is the most common risk associated with our topic. It is the risk that may come from your company or your customer, not from your project.*

* Testing Risks: 

*You should be well acquainted with the platform you are working on, along with the software testing tools being used.*

* Premature Release Risk: 

*a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required*

* Software Risks: 

*You should be well versed with the risks associated with the software development process.* 

### Risk Assessment 

***In the risk analysis process, these steps prove to be the most important one. It is said that this step is way too complex and should be tackled with the utmost care. After risk identification, assessment has to be dealt programmatically. There are a few perspectives on risk assessment:*** 

![Risk Assessment](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2019/08/Picture1-768x422.png) 

> The perspective of Risk Assessment 
* Effect : 

*To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.*

* Cause : 

*To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.*

* Likelihood : 

*To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.*

### How to perform Risk Analysis?

1. Searching the risk
2. Analyzing the impact of each individual risk
3. Measures for the risk identified


## Big O Notation 

***Big O is essentially an equation that describs how the runtime scales with respect to some input variables*** 

> The most important 4 rules to know with the Big O : 
1. If you have 2 different steps in your algorithm, you add up those steps. 
2. you drop constants. 
3. If you have different inputs you are usually going to use different variables to represent them.  
4. you drop non-dominant terms.  

* Big O(1) its constant time with respect to the size of the input. 

* Big O(n) it scales linearly with respect to the amount of input.
