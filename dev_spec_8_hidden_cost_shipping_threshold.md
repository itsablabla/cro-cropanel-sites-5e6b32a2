# Hidden cost: shipping threshold — dev spec
Site: allbirds.com · Priority 8 · Urgent · Effort: Medium (2-5 days)

## Problem
The product page shows a $10 price but does not disclose the $5 shipping fee or the $100 free-shipping threshold, creating a hidden cost that may trigger cart abandonment.

## Evidence (from the live site)
> Price: '$10' (from prices array). Body sample on homepage: 'Spend more to earn free shipping! Shipping $5.00'
> Body sample: 'Free ground shipping on orders over $100' appears only in the top announcement bar, while the hero copy 'Wildly Comfortable. Super Natural.' and CTAs 'SHOP MEN' / 'SHOP WOMEN' make no mention of the threshold.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: Price shown as $10, no mention of shipping costs or threshold on the product page.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Display 'Free shipping on orders over $100' near the price or add-to-cart button to set expectations upfront.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display 'Free shipping on orders over $100' near the price or add-to-cart button to set expectations upfront.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hidden_cost_shipping_threshold` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
