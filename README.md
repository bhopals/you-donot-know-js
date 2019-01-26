

## You Don't Know JS 

Below are the only summary/notes from the very popular JavaScript Book series **You Don't Know JS - KYLE SIMPSON**. 

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

Lexical scope means that scope is defined by author-time decisions of where functions and variables (formally called identifiers) are declared.
OR
Lexical scope is a scope that is defined at Lexing time. (Lexing/tokenization Phase).
Author-time defined lexical scoping.

Both **eval(..)** and **with** cheat the otherwise author-time defined lexical scope by modifying or creating new lexical scope at runtime.

The Lexical phase of compilation is essentially able to know where and how all identifiers are declared, and thus predict how they will be looked up during execution.


#### Functions Versus Block Scope
JavaScript has Function-Based Scope

Lexical scope look-up rules to identify what value would be of any variable.(In case of multiple variables with same
name in NESTED scopes).

Hiding variables and functions in function-scope or **scope-based hiding**. There is a Software Design principle - **Principle of Least Privilege** also sometimes called **Least Authority** or **Least Exposure**. This principle states that in the design of software, such as the API for a module/object, you should expose only what is minimally necessary, and "Hide" everything else.

Function Declarations
Function Expressions - Anonymous function expressions/named function expressions/Invoking functions expressions immediately

JavaScript **with** and **try/catch** are block-scoped.

*Declaration made with let will not hoist to the entire scope of the block they appear in.

To achieve Block Scoping, you can simply wrap your code chunk into { // your code goes here} and thats it.

**let** and **const** are block scoped.


#### Hoisting
The variable and function declarations are "moved" from where they appear in the flow of the code to the top of the code. 
This gives rise to the name **hoisting**.

 - Only the declarations themselves are hoisted, while any assignments or other executable logic are left in place
 - Hosting is per-scope.
 - Functions are hoisted first then variables
 - Hoisting is done at **Compiler-phase task**, however the atual code execution is done at **execution-phase task**


 **ReferenceError** - Variable not found
 **TypeError** - illegal operations


#### Scope Closure
 - Closures happen as a result of writing code that relies on lexical scope.

 **Definition** - Closure is when a function is able to remember and access its lexical scope even that function is execution 
                  outside its lexical scope. (That reference is called closure).

Whatever facility we use to transport an inner function outside of its lexical scope, it will maintain a **scope reference** to where it was originally declared, and wherever we execute him, that closure will be exercised.

**Revealing Module** pattern is the best example of closure     .


**TODO**
 - Benefits of hosting??
 - Why compiler does lexing??
 - In depth compiler working??
 - How hoisting actually works??
 - Why Closure??




### Up and Going



### This and Object Prototypes 



### Types and Grammar] 



### ES6 and Beyond]



### Async and Presormance


