# Valmo Delivery Recovery Console — Prototype

Standalone interactive demonstration for the selected address/hub, delivery attempt/contact, and COD refusal problem areas.

## Open

Open `index.html` directly in a modern browser. It has no build step or external runtime dependency.

## Prototype areas

- **Parcel exceptions:** screenshot-inspired operations dashboard with four sample queues, filters, event/owner/action/deadline rows, parcel decision detail, event-to-outcome handoffs, minimum event architecture, and metric definitions. Every record/count is synthetic UI data.
- **Control room:** sample parcel queue and end-to-end event timeline.
- **Address & hub:** editable address completeness, confidence rules, destination route token, mismatch scan, and salvage decision.
- **Attempt recovery:** reason-specific NDR state, customer options, simulated contact, and multi-signal attempt-review score.
- **Refusal desk:** explicit refusal vs temporary unavailability; seller/product eligibility; local recovery or time-bounded reverse batching.
- **Economics:** editable order mix and unit costs, cost-node check, distance scenario view, local recovery comparison, and formulas/exclusions.
- **Pilot lab:** 30/60/90 plan, metrics/guardrails, and approximate two-arm proportion sample-size calculator.
- **Rulebook:** decision rules, data labels, and known prototype boundaries.

## Data and calculation labels

The interface separates challenge scenario inputs from external reference facts, prototype rules, and editable scenario assumptions. Sample parcels, addresses, hubs, and events are fictional. No calculated change is a measured Valmo result. The cost model excludes forward costs on failed shipments because those costs are not specified in the scenario inputs.

All changes are held in browser memory/local storage only. Use **Reset demo** to restore the seeded sample state.

## How to explore

1. Start in **Parcel exceptions**. Switch queues, filter sample records, select a parcel row, inspect the detail tabs, reassign its demo owner, or save a local sample decision note. Use the handoff map, event architecture and metric definitions below the queue as the operating model.
2. In **Control room**, switch among the fictional parcels in the selector or queue.
3. In **Address & hub**, edit fields freely, then select **Update preview** to refresh scores and transfer feasibility. Confirm a hub transfer only when the displayed checks pass.
4. In **Attempt recovery**, choose a customer option and confirm it to change the parcel state. Toggle evidence signals and observe the score. The embedded **Rider app** preview simulates route viewing, masked-call action, COD collection, OTP delivery confirmation and attempt-reason reporting.
5. In **Refusal desk**, open the confirmed-refusal parcel from the selector. Change the seller/item eligibility checks; the local offer is blocked when a required check fails. Edit the local recovery and batch assumptions.
6. In **Economics**, edit any number of order-mix, RTO, unit-cost, improvement and intervention inputs, then select **Update preview** to recalculate baseline, proposed partial cost and net savings.
7. In **Pilot lab**, edit target improvement, design effect and attrition, then select **Update preview** to recalculate the two-arm sample estimate.
8. In **Rulebook**, change score thresholds, release batch size or parcel hold limit, then select **Update preview**; other screens use the saved values.

Field edits save without rebuilding the screen, so dropdowns and typing retain focus. Parcel selection refreshes the current work area while keeping the selector in place. Use **Update preview** when you want calculated panels to refresh. The rider phone is embedded in the same **Attempt recovery** page; scroll below the recovery choices to view it.

## Core calculation rules

- **Address confidence:** 25 address text + 20 valid six-digit pincode + 20 confirmed locality + 20 customer-confirmed pin + 15 landmark/directions. Missing values score zero. A written address is retained even when a pin is added.
- **Attempt evidence:** assignment 25 + plausible route 25 + GPS quality 0–25 + contact 15 + scan sequence 10. This is a review aid and never automatically accuses or penalizes a rider.
- **Hub transfer:** transfer cost + handling must be no greater than the alternate route; transfer ETA must fit the remaining promise; parcel age plus ETA must stay within the configured holding cap.
- **Local recovery:** eligible units × sell-through × (seller contribution + avoided reverse cost − local delivery) − eligible units × (handling + discount subsidy + hold-risk allowance). Requires seller-approved economics and safe inventory rules.
- **Reverse consolidation:** shared trip cost ÷ parcels in batch + handling per parcel. Release at batch threshold **or** service/seller deadline, whichever arrives first.
- **Partial scenario cost:** successful orders × successful-forward cost + RTO orders × reverse cost. It excludes forward cost already incurred on failed shipments, so it is not all-in network cost.
- **Pilot sample estimate:** two-proportion normal approximation, two-sided 5% significance and 80% power, inflated for design effect and attrition. Cluster tests require cluster-level inputs before the estimate can be used for planning.

## Default scenario arithmetic

For 100 orders, 80% COD, 20% COD RTO and 5% prepaid RTO: 80 COD orders × 20% = 16 COD RTOs; 20 prepaid orders × 5% = 1 prepaid RTO; total = 17 RTOs. With ₹120 reverse cost and ₹50 successful-forward cost, partial baseline cost is ₹2,040 reverse + ₹4,150 successful forward = ₹6,190. A 2 percentage-point improvement produces 15 RTOs; at ₹1.50 intervention cost per order, proposed partial cost is ₹6,200, or ₹10 higher than baseline. The break-even intervention cap is ₹1.40/order. All values are a scenario demonstration, not a forecast or company result.
