# Testing-school

- [What is testing?](#what-is-testing)
- [What/When should I test?](#what/when-should-i-test)
- [Testing fundamentals](#testing-fundamentals)
- Testing balance

## What is testing?

According to Wikipedia:

> Is an investigation conducted to provide stakeholders with information about the quality of the software product or service under test.

I believe:

> The tests are a means that help us to improve the quality of an application, not an end in itself. Writing tests that do not give any value, does not make any sense. So the fundamental thing is that a test gives me confidence that the production code works.

Kent Beck (father of TDD) says:

> I get paid for code that works, not for tests.

### What/When should I test?

Three thing to keep in mind:

- [Validates something useful](#validates)
- [Understandable](#understandable)
- [Run frequently](#frecuently)

> For each [desired change](#explain-desired-change), make the change easy (warning: this may be hard), then make the easy change

Let's break kent Beck suggestion in two steps:

1. _make the change easy_

> Refactor the code to make it look like you knew this new feature was coming from the start.

2. _then make the easy change_

> Next, add code to support the new use case.

I really like this approach. You’re always refactoring [code to keep it fresh.](#legacy-dead)

So how this fit with the testing world:

1. Writing tests for the existing block of code

2. Then, I refactor it to make the new change easier to introduce. The tests help make these changes faster without breaking any existing features.

3. When that’s done, I make the easy change of adding the new feature and tests to support it.

_Make the change easy, then make the easy change._

There are 2 things I’d like you to point out in this workflow:

1. The best time to write tests for a feature is just before you change it.

2. Tests are not just for catching bugs.

With the above approach, tests can help you create a to-do list of use cases that can be checked one by one. This workflow helps me get the benefit of tests even when I’m not able to invest a lot of time up front.

## Testing fundamentals

> It's all about CONFIDENCE

- [Principles](#principles)
- [Test types](#test-types)
- [What to test](#what-to-test)

### Some Principles

- Mocking too much reduces test quality
- More isolation means less bugs caught
- Testing UI is extremely hard
- Avoid test implimentation details

### Test types

- [Static](#static) 🚴
  > Typos and type errors.
- [Unit](#unit) 🚗
  > Test in isolation
- [Integration](#integration) 🚆
  > Individual units are combined and tested as a group
- [End-to-end](#end-to-end) ✈️
  > Highest-level test.Is an automated use case perpective, testing not just the code but things out side.

### Static

Also called dry run testing is a form of software testing where the actual program is not used because either typos or types errors.
The most common solution for this kind of test is by using automated tools like esLint/prettier and typescript to caught those bugs.

### Unit

Tests that are independent of one another - meaning, executing one should not have any effect on the result of another. (Kent Beck).

Some benefits we get from unit testing are:

- [Speed](#Speed)
- [Ease of writing](#ease-of-writing)
- [Error locality](#error-locality)
- [Stability](#stability)

### Integration

> Individual units are combined and tested as a group

### End to end

> Highest-level test. Is an automated use case perpective, testing not just the code but things out side.

##### Speed

> Because of the isolation from anything outside, unit tests execute purely in memory, which means they are fast.

##### Ease of writing

> As they are only concerned with their code, unit tests are the simplest ones to write.

##### Error locality

> When a unit test fails, it's usually quite simple to locate the cause of the failure.

##### Stability

> Because they execute in a deterministic, controlled environment, unit tests rarely give false positives, in general produce consistent and repeatable results, and are not flaky

##### Legacy dead

> And you don’t have to ask for time or permission to pay tech debt because you’re constantly reducing it while you add new features. The code never becomes “legacy”. On the surface, it might look like this will slow you down because you’re doing more work. In my experience, it’s almost always faster than making the hard change because you don’t spend any time trying to understand complex code or fixing regression bugs.

##### Explain Desired Change

> When you write a block of code, you write it with the best understanding and the latest information you have at that time. Months/weeks later you have to extend your code and support another user case. So somehow you fit the logic on top of the existing code and isn't always the prettiest result. Your code become complex _because it wasn't originally written with this new feature in mind_. That's where legacy code starts.

##### Understandable

> If the test is complicated to understand, it is difficult to know if it really tests what I want, and also in case of failure I do not know if the production code or the test code is wrong (and no, TDD does not save you from this).

##### Validates

> If the test is going to be limited to validating that getters and setters work, probably my overall confidence in the production code does not increase much. I am interested in testing the most complicated parts of my application, those that are most logical, those that are more prone to failures, those that are most important for my application.

##### Frecuently

> It is not worth having a suite of 8000 tests, if you never execute it. You have to find a way to execute them with certain periodicity (ideally in each commit).

TODO:

https://kentcdodds.com/blog/how-to-know-what-to-test

https://kentcdodds.com/blog/unit-vs-integration-vs-e2e-tests

https://vimeo.com/274376070
