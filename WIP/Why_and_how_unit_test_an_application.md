# Why and how unit test an application ?

## Purpose of this article

I know what you may think : an umpteenth article on unitary tests, in 2018. Don't we have enough already ?

Well, I think not. 

The fact is that a lot of developers are still struggling to understand and to write unit tests. Most of the time, they will waste a huge amount of time and pain to write a dirty mix between unit tests and integration tests without getting the advantages of any of them. This leads to unclear test suites which will need high maintenance and will be quite useless.

Furthermore, I found the existing articles/tutorials about unit testing frustrating :

- They explain in fact only what is automated testing, using too simple examples like "How to test a `square(x) function". These examples are of little value in the real world, especially with a complex web application.
- They are too theoretical and to not give concrete solutions to apply the paradigms they are explaining.
- Or, on the contrary, they brutally show how to test a particular framework without giving the keys to understand why it should be tested this way.

This article aim to be a guide to novice developers to **understand the theory** of unit testing and **how concretely they should implement it**.

## What unit testing is not

First, let's address some misconceptions :

- Unit testing is not a way to detect bugs.
- Unit testing is not a way to detect defects or regressions either.

Unit tests, by definition, examine each unit of your code separately. But when your application is run for real, all those units have to work together, and the whole is more complex and subtle than the sum of its independently-tested parts.

To detect bugs and regressions, you have to implement **integration testing** or **end to end tests**, which use other techniques, frameworks and paradigms. 

## What is unit testing

So, what is the point of unit testing ? There are many answers to that question, but here are those I find the most valuable :

### Improve code quality

Simply put, unit testing is **a way to improve code quality by forcing the developer to produce small and decoupled units of code.**

The fact is that dirty code with huge and complicated function will be way more painful to test. This pain is the punishment imposed to the developer for writing tightly-coupled code or code that requires complex initialization.

### Make refactoring easier

To be honest, I lied when I said unit testing was not a tool to detect regressions. It is in **only one particular case**: refactoring.

Unit Tests allows you to make big changes to code quickly. You know it works now because you've run the tests, when you make the changes you need to make, you need to get the tests working again. This saves hours.

## The notion of System Under Testing (SUT)

## How to isolate and only test your SUT

### Output tests

### Behaviour tests

### The case of private methods

## Conclusions

## References
