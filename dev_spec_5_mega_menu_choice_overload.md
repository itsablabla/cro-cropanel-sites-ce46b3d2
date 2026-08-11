# Mega-menu choice overload — dev spec
Site: allbirds.com · Priority 5 · High · Effort: Low (0.5-2 days)

## Problem
The mega-menu presents 20+ nav items with multiple subcategories, causing choice overload and decision paralysis for users.

## Evidence (from the live site)
> nav_items list includes 20 items: 'New Arrivals', 'Shop All', 'Bestsellers', 'LEATHER ALTERNATIVES', 'Men's Shoes', 'Sneakers', 'Slip Ons', 'Sandals', 'Active', 'All-Weather', 'Runner NZ', 'Cruiser', 'Tree Runner NZ', 'Socks', 'Men's Apparel', 'Women's Shoes', 'Trainers', 'Flats', 'Canvas Cruiser', 'Women's Apparel'.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Shop All; notes: Mega-menu with 20+ items, multiple subcategories, and duplicate links (e.g., 'Tree Runner NZ' appears twice).

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop All; notes: Simplify mega-menu to 5-7 top-level categories with clear subcategories, remove duplicate links, and use descriptive labels to reduce cognitive load.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Simplify mega-menu to 5-7 top-level categories with clear subcategories, remove duplicate links, and use descriptive labels to reduce cognitive load.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_mega_menu_choice_overload` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
