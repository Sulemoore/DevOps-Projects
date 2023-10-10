# Continuous Integration (CI) on AWS.

### Scenario

You have a product development and Agile SDLC with developers regularly making multiple code changes every day. And all these codes need to be regularly built and tested because this is what actually is building our product.

In a typical enterprise there will be a separate build and release team who bears this responsibility of building, testing and releasing the code.

### Problem

Because of the regular commits and/or pull requests, their will be dependency of teams on one another to complete their jobs.

- Developers will be dependent on build and release team, usually to test the code and move it to the next level in the release cycle.
- The code will be tested for any bugs or error which may be discovered late after a tone have accumulated.
- Developers would need to work extra to fix these bugs and errors, which is a time consuming process and teams would be already approaching the deadline.

### Solution
- Regular build and test for every commit. Instead of waiting to complete the code before discovering bugs, regular commits are made during the code writing to discover and fix bugs if any.
- Automated build and release process instead of manual process.
- Developer should get notified automatically if their is any code error or test failure.
- 
