# No guarantee near CTA — dev spec
Site: allbirds.com · Priority 10 · High · Effort: Medium (2-5 days)

## Problem
The product page lacks a visible guarantee or return policy near the add-to-cart button, leaving purchase hesitation unaddressed.

## Evidence (from the live site)
> Product page shows 'Get Notified' CTA (likely out of stock) and 'Learn More' but no guarantee or return policy text near the CTA; trust signals are not evident in the captured body sample.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: No guarantee or return policy visible near the CTA.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified; notes: Add a line under the CTA: 'Free shipping & returns. 30-day guarantee.'

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a line under the CTA: 'Free shipping & returns. 30-day guarantee.'
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_guarantee_near_cta` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
