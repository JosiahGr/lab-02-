![cf](https://i.imgur.com/7v5ASc8.png) 02: Tools and Context
======

## Feature Tasks
#### Scope and Context
Given the code linked [HERE](https://gist.github.com/sjschmidt44/556d31146a2b1ff3be84820e5fc06959), answer the set of questions below. Please copy the questions to your lab directory in a file called `answers.md`.


#### Questions:
1. When this code is run in Node, e.g. `node index.js`, what are the two stages of execution for this file called, and which order do they happen in?

A. Compiliation and Execution. In that order. 

2. Write an explanation, using as much space as you need, relating to how the first stage of execution for this file operates.
    - For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.
    
A. In the compilation phase, the computer searches through all of the code and finds all function declarations and variables. The computer then proceeds to remember them by hoisting them to the top where they await as reference for stage 2, execution. 

3. Write an explanation, using as much space as you need, relating to how the second stage of execution for this file operates.
    - For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.
   
A. Execution. This is where the computer actually runs through the code and assigns values to the function declarations and variables as they come. 

4. During the second stage of execution how many scopes have been registered by the engine?
    - Which segments of the code do they belong to?
    - Please identify any variables/refs and which scope each belongs to?
    
A. There are 3 scopes in this code. Global, bar(), then baz(). Global includes variable `foo`, and bar(). Bar() reassigns `bar` to `foo` when it is invoked and contains the function baz(). Finally, baz() has two variables inside it's own scope (though `bam` is never actually defined). 

5. When line 13 invokes the `baz` function, which `foo` will be assigned a value of `bam`? More specifically, `bam` will be assigned to the `foo` in ??? scope. Give a brief description in your own words to support your conclusion.

A. Foo is never redefined because the function declaration never passed an argument. Therefore, `foo` will remain assigned to `bam` in the `baz` function, but where the code currently stands, `foo` will have the value of `baz`. 

6. Which scope, if any, will the variable `bam` on line 11 be registered to when the first stage of execution occurs on this file? Provide a brief description in your own words to support your conclusion.

A. bam is not assigned to a variable. This means that it will never be hoisted during the execution phase and likely throw up a lintr error when you write out the code and ultimately a referenceError will occur during execution. 

7. For each line, 16 through 19, what is the return value for each?

16) baz
17) bar
18) ReferenceError
19) ReferenceError
