## Lab 2, April 17th, 2018, Cara Ottmar

When this code is run in Node, e.g. node index.js, what are the two stages of execution for this file called, and which order do they happen in?
- The two stages of execution are called:
1. Compilation
2. Execution

Write an explanation, using as much space as you need, relating to how the first stage of execution for this file operates.
- I guess technically the first stage of execution is finding the 'use strict' then the following will happen: 
- The first stage of execution will see the compiler hoisting the "left hand side." For example, var in the global scope will be hoisted - the code execution will find bar(), then var foo = 'baz', function baz(), and then foo = 'bam'. 

Write an explanation, using as much space as you need, relating to how the second stage of execution for this file operates.
- The second stage of execution is RHS - right hand side. 

During the second stage of execution how many scopes have been registered by the engine?
- Three. Global, baz and bar. 
Which segments of the code do they belong to?
- Global scope is for var foo = 'bar' and the function bar(), baz is function baz(foo) from lines 8-10, and bar is 'foo' var and bar(). 

Please identify any variables/refs and which scope each belongs to?
- global = var foo = 'bar'
- baz = function baz(foo)
- bar = var foo and the function bar()

When line 13 invokes the baz function, which foo will be assigned a value of bam? More specifically, bam will be assigned to the foo in ??? scope. Give a brief description in your own words to support your conclusion.
- It will get assigned the value of bam. It is inside the function baz(foo) scope. I came to this conclusion based on the order of execution of the code. 

Which scope, if any, will the variable bam on line 11 be registered to when the first stage of execution occurs on this file? Provide a brief description in your own words to support your conclusion.

- I don't believe that bam will be registered on line 11 because it hasn't been defined in any scope.

For each line, 16 through 19, what is the return value for each?
- line 16 = undefined
- line 17 = 'bar'
- line 18 = 'yay'
- line 19 = reference error