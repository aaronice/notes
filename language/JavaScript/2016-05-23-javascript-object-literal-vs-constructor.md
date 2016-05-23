

# JavaScript: Literals vs. Constructors

## Comparison

### Simpleness

[stackoverflow](http://stackoverflow.com/questions/4859800/should-i-be-using-object-literals-or-constructor-functions)

> Apply the KISS principle. If you don't need anything beyond a simple container of data, go with a simple literal.

> If you want to add behavior to your object, you can go with a constructor and add methods to the object during construction or give your class a prototype.
> Although, it's also normal to put functions inside object literals, see #Encapsulation

### Singleton vs Multiple Instances

[stackoverflow](http://stackoverflow.com/questions/4859800/should-i-be-using-object-literals-or-constructor-functions)

> It essentially boils down to if you need multiple instances of your object or not; object defined with a constructor lets you have multiple instances of that object. Object literals are basically singletons with variables/methods that are all public.

### Encapsulation

[stackoverflow](http://stackoverflow.com/questions/4859800/should-i-be-using-object-literals-or-constructor-functions)

> If you include the function definitions as part of the object literal, or use the `this.fn = function ...` approach in a constructor, each of your object instances will have their own copies of functions. Using the prototype approach, you attach each function once and only once: they'll be inherited by the instances through prototypal inheritance.

> I believe you missed an important thing. only constructor function can provide private members as well as public members (encapsulation). in the object literal - they are all public.

### Performance

[performance](http://www.dhchoi.com/javascript-literals-vs-constructors-performance/)


> It turns out that the constructor notation is much more slower when considering performance issues. If the object is not designed to have any instances of it later on, using the literal notation will crunch the speed of your code better.


## Reference

- [MDN: Introduction to Object-Oriented JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript)

- [StackOverflow: Should I be using object literals or constructor functions?](http://stackoverflow.com/questions/4859800/should-i-be-using-object-literals-or-constructor-functions)

- [JavaScript: Literals vs. Constructors Performance](http://www.dhchoi.com/javascript-literals-vs-constructors-performance/)
