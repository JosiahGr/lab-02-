#### Questions:
1. When this code is run in Node, e.g. `node index.js`, what are the two stages of execution for this file called, and which order do they happen in?

##### A. Compiliation and Execution. In that order. 

2. Write an explanation, using as much space as you need, relating to how the first stage of execution for this file operates.
    - For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.
    
##### A. In the compilation phase, the computer searches through all of the code and finds all function declarations and variables. In this case it first sees the variable foo and a function bar. It hoists them to the top of the program and saves them until called upon for execution. Further more, it looks into baz for the next steps. 

3. Write an explanation, using as much space as you need, relating to how the second stage of execution for this file operates.
    - For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.
   
##### A. Execution. This is where the computer actually executes the code. The computer assigns values to the variables as it runs through the code, then it executes the functions that were found. In this example, it starts with assigning `foo` a value of `bar`, then executes the function bar(), and then looks "inside" it and executes it's containing code. It will then assign baz to the new variable `foo`. Afterwards it runs baz() and reassigns foo and assigns 'yay' to bam. This in turn will return a function (baz) and it is not (to everyones great dismay) recognized in the global scope.

4. During the second stage of execution how many scopes have been registered by the engine?
    - Which segments of the code do they belong to?
    - Please identify any variables/refs and which scope each belongs to?
    
##### A. There are 3 scopes in this code. Global, bar(), then baz(). Global includes variable `foo`, and bar(). Bar() reassigns `bar` to `foo` when it is invoked and contains the function baz(). Finally, baz() has two variables inside it's own scope (though `bam` is never actually defined). 

5. When line 13 invokes the `baz` function, which `foo` will be assigned a value of `bam`? More specifically, `bam` will be assigned to the `foo` in ??? scope. Give a brief description in your own words to support your conclusion.

##### A. Foo is never redefined because the function declaration never passed an argument. Therefore, `foo` will remain assigned to `bam` in the `baz` function, but where the code currently stands, `foo` will have the value of `baz`. 

6. Which scope, if any, will the variable `bam` on line 11 be registered to when the first stage of execution occurs on this file? Provide a brief description in your own words to support your conclusion.

##### A. bam is not assigned to a variable. This means that it will never be hoisted during the execution phase and likely throw up a lintr error when you write out the code and ultimately a referenceError will occur during execution. 

7. For each line, 16 through 19, what is the return value for each?

##### 16) ReferenceError
##### 17) bar
##### 18) ReferenceError
##### 19) ReferenceError
