# Overview

- this module will cover designing functions that consume two arguements of one-of type
- in order to do this we need to develop a new model of our code, the cross product of the types comment table
- this will provide us with a clear way to think of all possible test cases 


# Cross Product Table
- this deisgn approach is applicable to any function that consumes two one-of types of data(they do NOT need to be the same)
- the table will have each case for each arguement along the axis
- we can then construct tests that cover each possible occurence of a one-of
- now we could code a cond expression for each possible case but this becomes tedious as we get an n x m matrix of one-of's in practice
- looking at the results of our different possible variable types we can generalize them and remove the cases are redundant. 
- this is called simplifying at the model level