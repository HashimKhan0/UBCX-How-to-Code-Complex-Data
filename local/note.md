The Intermediate Student Langauge (ISL) provides local expressions which make it possible to have definitions visible only within the local expression

# Forming and Intuition
- to from a local expression:
    - > (local [ {definiton} ... ] {expression})
- it sets up the defintions, it sets up a special world that has these definitons and the expression/body uses these to produce a result

# Lexical Scoping
- lexical scoping allows us to answer questions about what definiton any reference name refers to 
- in a program there is a top level scope of the whole program
- if we define a local and a variable in our file, in our top level there are two definitons
- when we encounter a local we enter the inner scope where other definitons take place
- in practice we can go between the inner scope and the top level depending on if our variables are defined outside the local

# Evaluation Rules
- local is just an expression and does not affect the evaulation rules of the defintions around them
- for evaluating a local 3 things happen in one step
> 1. Rename definitions and references to a unique global name 
> 2. Lift renamed definitions out of the local into top-level scope
> 3. replace local with its renamed body(this removes the local similar to if expressions and results in a BSL program)


# Encapsulation
- encapsulation allows us to tackle the problem of using the same naming conventions but for completly different purposes

- Good Candidates for Encapsulation
> 1. one function has one or more helpers closely linked to it
> 2. the outside program really only wants toc all the main function, not the the helpers

- this refactoring is useful on mutually referential data and allows us to name helpers and functions inside our top level function to avoid confusion in large programs

- Encapsulation doesn't just work with mutually recursive functions. As a guideline, it is valuable whenever one function is useful at top-level, and it has one or more helpers that are not useful at top level.

# Avoiding Recomputation

- local expressions can be used to avoid recomputing results which in recursive programs can have signifcant effects on program performance as our data set grows
- find the nearest expression that encloses all the recomputed values and local around the expression 