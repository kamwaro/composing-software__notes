# Composing Software

## An exploration of functional Programming and Object Composition in Javascript

### By Eric Elliot

# Contents

1. Intro
2. The way of the functional Programmer
3. Composable software
4. Why learn functional programming in Javascript
5. Pure functions
6. What is functional programming
7. A functional Programmer's INtroduction to javacsript
8. Higher Order Functions
9. Curry and Function composition
10. Abstraction and composition
11. Functors and categories
12. Monads
13. The forgotten history of OOP
14. Object Composition
15. Factory functions
16. Functional mixins
17. Why composition is harder with classes
18. Composable Custom Data types
19. Lenses
20. Transducers
21. Elements of Javascrpt style
22. MOcking is a code smell

# Intro

- Composition: The act of combining parts or elements to form a whole.
- Software development: Its the act of breaking a complex problem down into smaller problems, and composing simple solutions to form a complete solution to the complex problem.

- The most important questions in software development are: 1. What is function composition? 2. What is object composition?

- You can't avoid composition just because you are not aware of it. You still do it - but you do it badly. You write code with more bugs, and make it harder for other developers to understand.
- We spend more time maintaining software than we do creating it from scratch.
- If you are a software developer, you compose functions and data structures every day, whether you know it or not.
- You can do it consciously ( and better), or you can do it accidentally.
- The process of software development is breaking down large problems into smaller problems, building components that solve those smaller problems, then composing those components together to form a complete application.

### Composing functions

- Function composition is the process of applying a function to the output of another function.
- In algebra, given two functions, f and g, (f0g)(x) = f(g(x)).
- The circle is the composition operator.
- Its commonly pronounced "composed with" or "after".
- You can say, "f composed with g equals f of g of x", or "f after g equals f of g of x".
- We say f after g because g is evaluated first, then its output is passed as an argument to f.

#### EXample of code, composing functions

    const g = n => n+1
    const f = n => n*2


    const  doStuff = x => {
        const afterG = g(x);
        const afterF = f(afterG);
        return afterF;
    }

    doStuff(20); // 42

#### EXample of promise chain, while composing functions

    const g = n => n + 1;
    const f = n => n * 2;

    const wait = time => new Promise((resolve, reject) => setTimeout(resolve, time));


    wait(5000).then(() => 20).then(g).then(f).then(value => console.log(value)) // 42

- Likewise, every time you chain array method calls you're composing functions.
- If you're chaining, you're composing.
- If you're passin return values into other functions, you're composing.
- When you compose functions intentionally, you'll do it better.

# 2. The way of the Functional Programmer.

- Functional programming is a foundational pillar of Javascript.
- Immutability is a foundational pillar of functional programming.
- You cant fully understand programming without first understanding immutability.

// Aside note: Frameworks ease the work of creation by removing hard choices.

- Keep functions small. Do one thing at a time, and do it well.
  -Plan for composition.
- Write functions whose outputs will naturally work as inputs to many other functions.
- Type-specific functions can't be reused for data of a different type.
- Wise programmers lift functions to work on many data types, or wrap data to make it look like what the function is expecting.
- Lists and items make great universal abstractions.
- A program can be reasoned about and outcomes predicted only when data flows freely through pure functions.

# Composable Software:
