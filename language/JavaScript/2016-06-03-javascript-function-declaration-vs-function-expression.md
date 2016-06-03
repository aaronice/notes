# Function Declarations vs. Function Expressions

Original Article by Angus Croll: https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/

### A Short Quiz
Lets start with a short quiz. What is alerted in each case?:

Question 1:

```javascript
function foo(){
    function bar() {
        return 3;
    }
    return bar();
    function bar() {
        return 8;
    }
}
alert(foo());
```

Question 2:

```javascript
function foo(){
    var bar = function() {
        return 3;
    };
    return bar();
    var bar = function() {
        return 8;
    };
}
alert(foo());
```

Question 3:

```javascript
alert(foo());
function foo(){
    var bar = function() {
        return 3;
    };
    return bar();
    var bar = function() {
        return 8;
    };
}
```

Question 4:

```javascript
function foo(){
    return bar();
    var bar = function() {
        return 3;
    };
    var bar = function() {
        return 8;
    };
}
alert(foo());
```

If you didn’t answer 8, 3, 3 and `[Type Error: bar is not a function]` respectively, read on… (actually read on anyway😉 )

### What is a Function Declaration?

A Function Declaration defines a named function variable without requiring variable assignment. Function Declarations occur as standalone constructs and cannot be nested within non-function blocks. It’s helpful to think of them as siblings of Variable Declarations. Just as Variable Declarations must start with “var”, Function Declarations must begin with “function”.

e.g.
```javascript
function bar() {
    return 3;
}
```

ECMA 5 (13.0) defines the syntax as

```javascript
function Identifier ( FormalParameterListopt ) { FunctionBody }
```
The function name is visible within it’s scope and the scope of it’s parent (which is good because otherwise it would be unreachable)

```javascript
function bar() {
    return 3;
}

bar() //3
bar  //function
```

### What is a Function Expression?

A Function Expression defines a function as a part of a larger expression syntax (typically a variable assignment ). Functions defined via Functions Expressions can be named or anonymous. Function Expressions must not start with “function” (hence the parentheses around the self invoking example below)

e.g.

```javascript
//anonymous function expression
var a = function() {
    return 3;
}

//named function expression
var a = function bar() {
    return 3;
}

//self invoking function expression
(function sayHello() {
    alert("hello!");
})();

```

ECMA 5 (13.0) defines the syntax as
```javascript
function Identifieropt ( FormalParameterListopt ) { FunctionBody }
```
(though this feels incomplete since it omits the requirement that the containing syntax be an expression and not start with “function”)

The function name (if any) is not visible outside of it’s scope (contrast with Function Declarations).

## Reference
- [Function Declarations vs. Function Expressions](https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/)
