# Vague hero copy — dev spec
Site: allbirds.com · Priority 3 · High · Effort: Low (0.5-2 days)

## Problem
The hero headline is abstract and doesn't communicate the product category or key benefit, failing to answer the visitor's intent to find comfortable, sustainable shoes.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' with CTAs 'Shop Men' and 'Shop Women' but no subheadline or explicit mention of shoes, comfort, or sustainability.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Shop Men / Shop Women; notes: No subheadline; the hero is feature-led and doesn't specify what is being sold.

## Required change
h1: Shoes That Feel Like Nothing Else; cta: Shop Men's Shoes / Shop Women's Shoes; notes: Add a subheadline: 'Made from natural materials, designed for all-day comfort.' This directly addresses the visitor's intent to find comfortable, sustainable footwear.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a subheadline: 'Made from natural materials, designed for all-day comfort.' This directly addresses the visitor's intent to find comfortable, sustainable footwear.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
