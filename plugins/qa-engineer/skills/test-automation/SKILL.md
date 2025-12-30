---
name: test-automation
description: Master test automation with Selenium, Cypress, Playwright, framework design, and maintainable automated tests.
---

# Test Automation

Build robust automated test suites using modern frameworks like Selenium, Cypress, and Playwright for efficient regression testing.

## When to Use This Skill

- Regression testing automation
- CI/CD integration
- API testing automation
- Cross-browser testing
- Performance testing
- Smoke test automation
- Data-driven testing
- Continuous testing

## Core Concepts

### 1. Cypress Test Example

```javascript
// cypress/e2e/login.cy.js
describe('User Login', () => {
  beforeEach(() => {
    cy.visit('/login')
  })

  it('should login successfully with valid credentials', () => {
    cy.get('[data-testid="email"]').type('user@example.com')
    cy.get('[data-testid="password"]').type('SecurePass123!')
    cy.get('[data-testid="login-btn"]').click()

    cy.url().should('include', '/dashboard')
    cy.get('[data-testid="welcome-msg"]')
      .should('contain', 'Welcome')
  })

  it('should show error with invalid credentials', () => {
    cy.get('[data-testid="email"]').type('invalid@example.com')
    cy.get('[data-testid="password"]').type('wrong')
    cy.get('[data-testid="login-btn"]').click()

    cy.get('[data-testid="error-msg"]')
      .should('be.visible')
      .and('contain', 'Invalid credentials')
  })
})
```

### 2. Page Object Model

```javascript
// pages/LoginPage.js
class LoginPage {
  get emailInput() { return cy.get('[data-testid="email"]') }
  get passwordInput() { return cy.get('[data-testid="password"]') }
  get loginButton() { return cy.get('[data-testid="login-btn"]') }
  get errorMessage() { return cy.get('[data-testid="error-msg"]') }

  login(email, password) {
    this.emailInput.type(email)
    this.passwordInput.type(password)
    this.loginButton.click()
  }

  verifyLoginError(message) {
    this.errorMessage.should('contain', message)
  }
}

export default new LoginPage()

// Test using Page Object
import LoginPage from '../pages/LoginPage'

it('login test', () => {
  cy.visit('/login')
  LoginPage.login('user@example.com', 'password')
})
```

### 3. API Test Example (REST Assured - Java)

```java
@Test
public void testGetUser() {
    given()
        .baseUri("https://api.example.com")
        .header("Authorization", "Bearer " + token)
        .pathParam("id", "123")
    .when()
        .get("/users/{id}")
    .then()
        .statusCode(200)
        .body("id", equalTo("123"))
        .body("name", notNullValue())
        .body("email", containsString("@"));
}
```

## Best Practices

1. **Use selectors wisely** - data-testid over CSS
2. **Page Object Model** - Maintainable structure
3. **Wait strategies** - Explicit over implicit
4. **Independent tests** - No test dependencies
5. **Test data management** - Fixtures, factories
6. **Clear assertions** - Meaningful error messages
7. **Screenshot on failure** - Debug information
8. **CI/CD integration** - Automated execution

## Resources

- **Cypress**: https://www.cypress.io
- **Playwright**: https://playwright.dev
- **Selenium**: https://www.selenium.dev
