# Competing primary CTAs — dev spec
Site: allbirds.com · Priority 1 · Urgent · Effort: Medium (2-5 days)

## Problem
The hero presents two equally prominent CTAs (SHOP MEN and SHOP WOMEN) that split user focus and delay the primary conversion action.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN', 'SHOP WOMEN'
> Hero copy: 'Wildly Comfortable. Super Natural.' with CTAs 'SHOP MEN' and 'SHOP WOMEN' with no subhead visible in the crawl.
> Hero section contains 'SHOP MEN' and 'SHOP WOMEN' CTAs, but no 'Shop All' CTA in the hero; 'Shop All' appears in nav but not as a hero CTA.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Two primary CTAs of equal weight, no single clear next step.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP BESTSELLERS; notes: Single primary CTA to a neutral, high-intent collection; secondary links to Men/Women can be placed below.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Single primary CTA to a neutral, high-intent collection; secondary links to Men/Women can be placed below.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_primary_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
