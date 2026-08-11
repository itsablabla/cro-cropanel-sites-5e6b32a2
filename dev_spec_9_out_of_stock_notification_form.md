# Out-of-stock notification form — dev spec
Site: allbirds.com · Priority 9 · High · Effort: Medium (2-5 days)

## Problem
The product page for the Anytime Ankle Sock shows a 'Get Notified' CTA, indicating the product is out of stock, but the form may lack trust signals or a clear restock timeline, potentially losing interested customers.

## Evidence (from the live site)
> The product page CTAs include 'Get Notified' and 'Learn More', and the page has a form with 1 input and submit 'Get Notified'.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: The form likely captures email for restock notification, but no timeline or incentive is shown.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified When Back in Stock; notes: Add an estimated restock date or a small incentive (e.g., free shipping on next order) to encourage sign-ups.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add an estimated restock date or a small incentive (e.g., free shipping on next order) to encourage sign-ups.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_out_of_stock_notification_form` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
