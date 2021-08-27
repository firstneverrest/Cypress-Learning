# Cypress Learning

The test runner which is modern testing with cross-browser compatibility. Easy to use and friendly to user with wonderful GUI. [visit official website here](https://www.cypress.io/).

## Installation

```
npm install cypress --save-dev
or
yarn add cypress --dev
```

## Run Cypress

First, let Cypress set everything up for us with:

```
npx cypress open
```

Cypress GUI window will pop up with three sections

1. Tests - all the tests that you write will be there. Cypress provides test examples to show how Cypress do automate test.
2. Runs - display your record results of test. Login to dashboard is required.
3. Settings - every configuration and other environment are showed in this section.

### Run Cypress with headless mode

```
npx cypress run --headless
```

## Folder Structure

1. fixtures - dummy data
2. integration - test files used to create test case, test suite and so on
3. plugins - extends functionality of cypress
4. support - create reusable code such as command

## Writing Test

1. Create test file in cypress/integration e.g., hello-word.spec.js
2. define `/// <reference types="cypress" />` at the top of the file because cypress has created type by TypeScript to make us and editor know the type of argument.

```javascript
/// <reference types="cypress" />

// test suite
describe('hello world', () => {
  // test case
  it('test one', () => {
    cy.visit('http://localhost:3000');
  });
});
```

Then, you can open Cypress and start automate testing.

Cypress is built on top of Mocha and Chai which support both Chai's BDD and TDD assertion styles. Tests you write in Cypress will mostly adhere to this style.

### Test Structure

The test interface, borrowed from Mocha, provides describe(), context(), it() and specify(). context() is identical to describe() and specify() is identical to it(), so choose whatever terminology works best for you.

### Hooks

Cypress also provides hooks (borrowed from Mocha). These are helpful to set conditions that you want to run before a set of tests or before each test. They're also helpful to clean up conditions after a set of tests or after each test.

```javascript
before(() => {
  // root-level hook
  // runs once before all tests
});

beforeEach(() => {
  // root-level hook
  // runs before every test block
});

afterEach(() => {
  // runs after each test block
});

after(() => {
  // runs once all tests are done
});

describe('Hooks', () => {
  before(() => {
    // runs once before all tests in the block
  });

  beforeEach(() => {
    // runs before each test in the block
  });

  afterEach(() => {
    // runs after each test in the block
  });

  after(() => {
    // runs once after all tests in the block
  });
});
```

## Command

- cy.visit(url: string) - visit the page at url
- cy.get(class: string) - find the html element <> with defined class
- type(text: string) - when use cy.get() to get element, you can type or insert string with .type() command.
- cy.contains(text: string) - find element that contain defined text.
- click() - element click
- cy.url() - get current url
- should('include', url: string) - when you grab url, use this command to check whether current page contain defined url or not.
  Tip: Contain use to find text, include use to find url
