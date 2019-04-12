# Testing-school

- [What is testing?](#what-is-testing)
- [What/When should I test?](#what/when-should-i-test)
- Testing fundamentals
- Testing balance

### What is testing?

According to Wikipedia:

  > Is an investigation conducted to provide stakeholders with information about the quality of the software product or service under test. 

I believe:

  > The tests are a means that help us to improve the quality of an application, not an end in itself. Writing tests that do not give any value, does not make any sense. So the fundamental thing is that a test gives me confidence that the production code works.

Kent Beck (father of TDD) says:

> I get paid for code that works, not for tests.

### What/When should I test?

Three thing to keep in mind:

- [Validates something useful](#validates) 
- [Understandable](#understanble)
- [Run frequently](#frequently)

> For each [desired change](#explain-desired-change), make the change easy (warning: this may be hard), then make the easy change

Let's break kent Beck suggestion in two steps:

  1. *make the change easy*

  > Refactor the code to make it look like you knew this new feature was coming from the start.

  2. *then make the easy change*

  > Next, add code to support the new use case.

I really like this approach. You’re always refactoring [code to keep it fresh.](#legacy-dead)

So how this fit with the testing world:

  1. Writing tests for the existing block of code

  2. Then, I refactor it to make the new change easier to introduce. The tests help make these changes faster without breaking any existing features.

  3. When that’s done, I make the easy change of adding the new feature and tests to support it.

*Make the change easy, then make the easy change.*

There are 2 things I’d like you to point out in this workflow:

  1. The best time to write tests for a feature is just before you change it.

  2. Tests are not just for catching bugs.

With the above approach, tests can help you create a to-do list of use cases that can be checked one by one. This workflow helps me get the benefit of tests even when I’m not able to invest a lot of time up front.




##### Legacy dead

  > And you don’t have to ask for time or permission to pay tech debt because you’re constantly reducing it while you add new features. The code never becomes “legacy”. On the surface, it might look like this will slow you down because you’re doing more work. In my experience, it’s almost always faster than making the hard change because you don’t spend any time trying to understand complex code or fixing regression bugs.

##### Explain Desired Change

  > When you write a block of code, you write it with the best understanding and the latest information you have at that time. Months/weeks later you have to extend your code and support another user case. So somehow you fit the logic on top of the existing code and isn't always the prettiest result. Your code become complex *because it wasn't originally written with this new feature in mind*. That's where legacy code starts.



##### Understandable

 > If the test is complicated to understand, it is difficult to know if it really tests what I want, and also in case of failure I do not know if the production code or the test code is wrong (and no, TDD does not save you from this).

##### Validates 

  > If the test is going to be limited to validating that the getters and setters work, probably my overall confidence in the production code does not increase much. I am interested in testing the most complicated parts of my application, those that are most logical, those that are more prone to failures, those that are most important for my application.


##### Frecuently

  > It is not worth having a suite of 8000 tests, if you never execute it. You have to find a way to execute them with certain periodicity (ideally in each commit).
