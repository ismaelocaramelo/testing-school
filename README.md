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

> For each desired change, make the change easy (warning: this may be hard), then make the easy change

<!-- TODO: Describe this ^  -->


##### Understandable

 > If the test is complicated to understand, it is difficult to know if it really tests what I want, and also in case of failure I do not know if the production code or the test code is wrong (and no, TDD does not save you from this).

##### Validates 

  > If the test is going to be limited to validating that the getters and setters work, probably my overall confidence in the production code does not increase much. I am interested in testing the most complicated parts of my application, those that are most logical, those that are more prone to failures, those that are most important for my application.


##### Frecuently

  > It is not worth having a suite of 8000 tests, if you never execute it. You have to find a way to execute them with certain periodicity (ideally in each commit).
