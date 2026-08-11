# Missing size selector on PDP — dev spec
Site: allbirds.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
Product page lacks a size selection field, forcing users to guess or leave, increasing friction and potential returns.

## Evidence (from the live site)
> Product page for 'Anytime Ankle Sock' shows no size input in the forms inventory; only 'Learn More' CTA visible.

## Current state
h1: Anytime Ankle Sock; cta: Learn More; notes: No size dropdown or selector visible in the extracted data.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Add a size selector (e.g., S/M/L) and an 'Add to Cart' button to reduce friction and prevent size-related returns.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a size selector (e.g., S/M/L) and an 'Add to Cart' button to reduce friction and prevent size-related returns.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_size_selector` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
