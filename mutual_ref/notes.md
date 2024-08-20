# Learning Goals
- identify problem domain information of arbitrary size that should be represented using arbitrary arity trees
- use the design recipes to design with arbitrary arity trees
- use the design recipes with mutually-referential data.
- predict and identify the correspondence between external-, self- and mutual-reference in a data definition and calls, recursion and mutual-recursion in functions that operate on the data.


# Module 1: Mutually Recursive Data

- another form of data is an arity tree
- it is similar to a directory that has files in files and such
- each element can have a sub element 
- here we end up having two self referential type comments compared to one 

> ;; Element is (make-elt String Integer ListOfElement)
;; interp. An element in the file system, with name, and EITHER data or subs.
;;         If data is 0, then subs is considered to be list of sub elements.
;;         If data is not 0, then subs is ignored.

> ;; ListOfElement is one of:
;;  - empty
;;  - (cons Element ListOfElement)
;; interp. A list of file system Elements

- here there is a self reference in 'ListOfElement ''
- and the mutual reference is in that in the reference to element in ListOfElement, we return to its own definition. Element is defined by ListOfElement
- thus we can make an arbitrarily sized arity tree(arbitrarily wide and arbitrarily deep)