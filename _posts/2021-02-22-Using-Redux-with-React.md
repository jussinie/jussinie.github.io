---
layout: post
author: Jussi
date: 2021-02-22 17:45
---

As you probably already now, I am now learning React. I came to the part in this course where I have to learn to use Redux to manage the state of the application. I thought that it might make sense to write down some notes as I go along - also to make it clearer for me what I am actually doing. 

### What is Redux used for? ###

Redux is used to manage the state for an application. Normally you would use states in this fashion: 

        const [myState, setMyState] = useState('');
        

In Redux you do things on a bit different fashion. 
You save the state of the app to a JavaScript object that gets saved to a _store_. 
Then you start modifying the state of your app with _actions_. 
Actions are objects that get at least one attribute, type. 

After you have defined the actions you create a _reducer_ which is a function that gets the state and the action as parameters and then returns the new state.
So the actions define what to do but reducer is the place that defines what are the steps to complete when this action is taken.
Store will use the reducer to handle actions that are _dispatched_ to the store.

        store.dispatch({type: 'INCREMENT'})

Remember that you never want to call the reducer from the code. You just give it as a parameter for the createStore function that creates the _store_.

        const store = createStore(counterReducer)
