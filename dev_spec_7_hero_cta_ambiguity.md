# Hero CTA ambiguity — dev spec
Site: allbirds.com · Priority 7 · High · Effort: Medium (2-5 days)

## Problem
The hero CTAs 'SHOP MEN' and 'SHOP WOMEN' are gender-specific, potentially alienating non-binary or gender-neutral shoppers and lacking a clear 'Shop All' option.

## Evidence (from the live site)
> Hero section contains 'SHOP MEN' and 'SHOP WOMEN' CTAs, but no 'Shop All' CTA in the hero; 'Shop All' appears in nav but not as a hero CTA.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Hero CTAs force gender choice, which may not align with all users' preferences.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN / SHOP ALL; notes: Add a neutral 'Shop All' CTA to the hero to accommodate all users and reduce friction for those not ready to choose a gender.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a neutral 'Shop All' CTA to the hero to accommodate all users and reduce friction for those not ready to choose a gender.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hero_cta_ambiguity` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
