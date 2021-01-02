(slide1)
My presentation topic is asynchronous in JavaScript. Itself JavaScript single-threaded, which means that only one block of code can execute at a moment. But in JavaScript has the ability to execute code asynchronously. Let`s compare synchronous and asynchronous tasks

(slide 2)
What is a synchronous task?
(slide 2.1)
For example we have two lines of code following each other. Synchronous task mean that second line of code can`t execute until first one has finished executing. At the beggining of execution the call will go to the call stack and after completes it is thrown from the stack. 

Let's take an example
(slide 2.2)
We have three function. When we start execute function on line 14 we find call of second function and send her to call stack.
(slide 2.3)
You can see how first() goes to call stack.
When we execute function in local scope (on line 10) we find call of second function. Now second function send to call stack.
(slide 2.4)
In seconds function we find call of third function and send it to call stack.
(slide 2.5)
Since we are facing with return third, function ends and return send to call stack
(slide 2.6)
Return and call of third function pop from call stack.
(slide 2.7)
Execute second function, console.log send to call stack.after execution pop console.log and execute first function. call stack is clear.

(slide 3)
What is a asynchronous task?
(slide 3.1)
The essence of asynchrony is that we don`t know exactly when code execute.
Lets say we have two lines of code following each other. But now asynchronous lets us run first line in background so that second execute without waiting of complite first one. We use this for example when we upload data from server and lose connection or slow internet connection.

(slide 3.2)
Let's take an example with use of setTimeout, the simpliest way to show how work asynchronous. We have two console.logs and one timer with callback function that execute console.log.
When we start execute our code first console.log push to call stack
(slide 3.3)
code is output to the console and execution of console.log pop from call stack
then setTimeout execute and push to call stack
(slide 3.4)
Js engine doesn't support setTimeout/setInterval that why callback function in setTimeout scope goes to webApi
(slide 3.5)
at the same time execute third console.log, push to call stack and after execute pop from call stack
After two seconds of delay callback function goes to callback queue
(slide 3.6)
and after all synchronous tasks are completed push to call stack
(slide 3.7)
callback execute and call stack cleared.

There are several ways to work with asynchrony: callback function, promise and async/await.Lets talk about it
(slide 4)

For many years to solve the problem of asynchrony we use callback function.Callbacks are simply a function that you call when you receive a return result.Let`s see an example.
(slide 4.1)
We have function loadScript which load script and than execute callback function which load script and so on.
But everything is fine as long as there are no more than three callbacks.
(slide 4.2)
As calls become more nested, the code becomes deeper and increasingly more difficult to manage, especially if we have real code instead of callback scope that may include more loops, conditional statements and so on.
That�s sometimes called �callback hell� or �pyramid of doom.� Code grow bottom and right.
If we want to fix this we need to use promise
(slide 4.3)
We see practicaly identical function but it look like very compact.

Okay lets speak about promise
(slide 5)
So, in a nutshell about promis: "You are child and mother tell you that she maybe buy you a new phone or if she is not in the mood, she will not buy"
Lets see an example
(slide 5.1)
We have variable with mom mood(false mean bad) and variable willIGetNewPhone which is assigned a new promise which has two states (resolve and reject)

resolve mean that mother in a good mood and child get new phone and reject mean that mother in a bad mood and child stay without new mobile. 

And the way that appeared in es7 it is async/await
(slide 6)


we have function LoadJson that with async become asynchronys and code looks like synchronous. We get url from server with fetch and get json data or throw error.

(slide 6.1)
Async/await this is syntactic sugar for better undestanding asynchronus in js
Key word async before the function declaration:
   - Makes it always return a promise.
   - Allows await to be used in it.
The await keyword before a promise makes JavaScript wait until that promise settles, and then:
   - If it�s an error, the exception is generated � same as if throw error were called at that very place.
   - Otherwise, it returns the result.
And example using async/await
(slide 7)
Thanks for watching





 


