# Vague hero copy — dev spec
Site: allbirds.com · Priority 2 · Urgent · Effort: Low (0.5-2 days)

## Problem
The hero headline and subhead are abstract and feature-led, failing to connect with the visitor's intent to find comfortable, sustainable shoes for their specific needs.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN' and 'SHOP WOMEN' with no subhead visible in the crawl.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: The hero lacks a clear value proposition or problem-solution framing; it's a brand slogan rather than a message that addresses visitor intent.

## Required change
h1: Shoes That Feel Like Nothing Else; cta: Shop Men's Shoes / Shop Women's Shoes; notes: Rewrite to speak to the visitor's desire for comfort and ease, and make the CTAs more specific to the product category.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Rewrite to speak to the visitor's desire for comfort and ease, and make the CTAs more specific to the product category.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
