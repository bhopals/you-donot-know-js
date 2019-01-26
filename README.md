

## You Don't Know JS


### Index

[Scopes and Closures](#scope-and-closures) 

[Up and Going](#up-and-going)

[This and Object Prototypes](#this-and-object-prototypes) 

[Types and Grammar](#types-and-grammar) 

[ES6 and Beyond](#es6-and-beyond) 

[Async and Preformance](#async-and-performance)




### Scopes and Closures 

#### Introduction of Scope

Compilation involved:
    -   Tokenizing/lexing - Breaking up a code snippet into meaningfull chunks called TOKENS.
    -   Parsing - Taking a stream of TOKENS and turning into a tree, called AST (Abstract Syntax Tree), 
        of nested elements
    -   Code-Generation - Taking AST tree and turning into an executable code.


**Variable Lookups** 
    -   LHS - Who's the target of the assingments. (var a = b)
    -   RHS - Who's the source of the assigmnents. (console.log(a))

**ReferenceError** is scope resolution-failure (The variable not found).
**TypeError** implies that scope resolution was successful, but there was an illegal/impossible action attempted 
against the result, for example, trying to execute-as-function a nonfunction value, reference a property on a null or undefined value.


##### Lexical Scope
There are two predominant models for how scope works:
    -   Lexical Scope - (JavaScript )
    -   Dynamic Scope - (Bash Scripting, Perl)

** The first traditional phase of a standard language compiler is called "Lexing" (Tokenizing)                         
So the Lexical Scope is the scope that is defined at Lexing time. 
Lexical Scope is a scope model used by the JavaScript Language.
The lexing phase of compilation determines where and how all identifiers are declared, and thus how they will be looked up during execution.

Lexical scope means that scope is defined by author-time decisions of where functions and variables are declared.
OR
Lexical scope is a scope that is defined at Lexing time. (Lexing/tokenization Phase).
Author-time defined lexical scoping.

Both **eval(..)** and **with** cheat the otherwise author-time defined lexical scope by modifying or creating new lexical scope at runtime.

The Lexical phase of compilation is essentially able to know where and how all identifiers are declared, and thus predict how they will be looked up during execution.


#### Functions Versus Block Scope


### Up and Going



### This and Object Prototypes 



### Types and Grammar] 



### ES6 and Beyond]



### Async and Presormance


