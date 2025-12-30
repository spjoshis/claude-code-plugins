---
name: usability-testing
description: Master usability testing with test planning, moderation, analysis, and actionable recommendations.
---

# Usability Testing

Conduct effective usability tests to validate designs, identify issues, and gather user feedback for improvement.

## When to Use This Skill

- Validating designs
- Identifying usability issues
- Comparing alternatives
- Pre-launch testing
- Iterative improvement
- Feature validation
- Accessibility testing
- Competitive analysis

## Core Concepts

### 1. Test Plan

```markdown
# Usability Test Plan: Checkout Flow

**Objective**: Validate checkout usability and identify friction points

**Participants**: 8 users
- 4 first-time users
- 4 returning customers
- Mix of mobile (4) and desktop (4)

**Method**: Moderated remote testing
**Duration**: 45 minutes per session
**Tool**: Zoom + UserTesting.com

**Tasks**:
1. Find and add product to cart (Success: <2 min)
2. Apply discount code (Success: <30 sec)
3. Complete checkout as guest (Success: <3 min)
4. Create account during checkout (Success: <4 min)

**Metrics**:
- Task completion rate
- Time on task
- Error rate
- Satisfaction rating (1-5)

**Questions**:
1. How would you rate the checkout process? (1-5)
2. What was most confusing?
3. What would you improve?
4. Would you use this again?
```

### 2. Test Script

```markdown
## Usability Test Script

**Welcome** (5 min):
- Thank you for participating
- We're testing the website, not you
- Think aloud as you complete tasks
- No wrong answers
- Any questions before we start?

**Background** (5 min):
1. How often do you shop online?
2. What devices do you typically use?
3. Any accessibility needs?

**Tasks** (25 min):

**Task 1**: "You need a wireless mouse for your laptop. Show me how you would find and purchase one."

*Observe*:
- Navigation path
- Search usage
- Product selection criteria
- Hesitations

*Follow-up*:
- What made you choose that product?
- Was anything confusing?

**Task 2**: "You have a coupon code 'SAVE20'. Apply it to your order."

*Observe*:
- Can they find coupon field?
- Understand where to enter it?
- Notice discount applied?

**Wrap-up** (10 min):
- Overall impression (1-5)?
- Most challenging part?
- What would you improve?
- Anything else?

**Thank and compensate**
```

### 3. Findings Report

```markdown
# Usability Test Results

**Date**: January 15, 2024
**Participants**: 8 users
**Product**: E-commerce Checkout

## Executive Summary
Overall checkout usability is good (avg 4.2/5), but 3 critical issues identified that impact conversion.

## Key Findings

### Critical Issues (Fix Immediately)

**Issue #1: Coupon Code Not Discoverable**
- **Severity**: High
- **Frequency**: 6/8 users missed it
- **Impact**: Lost discount opportunities
- **Evidence**: "I had a code but couldn't find where to use it"
- **Recommendation**: Make coupon field visible above payment section

**Issue #2: Guest Checkout Confusing**
- **Severity**: High
- **Frequency**: 5/8 users
- **Impact**: 3 users abandoned checkout
- **Evidence**: "Do I need an account to purchase?"
- **Recommendation**: Clearly label "Continue as Guest" button

### Medium Issues

**Issue #3: Mobile Form Fields Too Small**
- **Severity**: Medium
- **Frequency**: 4/4 mobile users
- **Recommendation**: Increase touch target to 48px minimum

## Metrics

| Metric | Target | Actual |
|--------|--------|--------|
| Task completion | >90% | 75% |
| Avg time on task | <3 min | 4.5 min |
| Error rate | <10% | 25% |
| Satisfaction | >4.0 | 4.2 |

## Recommendations
1. Move coupon field above payment (Priority: P0)
2. Improve guest checkout CTA (Priority: P0)
3. Increase mobile form field size (Priority: P1)
4. Add progress indicator (Priority: P2)
```

## Best Practices

1. **Recruit representative users** - Match target audience
2. **Test with 5-8 users** - Identify 80% of issues
3. **Think aloud protocol** - Understand reasoning
4. **Don't lead participants** - Let them struggle
5. **Record sessions** - Review and clip highlights
6. **Take detailed notes** - Quotes, observations
7. **Prioritize findings** - Severity and frequency
8. **Test iteratively** - Continuous improvement

## Resources

- **Don't Make Me Think**: Steve Krug
- **Rocket Surgery Made Easy**: Steve Krug
- **UserTesting.com**: Remote testing platform
- **Maze**: Rapid testing tool
