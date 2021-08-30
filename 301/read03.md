# Lists and Keys

### Given the code below, we use the map() function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it:

(```const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);```)

# Rendering Multiple Components

### You can build collections of elements and include them in JSX using curly braces {}.

# Keys

### Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.



# Spread Operator in JavaScript

### The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.


# what it can do ?

1. Copying an array
2. Using Math functions
3. Combining objects
4. Adding an item to a list

![](https://miro.medium.com/max/2000/1*24ayqOY008AvW_VmkqsYdA.png)

# exapmles for using spread operators in different things : 

## 1- Compine two arrays (```const objectOne = {hello: "🤪"}
(```const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂```)

## 2- Adding an item to a list

(```const fewFruit = ['🍏','🍊','🍌']
const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]```)

## 3- Combining objects into one

(```const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂```)


***
# Passing function between components:

1. creates a bunch of person objects
2. creates a function that loops through the array of objects that is defined in the state.

# What does the increment do ?

### then number increases each time the user click on the item

# How does the child component invoke a method that was passed to it from a parent component?

### By Passing the key to the methodName.

![](https://lh4.googleusercontent.com/sBaxDLU9jP8BOaB8vNld8Yu_dv7V3HZGBNBHiguET93-VXWxm1tO3J6PtAWEg46cBAicYGZtZEMwRdYO3NYJUKBrEIT18-KvRUAMIHzQ_Q1sagcKZa3hyKVR4hJaf4VpTV3hoAoa)
.


