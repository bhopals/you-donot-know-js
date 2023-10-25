## You Don't Know JS

Below are the only summary/notes from the very popular JavaScript Book series **You Don't Know JS - KYLE SIMPSON**.

### Index

[Scopes and Closures](#scope-and-closures)

[Up and Going](#up-and-going)

[This and Object Prototypes](#this-and-object-prototypes)

[Types and Grammar](#types-and-grammar)

[ES6 and Beyond](#es6-and-beyond)

[Async and Preformance](#async-and-performance)

### Up and Going

## Chapter 1 - Into Programming

- STATEMENT

  - In a computer programming, a group of words, numbers, and operators that
    performs a specific task is a STATEMENT.
  - Example: `a = b * 2`
    - `a`, `b` are Variables
    - `*,`=` are Operators
    - `2` is a Literal value

- EXPRESSION
- STATEMENTS are made of one or more expressions. An expression is any reference to a variable or a value,
  OR a set if variable(s), and value(s) combined with Operators.
- Example: `a = b * 2`

  - This statement has FOUR expressions:
    - `2` is a LITERAL VALUE EXPRESSION
    - `b` is a VARIABLE EXPRESSION, which means to retrieve its current value
    - `b * 2` is an ARITHMETIC EXPRESSION, which means to od a multiplication
    - `a = b * 2` is an ASSIGNMENT EXPRESSION, which means to assign the result of the `b * 2`
      expression to the variable `a`

- A General expression that stands alone is also called an EXPRESSION STATEMENT

  - Example: `b * 2`
    - This would not have any effect as it would not do anything.

- A More common expression statement is a CALL EXPRESSION STATEMENT - Function Call

  - Example: `alert(a)`

- Implicit Coersion (Double equal does the implicit Coersion for you)
- Explicit Coersion

- VARIABLES

  - A Symbolic Container that stores the value of a variable.
  - You declare a variable to hold a specific type of value, we use
    `TYPE ENFORCEMENT` or `STATIC TYPING` of strict assignment of typed variable
  - OR define `DYNAMIC TYPING` or `WEAK TYPING`

- SCOPE
  - Technically called LEXICAL SCOPE
  - In Javascript each function get its own scope.
  - Scope is basically a collection of variables as well as rules for how those variables
    are accessed by name.
  - Only code inside that function can access that function's SCOPED Variables.
  - Lexical Scope means Definition SCOPE (Where the item got created)
  - REMEMBER - It will be Definition Space (where it is defined) not
    Invocation Space (Where the var is invoked)
  - Lexical ==> Lexicon ==> "Lexis" ==> "Word"
  - Lexican Means Dictionary
  - Lexical Scope - Region in which a WORD exists is determined by where it was DEFINED and CREATED.
    - A scope is an environment/region in which something (a variable) exists
    - A scope can access its parents.
    - A parent scope does not have direct access to variables declared in an inner scope.
    - Lexical has do do with where a variable was declared/created.
    - Lexical scope enforces finding variables from the scope/block they were created/declared and not the environment which they are running in.
    - Dynamic Scope is the opposite of Lexical Scope.
    - Dynamic scoping checks the variables from where they are running.

KEYWORDS

- STATEMENT ==> Multiple Expressions
- EXPRESSION
- LITERAL VALUE EXPRESSION
- VARIABLE EXPRESSION
- ASSIGNMENT EXPRESSION
- CORESION - IMPLCIT and EXPLICIT
- DYNAMIC TYPING or WEAK TYPING
- TYPE ENFORCEMENT or STATIC TYPING
- SCOPE (LEXICAL SCOPE/STATIC SCOPE)

## Chapter 2 - Into Javascript

- VALUES & TYPES

  - Followings are built-in types:

    - string
    - number
    - boolean
    - null or undefined
    - object

      - normal JS object (Key-Val pair)
      - array and functions are specific types of Objects
      - Both are OBJECT SubTypes

    - symbol (new to ES6)

- `typeof` Operator

  - Javascript provides a typeof operator that examine a value and tell you what type it is.
  - It returns type value in "string"
  - Example:
    - var a; typeof a; // "undefined"
    - a = "hello world"; // "string"
    - a = 42; typeof a; // "number"
    - a = true; typeof a; // "boolean"
    - a = null; typeof a; // "object" --weird BUG!!
    - a = undefined; typeof a; // "undefined"
    - a = {b: "c"}; typeof a; // "object"
    - a = [1, 2]; type of a; // "object"
    - function a() {return 42;}; typeof a; // "function"

- OBJECT

  - Properties of an object can be accessed with DOT NOTATION or BRACKET NOTATION

- COERSION

  - Explicit Coersion

    - var a = "42"; var b = Number(a);

  - Implicit Coersion
    - var a = "42"; var b = a + 1;

- Coresion in `==` v/s "==="

  - `==`
    - if same type just MATCH
    - if different type perform COERSION and then MATCH
  - `===`

    - Just match - No COERSION at all

  - `==` and `===` works on comparing two primitive values.
  - For object (non-primitive) it will always be falsy as it is compared by REFERENCE

- Coersion in comparison (<, > operators)

  - If both values in the comparison (<, >) are STRINGs ("42" > "43"),
    the comparison is made lexicographically.
  - But if one or both not a STRING (42 "43"), then both values will be coerced to NUMBER
  - "foo" > 42 ===> Nan > 42 ==> false

- NaN == NaN // false

  - Why shouldn’t NaN be equal to itself? Because that would lead to bad comparisons.
    NaN is coalescing, meaning that any mathematical operation done with NaN results in NaN.
    If two complex calculations were done and then their results compared, you would expect them
    to be equal if and only if they yielded the same number. Suppose there was an error in the
    calculations or in the input value and they each resulted in NaN. They should not be considered equal
    here because not all failures are equal.

    Note that there are two isNaN() methods in JavaScript: the global one and the one in the Number
    object. There’s a subtle but significant difference in them. The global isNaN() method coerces its
    argument into a number first, meaning that undefined, {}, 'NaN', and many other inputs return true.
    (This means isNaN(undefined) === true, even though undefined is clearly not NaN.)

    Number.isNaN(), however, does not coerce its argument. It will return true if and only if its argument
    is actually NaN. This is probably the method you want to use. It is a newer addition to ECMAScript
    (the JavaScript specification) and it is supported in every browser except Internet Explorer.
    Fortunately, writing your own polyfill is easy since NaN is the only value not equal to itself:

  Example:
  isNaN(undefined) // true - does coerce its argument
  Number.isNaN(undefined) // false - does not coerce its argument

- ARRAY
- ARRAY are default COERSED to STRING by simply joining all the values with COMMA
- Example:
  - var a = [1,2,3]; var b = [1,2,3]; var c = "1,2,3";
  - a == c // true - `a` coerced to string ("1,2,3")
  - b == c // true - `b` coerced to string ("1,2,3")
  - a == b // false - Same type so no COERSION

TRUTHY & FALSY

- "Falsy" List

  - "" (Empty String)
  - 0, -0, NaN(Invalid Number)
  - null, undefined
  - false

- "Truthy" List (Few of the examples)

  - "hello"
  - 42
  - true
  - [], [1, "2", 3] (arrays)
  - {}, {a: 42} (objects)
  - function foo() {...} (functions)

- VARIABLES

  - A Valid Identifiers
  - Starts with a-z, A-Z, $, or \_
  - Can contain number as well (not in the start)

- FUNCTION SCOPES

  - Whenever a Var appears inside a scope, that declaration is taken to belong to the entire SCOPE
    and accessible everywhere throughput.
  - Metaphorically, this behaviour is called HOISTING, when a VAR declaration is conceptually "moved"
    to the top of its enclosing scope.
  - When you declare a variable, it is available anywhere in that scope as well as any LOWER/INNER Scope.
  - If you try to access a variable value in a SCOPE where it is not available, you will get a REFERENCE ERROR thrown.

- BLOCK SCOPING

  - Use of LET keyword
  - Block Scoping is very useful for managing your variable scopes in a more fine-grained manner

- NAMED Function Expression - var a = function test() {...};
- ANONYMOUS Function Expression - var a = function() {...};
- IIFE (Immediately Invoked Function Expression) - (function(){...})()

- CLOSURE

  - You can think of CLOSURE as a way to "REMEMBER" and continue to access a function's scope
    (it's variable) even once the function has finished running.

- MODULES

  - The most common usage of Closure in JAVASCRIPT is the module pattern.
  - Modules let you define private implementation details that are hidden from the outside world,
    as well as Public API that is accessible from the outside.

- PROTOTYPES

  - When you reference a Property on an Object, if that Property doesn't exist, JavaScript will
    automatically use that object's internal PROTOTYPE Reference to find another object to look
    for the Property is missing.

- POLYFILL

  - Take the existing definition and produce a new code with some improvements and safe guarding
    is called POLYFILL

- TRANSPILING

  - Convert the new code into older equivalent code so Older JS Engines can execute it.

- KEYWORDS
  - a = null; typeof a; // "object" --weird BUG!!
  - LET - manage variable scope in more fine-grained fashion

### Scopes and Closures

#### Introduction of Scope

Compilation involved: - Tokenizing/lexing - Breaking up a code snippet into meaningfull chunks called TOKENS. - Parsing - Taking a stream of TOKENS and turning into a tree, called AST (Abstract Syntax Tree),
of nested elements - Code-Generation - Taking AST tree and turning into an executable code.

**Variable Lookups** - LHS - Who's the target of the assingments. (var a = b) - RHS - Who's the source of the assigmnents. (console.log(a))

**ReferenceError** is scope resolution-failure (The variable not found).
**TypeError** implies that scope resolution was successful, but there was an illegal/impossible action attempted
against the result, for example, trying to execute-as-function a nonfunction value, reference a property on a null or undefined value.

##### Lexical Scope

There are two predominant models for how scope works: - Lexical Scope - (JavaScript ) - Dynamic Scope - (Bash Scripting, Perl)

\*\* The first traditional phase of a standard language compiler is called "Lexing" (Tokenizing)  
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

\*Declaration made with let will not hoist to the entire scope of the block they appear in.

To achieve Block Scoping, you can simply wrap your code chunk into { // your code goes here} and thats it.

**let** and **const** are block scoped.

#### Hoisting

- Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope
- Hoisting is result of Javascript Interpreter Implmentation.

- The variable and function declarations are "moved" from where they appear in the flow of the
  code to the top of the code.This gives rise to the name **hoisting**.

- \*\*Javascript Only Hoists DECLARATIONS, not the INITIALIZATIONS.
- Example:
  `console.log(a); var a=2;` ==> `var a; console.log(a); a=2;`

- Only the declarations themselves are hoisted, while any assignments or other executable logic are left in place
- Hosting is per-scope.
- Functions are hoisted first then variables (If both are of the same NAME)
- Hoisting is done at **Compiler-phase task**, however the atual code execution is done at **execution-phase task**

- Function Declaration are hoised; however, function expressions are not.
- Examples:

  - Function declarations
    foo(); // Prints 'TEST'
    function foo() {console.log('TEST')}

  - Function expression
    foo(); // `TypeError` (As var foo; is hoisted)
    var foo = function bar() {console.log('TEST1')}

  **ReferenceError** - Variable not found
  **TypeError** - illegal operations

- Benefits of HOISTING
  - Allow you to use function declarations before they are defined.
  - This allows you to organize where you put your function code regardless of where they
    are called as long as they are within the same SCOPE. It IMPROVES the Performance of the Interpreter.

#### Scope Closure

- Closures happen as a result of writing code that relies on lexical scope.

**Definition** - Closure is when a function is able to remember and access its lexical scope even that function is execution outside its lexical scope. (That reference is called closure).

Whatever facility we use to transport an inner function outside of its lexical scope, it will maintain a **scope reference** to where it was originally declared, and wherever we execute him, that closure will be exercised.

- Example:
  function foo() {
  var a = 2;
  function bar() {
  console.log(a);
  }
  return bar;
  }
  var baz = foo();
  baz(); // 2

  The function `bar` has lexical scope access to the inner scope of `foo`, which keeps that scope
  alive for `bar` to reference at any later time.
  The function is invoked well outside of its author-time lexical scope.
  Closure lets the function continue to access lexical scope it was defined in at author time.

- Author time lexical scop
- Lexical Scope
- Inner Scope
- Observable Closure in IIFE(immediately invoked function expression)

- Essentially, whenever and wherever you treat functions (that access their own lexical scopes) as
  first-class values and pass they around, you are likely to see these function exercising closure.
  Examples: Timers, event handlers, ajax requests, cross window messaging, web workers, and any of
  the asynchronous (or synchronous) taks, when you pass in a callback function, get ready to
  sling some closure around.

**Revealing Module** pattern is the best example of closure .

**TODO**

- Benefits of hosting??
- Why compiler does lexing??
- In depth compiler working??
- How hoisting actually works??
- Why Closure??

### This and Object Prototypes

### Types and Grammar

### ES6 and Beyond

### Async and Presormance
