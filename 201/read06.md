>> # Problem Domain, Objects, and the DOM

#### Many of the problem domains we face as programmers are difficult to understand and look completely different depending on your viewpoint. As programmers, we also are often not given complete information about the problem domain, so we don't even have the information we need to understand it.

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190916094546/5-Most-Difficult-Programming-Languages-of-the-World.png)

## On the other hand Programming is easy if you understand the problem domain so what can you do about it ?

* first : Make the problem domain easier.
* second :Get better at understanding the problem domain.

 #### In shorten words You can often make the problem domain easier by cutting out cases and narrowing your focus to a particular part of the problem.

# What is the Object in Java script ?

#### JavaScript is designed on a simple object-based paradigm. An object is a collection of properties, and a property is an association between a name (or key) and a value.

![](https://i.pinimg.com/originals/17/e4/8c/17e48c25c9d6dcd0751fe0616fca1575.jpg)

## How can we creat one ?

### In JavaScript, there are four methods to use to create an object:

1. Object Literals.
2. New operator or constructor.
3. Object create method.
4. Class.

***

>> # Document Object model 

#### A Document object represents the HTML document that is displayed in that window. The Document object has various properties that refer to other objects which allow access to and modification of document content. The way a document content is accessed and modified is called the Document Object Model, or DOM.

![](https://static.javatpoint.com/images/javascript/dom.jpg)

## Working with domain steps : 

1. ACCESS THE ELEMENTS.
2. WORK W ITH THOSE ELEMENTS.

## LOOPING THROUGH A NODELIST

### If you want to apply the same code to numerous elements, looping through a Nodelist is a powerful technique.



## TRAVERSING THE DOM, how we do it ?

1. Traversing downwards. element.querySelector. element.querySelectorAll. element.children.
2. Traversing upwards. element.parentElement. element.closest.
3. Traversing sideways. element.nextElementSibling. element.previousElementSibling. Combine parentElement , children , and index.

![](https://www.qualitestgroup.com/images/howto/DOMTree_HowTo.png)

## From an element node, you can access and update its content using properties such as textContent and innerHTML or using DOM manipulation techniques. 

## Browsers offer tools for viewing the DOM tree, how ?

#### How can I see Dom in browser? To do so, open the web page elk. html, turn on the browser developer tools and switch to the Elements tab. It should look like this: You can see the DOM, click on elements, see their details and so on.

![](https://unicorn-utterances.com/dd29a33ce8c80881495040df32d5472a/dom_tree.svg)
