---
name: user-story-writing
description: Master writing effective user stories with INVEST principles, acceptance criteria, story slicing, and agile best practices for clear, testable requirements.
---

# User Story Writing

Write effective user stories that capture customer value, enable development teams, and ensure clear acceptance criteria for agile delivery.

## When to Use This Skill

- Breaking down features into user stories
- Writing clear requirements for development
- Defining acceptance criteria
- Creating testable stories
- Estimating story complexity
- Facilitating backlog refinement
- Communicating with stakeholders
- Planning sprints and releases

## Core Concepts

### 1. User Story Format

**Standard Format**:
```
As a [type of user],
I want [an action or feature],
So that [a benefit or value].
```

**Example**:
```
As a customer,
I want to save items to a wishlist,
So that I can purchase them later.
```

### 2. INVEST Principles

- **Independent**: Stories can be developed in any order
- **Negotiable**: Details can be discussed and refined
- **Valuable**: Delivers clear value to users or business
- **Estimable**: Team can estimate effort required
- **Small**: Can be completed within a sprint
- **Testable**: Has clear pass/fail criteria

### 3. Story Components

- **Title**: Brief, descriptive name
- **Description**: As a/I want/So that format
- **Acceptance Criteria**: Specific conditions for completion
- **Story Points**: Complexity/effort estimate
- **Priority**: Business value ranking
- **Dependencies**: Related stories or technical requirements

## Practical Patterns

### Pattern 1: E-commerce User Stories

```markdown
## Story 1: Product Search

**As a** shopper
**I want** to search for products by keyword
**So that** I can quickly find items I'm looking for

**Acceptance Criteria:**
- Given I am on the homepage
- When I enter a keyword in the search box
- Then I see relevant product results within 2 seconds
- And results are sorted by relevance
- And I see product image, name, price, and rating

**Story Points:** 5
**Priority:** High
**Dependencies:** Product catalog API
```

```markdown
## Story 2: Add to Cart

**As a** shopper
**I want** to add products to my shopping cart
**So that** I can purchase multiple items together

**Acceptance Criteria:**
- Given I am viewing a product
- When I click "Add to Cart"
- Then the product is added to my cart
- And I see a confirmation message
- And the cart icon shows updated item count
- And I can continue shopping or proceed to checkout

**Story Points:** 3
**Priority:** High
**Dependencies:** Shopping cart service
```

### Pattern 2: SaaS Application Stories

```markdown
## Story: User Registration

**As a** new user
**I want** to create an account with email and password
**So that** I can access the platform

**Acceptance Criteria:**
- Given I am on the registration page
- When I enter valid email and password
- Then my account is created
- And I receive a verification email
- And I am redirected to onboarding

**Validation Rules:**
- Email must be valid format
- Password must be 8+ characters
- Password must include uppercase, lowercase, number
- Email must not already exist in system

**Story Points:** 5
**Priority:** Critical
```

### Pattern 3: Job Stories (Alternative Format)

```markdown
## When [situation], I want to [motivation], so I can [expected outcome]

**Example:**
When I'm reviewing my monthly expenses,
I want to filter transactions by category,
So I can understand where I'm spending the most money.

**Acceptance Criteria:**
- Filter dropdown shows all expense categories
- Selecting a category updates the transaction list
- Total amount updates to show filtered sum
- Can clear filter to show all transactions
```

### Pattern 4: Story Slicing

**Large Story (Epic):**
```
As a user, I want a comprehensive dashboard
So that I can monitor all my metrics.
```

**Sliced Stories:**
```
Story 1: As a user, I want to view key metrics (revenue, users)
         So that I can see high-level performance.

Story 2: As a user, I want to filter metrics by date range
         So that I can analyze specific time periods.

Story 3: As a user, I want to export dashboard data to CSV
         So that I can analyze it in Excel.

Story 4: As a user, I want to customize which metrics display
         So that I can focus on what matters to me.
```

### Pattern 5: Acceptance Criteria with Gherkin

```gherkin
Feature: User Login

Scenario: Successful login with valid credentials
  Given I am on the login page
  When I enter valid email "user@example.com"
  And I enter valid password "SecurePass123"
  And I click the "Login" button
  Then I should be redirected to the dashboard
  And I should see a welcome message

Scenario: Failed login with invalid password
  Given I am on the login page
  When I enter valid email "user@example.com"
  And I enter invalid password "wrong"
  And I click the "Login" button
  Then I should see an error message "Invalid credentials"
  And I should remain on the login page
```

