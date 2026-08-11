# Free shipping threshold hidden — dev spec
Site: allbirds.com · Priority 4 · High · Effort: Medium (2-5 days)

## Problem
The free shipping threshold is only mentioned in the body text, not prominently displayed near pricing or CTAs, causing potential surprise at checkout.

## Evidence (from the live site)
> Body sample: 'Free ground shipping on orders over $100' appears in the page body, but the H1 and CTAs do not mention this threshold.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Shop All; notes: Free shipping threshold is buried in body text, not near CTAs or pricing.

## Required change
h1: Wildly Comfortable. Super Natural. Free Shipping Over $100.; cta: Shop All; notes: Add free shipping threshold to hero or near CTAs to set expectations early.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add free shipping threshold to hero or near CTAs to set expectations early.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_free_shipping_threshold_hidden` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
