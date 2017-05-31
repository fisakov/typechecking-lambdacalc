### Conclusion

In this article we have given a short summary of constraints-based approach to type checking that is the foundation of an upcoming major feature of MPS. We have shown how this approach can be applied to solving a classic type inference problem in simply typed lambda calculus. This solution can be easily extended to support type annotations, and further to introduce subtyping and ADTs. The author is currently working on re-implementing type checking for Base Language and its extensions, while keeping compatibility with Java and providing full support for solving type relations.

The method of solving constraints generated from the source code is not only relevant to type checking. One can imagine running all kinds of model validation using this technique, which is why we are planning to make the framework of building constraint rules as generic and as flexible as possible to allow for future reuse. 
