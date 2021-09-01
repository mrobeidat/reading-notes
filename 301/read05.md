# Thinking in React

## How would you break a mock into a component hierarchy?

#### The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names. If you’re working with a designer, they may have already done this, so go talk to them! Their Photoshop layer names may end up being the names of your React components!

## What is the single responsibility principle and how does it apply to components:

#### The single-responsibility principle (SRP) is a computer-programming principle that states that every module, class or function in a computer program should have responsibility over a single part of that program's functionality, and it should encapsulate that part.

![](https://miro.medium.com/max/3410/1*Dee4cg5Hzg7JME1A9tjZJQ.png)

## What does it mean to build a ‘static’ version of your application?

#### The easiest way is to build a version that takes your data model and renders the UI but has no interactivity. To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props.

## Once you have a static application, what do you need to add?

#### you need to be able to trigger changes to your underlying data model.

1. if you want to control the behavior of the component 
2. some information that may change over the lifetime of the component 
3. change something inside Component

## How can you identify where state needs to live?

#### If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component. 
