# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

delegated: standalone HTML, CSS and JavaScript with no runtime dependencies; chosen for a reliable, directly runnable case-demo prototype that can keep all simulated role views synchronized in one browser session.

## Users

Primary users are teammates and case judges presenting or evaluating a parcel journey. They need to follow a single parcel and understand each role's action and its effect. Demonstration roles are Operations, Rider, Recipient and Nearby Buyer.

## Product Purpose

A browser prototype demonstrates a single Meesho/Valmo-style parcel from checkout through address and phone confirmation, hub routing, rider assignment, delivery attempt, customer choice and final delivery or return. Success means a presenter can demonstrate both the customer-chosen reattempt path and the explicit-refusal recovery path across synchronized role views.

## Positioning

One shared parcel record and event timeline makes each handoff visible to every role while preserving distinct role-specific screens.

## Operating Context

Used as a case-competition product demonstration in a browser. The presenter can switch between synchronized Operations, Rider, Recipient and Nearby Buyer views while following one parcel from checkout.

## Capabilities and Constraints

- Simulate phone OTP and address confirmation, hub scans and routing, rider assignment and doorstep outcomes, recipient-selected reattempt, explicit refusal, seller/item eligibility checks, Nearby Finds acceptance, delivery confirmation, and a timed return fallback.
- Actions update one shared parcel state and event history. The presenter can replay either outcome from the start.
- All parcel, person, product, timing, payout and operational records are synthetic and must be labeled as such.
- No live Valmo or Meesho APIs, real SMS/OTP, GPS, calls, payments, seller inventory, authentication, or backend persistence.
- Browser-only demonstration; no deployment target is confirmed.

## Brand Commitments

The user requested a Meesho-inspired customer and Nearby Finds experience, with clear Valmo-style rider and operations surfaces. Use this as inspiration, not as an assertion of official Meesho or Valmo integration or approved design assets.

## Evidence on Hand

The confirmed flow and requirements in the conversation are the product source. Existing case research and prototype are reference material only; their screens, code and records are not the build base. No live order data, customer evidence, seller inventory, operational telemetry, or approved product photography is available.

## Product Principles

- Every role sees the same parcel state and event history.
- Customer choice is explicit; no answer is not a refusal.
- Rider evidence supports review and does not automatically prove intent.
- Nearby resale requires seller approval and item eligibility; otherwise the parcel follows a timed return path.
- Clearly separate simulated content from measured or connected system data.
