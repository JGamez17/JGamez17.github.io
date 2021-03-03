---
layout: post
title:      "Understanding the inner workings of REDUX"
date:       2021-03-03 07:03:35 +0000
permalink:  understanding_the_inner_workings_of_redux
---


"Repeated patterns become facts, and when you're in touch with the facts you can predict the future"
Aniekee Tochukwu Ezekiel 

### What is REDUX?

Redux is a tool for JavaScript apps that maintains the entire state of an application. Redux makes web development more efficient because it makes the state available whenever needed.  The state usually refers to the single value or data that is managed by the store and consist of an object (key/value pairs). Redux can be used with a variety of frameworks but in this post we will be talking about it being used with the React front end framework.  At first glance utilizing redux sounds complex but luckily it follows a pattern that consists of the core concepts known as store, action creators, reducers, and a connect function. 

To start utilizing redux you first need install the library, if you haven’t done so already. The packages can be installed via NPM. To do so in your terminal you type...

```ruby
npm install redux 
```

Now that this has been installed its time to start learning how to utilize it in your apps. Below these core concepts will be defined and explained. 

## Redux Model

To change something in state you need to dispatch an action.  An action is a plain JavaScript object.  

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2082702b-4722-4300-80da-92c5f6a5d341/Screen_Shot_2021-03-02_at_3.13.34_PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2082702b-4722-4300-80da-92c5f6a5d341/Screen_Shot_2021-03-02_at_3.13.34_PM.png)

[https://www.educative.io/blog/understanding-redux](https://www.educative.io/blog/understanding-redux)

In redux the entire state object is in one centralized location called the store. The store is not a class and has the responsibility of storing, reading and updating the state. Action creators are simple functions that help create the changes or actions needed. Then these objects that are returned are sent to various reducers in the application.  The reducers take the action, make a copy of the existing state, apply all updates to the state and finally publish the updated state changes to the store. 

 In conclusion, redux has 3 main parts, actions, reducers, and store. These 3 main components follow a pattern called immutability. This in short means that we don't change the state object and its properties directly. Instead, we create a new object and with the spread operator make a copy of state, make a new object, recalcualte the new app sate and update it with our newly created object.
