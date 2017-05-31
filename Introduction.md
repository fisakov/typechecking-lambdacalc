### Introduction

In order to manipulate with types as objects we need to introduce an appropriate data structure. The «SNode»  used in the AST representation is just too heavyweight to be suitable for computation, so we created a data structure that is equivalent to a term as it is usually defined in theoretic discussions on types. This data structure is immutable, any change results in creating a new instance of a term. The key feature of the term data structure is that it is a perfect fit for unification. With unification we find the values for type variables, and thus we infer the type. 

**TODO: sample terms, types**

```
f (g (X))
```

Unification assumes a term may contain variables that can be substituted with other terms. So, we introduce logical variables, and allow terms to have logical variables as child terms. These are the same logical variables that are used as parameters to constraints, which enables us to create constraints on types that have not yet been instantiated, meaning logical variables can be used to represent type variables. 

```
Forall() { type: T; }
```

The language of typing rules, that is discussed later, makes it easy to declare and use the logical variables. They are declared  at the start of a rule block, just like type variables declared at the start of a Java method. 

The key we discuss here is the use of constraint rules to implement type checking and type inference. The typing rules, which constitute the essence of the algorithm, are recorded in form of templates that are applied to the source AST nodes. It is worth emphasising that, in contrast to the classic approach to building a type system with MPS, the typing rules are not executed immediately on being triggered, but rather produce instances of constraint rules. These rules are collected into handlers, according to the way they are organised in the type checking aspect, so the order of constraint rules activation is predictable. The handlers constitute a constraint rules program, which is then executed, and the results are produced in form of constraints representing inferred types and detected errors.

Constraints serve to express facts about types, which can be used to check type correctness or implement type inference. The way it works looks very much like the theoretic typing rules work: the rule head defines the antecedent, and the rule body is the consequence. Once we «know» all the inputs to the rule, we can make a conclusion. The structure of the constraint rule allows us to freely manipulate the facts: we can keep the ones that we are interested in and throw away those that are no longer needed. In effect, constraint rules constitute a simple but powerful apparatus for logic programming. 

```
gen(G, E) 
typeof(`let`) is G
```
