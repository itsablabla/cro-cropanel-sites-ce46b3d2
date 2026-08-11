# Email-only signup lacks incentive — dev spec
Site: allbirds.com · Priority 10 · High · Effort: Medium (2-5 days)

## Problem
The single email input with a generic 'Sign Up' CTA provides no explicit value exchange, likely reducing opt-in rates.

## Evidence (from the live site)
> Form on homepage has 1 input, no labels, submit button 'Sign Up'.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Sign Up; notes: No mention of discount, early access, or other benefit.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Get 10% Off Your First Order; notes: Add explicit incentive near the email field to increase signups.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add explicit incentive near the email field to increase signups.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_email_signup_lacks_incentive` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
