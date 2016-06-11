

**A checklist for your next project.**

Source: https://www.sitepoint.com/write-maintainable-javascript/

1. Analyse the project
  - Put your developer hat away for a moment, and be a user to see what it’s all about.
  - Go through the codebase and make a list of the tools in use.
  - Read up documentation and best practices of the tools.
  - Go through the unit tests to get a feeling for the project on a higher level.

2. Create a baseline
  - Introduce .editorconfig to keep the coding style guides consistent between different IDEs.
  - Make indentation consistent; tabs or spaces, doesn’t matter.
  - Enforce a naming convention.
  - If not already present, add a linter like ESLint, JSLint, or JSHint.
  - Update dependencies, but do it wisely and watch out for what exactly has been updated.

3. Cleaning up
  - Establish unit tests and browser automation with tools like Karma, Jasmine, or Nightwatch.js.
  - Make sure the architecture and design pattern are consistent.
  - Don’t mix design patterns, stick to the ones already there.
  - Decide if you want to split up your codebase into modules. Each should only have one purpose and be unaware of the rest of your codebase logic.
  - If you don’t want to do that, focus more on testable code and break it down into simpler blocks.
  - Document your functions and code in a balanced way with properly named functions.
  - Use JSDoc to generate documentation for your JavaScript.
  - Commit regularly and after important changes. If something breaks, it’s easier to go back.

4. Don’t lose your mind
  - Don’t get mad at the previous developer; negativity will only result in unnecessary refactoring and wasting time.
  - There have been reasons why code is written like it is. Keep in mind that we’ve all been there.


- [Untangling Spaghetti Code: How to Write Maintainable JavaScript](https://www.sitepoint.com/write-maintainable-javascript/) | [寻找头绪：编写可维护的 JavaScript](http://www.zcfy.cc/article/312)
