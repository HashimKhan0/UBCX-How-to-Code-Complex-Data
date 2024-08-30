- abstraction is a technique for taking highly repetitive code and refactoring out the identical parts to leabe behind a shared helper and just the different parts of the original code
- the shared helper is called an abstract function because it is more general than the original code
- it is a crucial technique for managing complexity in programs. 
    - it can make programs samller if the abstract functions are used by many other functions in the system
    - it also helps seperate knowledge domains more clearly in code

- the simplest way to desing abstract functions is to start with two or more examples of highly repetitive code
- we can create higher order functions which can consume one or more functions and can produce a function
    
