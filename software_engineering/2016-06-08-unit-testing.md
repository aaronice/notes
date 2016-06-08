# Unit Testing: How to Write Better Tests

*Source: [Eric Elliott: 5 Questions Every Unit Test Must Answer - How to Write Better Tests](https://medium.com/javascript-scene/what-every-unit-test-needs-f6cd34d9836d)*

## Why Test?

### The secret weapon to application success

1. **Design aid**: Writing tests first gives you a clearer perspective on the ideal API design.
2. **Feature documentation (for developers)**: Test descriptions enshrine in code every implemented feature requirement.
3. **Test your developer understanding**: Does the developer understand the problem enough to articulate in code all critical component requirements?
4. **Quality Assurance**: Manual QA is error prone. In my experience, it’s impossible for a developer to remember all features that need testing after making a change to refactor, add new features, or remove features.
5. **Continuous Delivery Aid**: Automated QA affords the opportunity to automatically prevent broken builds from being deployed to production.

### The Science of TDD

The evidence says:

- **TDD can reduce bug density**.
- **TDD can encourage more modular designs** (enhancing software agility/team velocity).
- **TDD can reduce code complexity**.

Says science: There is significant empirical evidence that TDD works*.

## Write Tests First

> **Before you implement, write the test.**

## What's Good Unit Test

### How unit tests are used

- Design aid: written during design phase, prior to implementation.
- Feature documentation & test of developer understanding: The test should provide a clear description of the feature being tested.
- QA/Continuous Delivery: The tests should halt the delivery pipeline on failure and produce a good bug report when they fail.

## Unit Test as a Bug Report

> A failing test should read like a high-quality bug report.

**What’s in a good test failure bug report?**

- What were you testing?
- What should it do?
- What was the output (actual behavior)?
- What was the expected output (expected behavior)?

> **Equal** is your new default assertion. It is the staple of every good test suite.

## Five Questions to Ask for Unit Test

- What are you testing?
- What should it do?
- What is the actual output?
- What is the expected output?
- How can the test be reproduced?

## Reference

- [Eric Elliott: 5 Questions Every Unit Test Must Answer - How to Write Better Tests](https://medium.com/javascript-scene/what-every-unit-test-needs-f6cd34d9836d) | [【译】每个单元测试必须回答的 5 个问题](http://www.zcfy.cc/article/423)
