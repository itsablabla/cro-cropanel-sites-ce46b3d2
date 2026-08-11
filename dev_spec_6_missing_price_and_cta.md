# Missing price and CTA — dev spec
Site: allbirds.com · Priority 6 · Urgent · Effort: Medium (2-5 days)

## Problem
The product page lacks a visible price and a clear add-to-cart CTA, preventing the visitor from completing a purchase.

## Evidence (from the live site)
> H1: 'Anytime Ankle Sock' but no price or 'Add to Cart' button in the extracted data; CTAs only include 'Learn More' and 'Sign Up'.

## Current state
h1: Anytime Ankle Sock; cta: Learn More; notes: No price displayed and no add-to-cart CTA; the page appears to be missing essential purchase elements.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart - $14; notes: Ensure the price is visible and the primary CTA is 'Add to Cart' to facilitate purchase.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Ensure the price is visible and the primary CTA is 'Add to Cart' to facilitate purchase.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_price_and_cta` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
