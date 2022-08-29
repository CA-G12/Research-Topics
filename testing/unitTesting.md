# Unit testing

Unit testing in the world of development.

## What is unit testing?

Unit testing is a software development process in which the ***smallest testable parts*** of an application, called ***units***, are individually and independently scrutinized for proper operation. This testing methodology is done ***during the development process*** by the software developers and sometimes QA staff.

## Why is unit testing important?

The main purpose of  unit testing is to isolate written code to test and determine if it works as intended.
If done correctly, it can help detect early flaws in code which may be more difficult to find in later testing stages.

## How unit testing works?

Unit testing is compromised of three stages:

- Planning for the tests.
- Edge cases we need to test.
- And actual tests scripting/coding.
Each test case is tested independently in an isolated environment, as to ensure a lack of dependencies in the code.

## Types of unit testing

- Manual testing.
- Automated testing.

Unit tests can be performed manually or automated. Those employing a manual method may have a document made detailing each step in the process; however, automated testing is the more common method to unit tests. Automated approaches commonly use a testing framework to develop test cases. These frameworks are also set to flag and report any failed test cases while also providing a summary of test cases.

## Advantages of unit testing

- Reducing errors in earlier stages.
- Costs of fixing a problem early can quickly outweigh the cost of fixing it later.
- Debugging processes are made easier.
- Developers can quickly make changes to the code base.
- Developers can also re-use code, migrating it to new projects.

## Disadvantages of unit testing

- Tests will not uncover every bug.
- Unit tests only test sets of data and its functionality, it will not catch errors in integration.
- More lines of test code may need to be written to test one line of code—creating a potential time investment.

## Best practices

- Don't test every line of code, your tests should focus on the functions that could affect the behavior of the application.
- Use pure function to ensure that you tests don't fails duo to other parts of the code.
- Test characteristics that vital to the performance of unit that under testing.

## Popular Unit Testing Frameworks for JavaScript

- Jest.
- Mocha.
- Storybook.
- Jasmine.
- Cypress.
- Puppeteer.
- Testing Library.
- WebdriverIO.
