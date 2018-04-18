## Lab 2, April 17th, 2018, Cara Ottmar

When this code is run in Node, e.g. node index.js, what are the two stages of execution for this file called, and which order do they happen in?
- The two stages of execution are called:
1. Engine - responsibile for start to finish compilation and execution. 
2. Compiler- handles the parsing and code-generation

Write an explanation, using as much space as you need, relating to how the first stage of execution for this file operates.
- The first stage of execution will see the compiler breaking down the code into tokens. Tokenizing is breaking up a string of characters into a more meaningful chunk for it to look at. I believe this starts at line 3 (var foo = 'bar') which is a global variable for foo. 

Write an explanation, using as much space as you need, relating to how the second stage of execution for this file operates.
- At second stage of execution, the compiler will look at Scope to see if var foo already exists for that particular scope. If it has, it will be ignored and it will move on to the next. If it hasn't, the engine will begin looking elsewhere. In this case, because the compiler sees foo defined as bar, it goes to search for bar globally and finds it. In line 16, (bar()) it is an invoked function.
- The compiler then goes inside the function bar() to the next foo and finds it. However, the var foo inside of the function is definied as 'baz'.

During the second stage of execution how many scopes have been registered by the engine?
- Two. Global and function bar. var foo = 'bar'; and function bar() {
- var foo = 'baz';

When line 13 invokes the baz function, which foo will be assigned a value of bam? More specifically, bam will be assigned to the foo in ??? scope. Give a brief description in your own words to support your conclusion.
- Line 13's baz function will result in the function baz(foo) getting assigned the value of bam, so line 10. It is inside the function baz(foo) scope. I came to this conclusion based on the order of execution of the code. 

Which scope, if any, will the variable bam on line 11 be registered to when the first stage of execution occurs on this file? Provide a brief description in your own words to support your conclusion.

- I don't believe that bam will be registered on line 11 because it hasn't been defined in any scope.

For each line, 16 through 19, what is the return value for each?
- line 16 = 'baz'
- line 17 = 'bar'
- line 18 = 'yay'
- line 19 = foo = 'bam'