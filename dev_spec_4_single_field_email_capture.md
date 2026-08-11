# Single-field email capture — dev spec
Site: allbirds.com · Priority 4 · High · Effort: Medium (2-5 days)

## Problem
The homepage email capture form asks only for an email address, which is minimal and frictionless, but it lacks a clear value proposition or incentive, potentially reducing sign-up conversion.

## Evidence (from the live site)
> The homepage has a form with 1 input and submit button labeled 'Sign Up', with no accompanying text or incentive visible in the body sample.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Sign Up; notes: Form appears in footer area with no additional context or incentive.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Sign Up for 10% Off; notes: Add a clear incentive (e.g., discount) and a brief value proposition to increase email sign-ups.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a clear incentive (e.g., discount) and a brief value proposition to increase email sign-ups.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_single_field_email_capture` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
