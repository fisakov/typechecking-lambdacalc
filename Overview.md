### Overview

This article serves as a brief account of using the new approach to type checking that is currently being developed. The contents should be accessible to anyone familiar with MPS and type checking in general. If you are interested in what’s going on in the area of type checking, and you would like to have better understanding of the new approach we are taking to address the problem, this article is for you. Also, we are interested in what you think, so please send your feedback. 

We explain how the redesigned type checking infrastructure for MPS works. We introduce term as the data structure to represent types, we discuss unification and what role it plays in type inference, what are logical variables and how they can be used as type variables, and finally how programming with constraints is applicable to type checking. 

In this article we will show how to build type system for simply typed lambda calculus in MPS. Type checking and type inference is a very complex topic, so we select a rather naive example to demonstrate how a fundamental type inference algorithm can be implemented using our new set of languages designed from scratch to address this problem.

The key idea we discuss here is the use of Constraint Logic Programming, or constraint rules, to drive the type inference logic. We use generative approach, with type checking templates defining the typing rules that get transformed into constraint rules, which are finally evaluated to produce the resulting set of constraints containing inferred types and errors detected in the process. 