### Pattern 6: Technical Stories

```markdown
## Story: API Performance Optimization

**As a** developer
**I want** to optimize the user search API response time
**So that** the application provides a better user experience

**Acceptance Criteria:**
- API response time is reduced to under 200ms (p95)
- Database queries are optimized with proper indexing
- Caching is implemented for frequent searches
- Load testing confirms performance improvement
- No regression in search result accuracy

**Technical Notes:**
- Add indexes on users.email and users.name
- Implement Redis caching with 5-minute TTL
- Use database query optimization tools

**Story Points:** 8
**Priority:** Medium
```

### Pattern 7: Bug Fix Stories

```markdown
## Story: Fix Checkout Payment Error

**As a** customer
**I want** the payment to process correctly
**So that** I can complete my purchase

**Current Behavior:**
- Payment fails intermittently (10% of transactions)
- Error message: "Payment gateway timeout"
- Occurs during peak hours

**Expected Behavior:**
- Payment succeeds consistently
- Proper error handling with retry logic
- Clear error messages for actual failures

**Acceptance Criteria:**
- Payment success rate increases to >99%
- Timeout increased to 30 seconds
- Retry logic implemented (3 attempts)
- User sees clear status during processing
- Failed payments provide actionable error messages

**Story Points:** 5
**Priority:** Critical
```

### Pattern 8: Non-Functional Requirement Stories

```markdown
## Story: Improve Page Load Performance

**As a** user
**I want** pages to load quickly
**So that** I have a smooth browsing experience

**Acceptance Criteria:**
- Homepage loads in under 2 seconds (p90)
- Largest Contentful Paint (LCP) under 2.5s
- First Input Delay (FID) under 100ms
- Cumulative Layout Shift (CLS) under 0.1
- Performance measured with Lighthouse
- Improvements verified on mobile and desktop

**Implementation:**
- Lazy load images
- Minify CSS and JavaScript
- Implement code splitting
- Use CDN for static assets

**Story Points:** 8
**Priority:** High
```

## Best Practices

### Story Writing
1. **Focus on value** - Every story delivers user/business value
2. **Keep stories small** - Completable within one sprint
3. **Write from user perspective** - Emphasize who and why
4. **Include acceptance criteria** - Clear, testable conditions
5. **Make stories independent** - Minimize dependencies
6. **Use consistent format** - Team agreement on structure
7. **Refine collaboratively** - Involve team in refinement
8. **Estimate relative size** - Use story points, not hours

### Acceptance Criteria
1. **Be specific** - Clear, unambiguous conditions
2. **Make testable** - Can verify pass/fail
3. **Cover edge cases** - Include error scenarios
4. **Use Gherkin when helpful** - Given/When/Then format
5. **Define done** - What complete means
6. **Include NFRs** - Performance, security, accessibility
7. **Get team agreement** - Shared understanding
8. **Review before sprint** - Ensure clarity

### Common Pitfalls to Avoid
- Writing technical tasks instead of user stories
- Stories too large (spanning multiple sprints)
- Vague acceptance criteria
- Missing the "so that" (value statement)
- No user perspective
- Implementation details in stories
- Forgetting edge cases
- Not testable

## Tools and Templates

### Story Template
```markdown
## [Story Title]

**As a** [user type]
**I want** [action/feature]
**So that** [benefit/value]

**Acceptance Criteria:**
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

**Story Points:** [1, 2, 3, 5, 8, 13]
**Priority:** [Critical, High, Medium, Low]
**Dependencies:** [List any dependencies]
**Notes:** [Additional context]
```

### Epic Template
```markdown
## Epic: [Epic Name]

**Goal:** [What we want to achieve]
**Success Metrics:** [How we measure success]

**User Stories:**
1. Story 1 - [Brief description]
2. Story 2 - [Brief description]
3. Story 3 - [Brief description]

**Timeline:** [Target quarter/release]
**Business Value:** [Why this matters]
```

## Resources

- **INVEST in Good Stories**: https://www.agilealliance.org/glossary/invest
- **User Story Mapping**: Mike Cohn's guide
- **Gherkin Reference**: https://cucumber.io/docs/gherkin/
- **Story Splitting Techniques**: https://www.agilealliance.org/resources/experience-reports/
- **Mike Cohn's User Stories Applied**: Definitive guide to user stories
