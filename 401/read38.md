# Conditional Rendering
is a term to describe the ability to render different user interface (UI) markup if a condition is true or false. In React, it allows us to render different elements or components based on a condition. This concept is applied often in the following scenarios: Rendering external data from an API

## Forms
```html
<form>
  <label>
    Name:
    <input type="text" name="name" />
  </label>
  <input type="submit" value="Submit" />
</form>
```
This form has the default HTML form behavior of browsing to a new page when the user submits the form. If you want this behavior in React, it just works. But in most cases, it’s convenient to have a JavaScript function that handles the submission of the form and has access to the data that the user entered into the form. The standard way to achieve this is with a technique called “controlled components”.

## Lists and Keys

**Lists** : we use it to Rendering Multiple Components


**Keys** :Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity

## lifting state up
lifting state from one level to the next, without necessarily making the state global. That's how I thought state management worked, since it is similar to variable, function and block scope

## Composition vs Inheritance

**Composition** :  one of the fundamental concepts in object-oriented programming. It describes a class that references one or more objects of other classes in instance variables. This allows you to model a has-a association between objects. You can find such relationships quite regularly in the real world


**Inheritance** : the procedure in which one class inherits the attributes and methods of another class.
