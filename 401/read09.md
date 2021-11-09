# Game of Greed 4

## Dunder Methods

### What Are Dunder Methods ?

***In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores***

*for example :*

      __init__ or __str__.

***Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string').***

### Special Methods and the Python Data Model

***This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.***

### Enriching a Simple Account Class

* Initialization of new objects : 

**__ init __**

*Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the __init__ dunder:* 

     class Account:
     """A simple account class"""

     def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []

* Object representation : 



>__ repr __ : The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr __ is to be unambiguous.
>__ str __: The “informal” or nicely printable string representation of an object. This is for the enduser.
*Example :* 

     class Account:
     # ... (see above)

     def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

     def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)

* Enable iteration : 

>__ len __  , __ getitem __
**Dunder methods to the rescue! It only takes a little bit of code to make the class iterable:** 

     class Account:
    # ... (see above)

    def __len__(self):
        return len(self._transactions)

    def __getitem__(self, position):
        return self._transactions[position]

>__ reversed __
**To iterate over transactions in reversed order you can implement the __reversed__ special method:** 

     def __reversed__(self):
    return self[::-1]

    >>> list(reversed(acc))
    [30, -20, 50, -10, 20]
* Operator overloading : 

>__ eq __ , __ lt __
**. To not have to implement all of the comparison dunder methods, I use the functools.total_ordering decorator which allows me to take a shortcut, only implementing __eq__ and __lt__:** 

     from functools import total_ordering

    @total_ordering
    class Account:
    # ... (see above)

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance

* Operator overloading : 

>__ add __ 
**Let’s implement __add__ to be able to merge two accounts. The expected behavior would be to merge all attributes together: the owner name, as well as starting amounts and transactions. To do this we can benefit from the iteration support we implemented earlier:** 

     def __add__(self, other):
    owner = '{}&{}'.format(self.owner, other.owner)
    start_amount = self.amount + other.amount
    acc = Account(owner, start_amount)
    for t in list(self) + list(other):
        acc.add_transaction(t)
    return acc

* Method invocation : 

>__ call __ 
**You can make an object callable like a regular function by adding the __call__ dunder method. For our account class we could print a nice report of all the transactions that make up its balance:** 

      class Account:
    # ... (see above)

    def __call__(self):
        print('Start amount: {}'.format(self.amount))
        print('Transactions: ')
        for transaction in self:
            print(transaction)
        print('\nBalance: {}'.format(self.balance))

* Context manager support : 

>__ enter __ , __ exit __ 
**A context manager is a simple “protocol” (or interface) that your object needs to follow so it can be used with the with statement. Basically all you need to do is add __enter__ and __exit__ methods to an object if you want it to function as a context manager.** 

     class Account:
    # ... (see above)

    def __enter__(self):
        print('ENTER WITH: Making backup of transactions for rollback')
        self._copy_transactions = list(self._transactions)
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('EXIT WITH:', end=' ')
        if exc_type:
            self._transactions = self._copy_transactions
            print('Rolling back to previous transactions')
            print('Transaction resulted in {} ({})'.format(
                exc_type.__name__, exc_val))
        else:
            print('Transaction OK')

## Statistics - Probability

### What is probability ?

***At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur.***

### The data and the distribution 

***The most important qualities to notice about the normal distribution is its symmetry and its shape. We’ve been calling it a distribution, but what exactly is being distributed? It depends on the context. In probability, the normal distribution is a particular distribution of the probability across all of the events. The x-axis takes on the values of events we want to know the probability of. The y-axis is the probability associated with each event.*** 

### Revisiting the normal 

* Central Limit Theorem :

***the closer the average of these trials approach the true probability, even if the individual trials themselves are imperfect. This idea is a key tenet of the Central Limit Theorem., a single trial  produces a single estimate of what probability suggests should happen We call it an estimate because we know that it won’t be perfect***

* Three Sigma Rule :

***The Three Sigma rule, also known as the empirical rule or 68-95-99.7 rule, is an expression of how many of our observations fall within a certain distance of the mean. Remember that the standard deviation (a.k.a. “sigma”) is the average distance an observation in the data set is from the mean. The Three Sigma rule dictates that given a normal distribution, 68% of your observations will fall between one standard deviation of the mean. 95% will fall within two, and 99.7% will fall within three. A lot of complicated math goes into the derivation of these values, and as such, is out of the scope of this article. The key takeaway is to know that the Three Sigma Rule enables us to know how much data is contained under different intervals of a normal distribution.***


* Z-score :

***The Z-score is a simple calculation that answers the question, “Given a data point, how many standard deviations is it away from the mean?” The equation below is the Z-score equation.***

