# Shipping delay notice — dev spec
Site: allbirds.com · Priority 2 · High · Effort: Medium (2-5 days)

## Problem
A prominent notice about shipping delays (up to 30 days) is placed in the top bar, potentially deterring immediate purchases due to perceived fulfillment risk.

## Evidence (from the live site)
> Body sample: 'Due to increased demand, orders may take up to 30 days to ship.'
> Body sample: 'Due to increased demand, orders may take up to 30 days to ship.' displayed prominently at top of homepage.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Shop All; notes: Notice appears in top bar, visible on all pages, may cause hesitation.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop All; notes: Move delay notice to checkout or provide a more reassuring message with expedited options.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Move delay notice to checkout or provide a more reassuring message with expedited options.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_shipping_delay_notice` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
