# Multiple competing CTAs — dev spec
Site: allbirds.com · Priority 1 · High · Effort: Medium (2-5 days)

## Problem
The homepage hero presents multiple competing CTAs (Shop Men, Shop Women, Shop All) without a single clear primary action, diluting user focus and reducing click-through to a specific product category.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'Shop All', 'Shop Womens', 'Shop Mens', 'SHOP MEN', 'SHOP WOMEN'

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Shop All, Shop Womens, Shop Mens, SHOP MEN, SHOP WOMEN; notes: Multiple CTAs of equal visual weight in hero, no clear primary path.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop Best Sellers; notes: Single primary CTA directing to a curated collection, reducing choice overload.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Single primary CTA directing to a curated collection, reducing choice overload.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_multiple_competing_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
