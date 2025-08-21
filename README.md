****# JS-DAY-1-INTERVIEW-QUESTION
1. Difference between == and ===

== → Loose Equality
It only checks values, not types. It tries to convert (typecast) before comparing.
Example:

5 == "5"   // true  (because "5" gets converted to number)


=== → Strict Equality
It checks both value and type.
Example:

5 === "5"  // false (number !== string)


👉 Always prefer === to avoid confusion.

2. Difference between var, let, const

var

Function-scoped

Can be re-declared and updated

Hoisted (but undefined initially)

Old way (not much used now)

let

Block-scoped ({ } scope)

Can be updated, cannot be re-declared in same scope

Safer than var

const

Block-scoped

Cannot be updated or re-declared

Used for fixed values

Example:

var a = 10;  // can change, old style
let b = 20;  // can change but safer
const c = 30; // fixed, cannot change

3. What is Execution Context?

When JavaScript runs code, it creates an environment called Execution Context.
It has two main parts:

Memory (Variable Environment) → where variables & functions are stored.

Code (Thread of Execution) → where code runs line by line.

4. Creation Phase vs Execution Phase

Creation Phase

JS scans code before running.

Allocates memory for variables and functions.

Functions are stored fully, variables are set to undefined initially.

Execution Phase

Code runs line by line.

Variables get actual values.

Functions are executed when called.

5. What is Hoisting?

Hoisting means JavaScript moves declarations to the top of the scope before execution.
Example:

console.log(x); // undefined
var x = 10;


Because var x is hoisted, but value assignment happens later.

6. Difference between undefined vs not defined vs NaN

undefined → Variable declared but no value given.

let x;
console.log(x); // undefined


not defined → Variable not declared at all.

console.log(y); // ReferenceError: y is not defined


NaN → Not a Number (invalid math).

console.log("hello" / 2); // NaN

7. How many operators in JavaScript?

JavaScript has many operators, grouped as:

Arithmetic (+, -, *, /, %, **)

Assignment (=, +=, -=, etc.)

Comparison (==, ===, !=, >, <, >=, <=)

Logical (&&, ||, !)

Bitwise (&, |, ^, ~, <<, >>, >>>)

Ternary (condition ? true : false)

Type (typeof, instanceof, delete, void, in, new)

👉 Roughly 40+ operators in total.

8. Local Scope, Block Scope, Functional Scope, Scope Chain

Local Scope → Variable inside a function is local (only accessible inside).

Block Scope → Variables declared with let or const inside { } are only accessible there.

Function Scope → var works inside a function (not accessible outside).

Scope Chain → If JS doesn’t find a variable in current scope, it goes one level up (parent scope) until global scope.

Example:

let a = 10;
function outer() {
  let b = 20;
  function inner() {
    let c = 30;
    console.log(a, b, c); // Can access all (scope chain)
  }
  inner();
}
outer();****
