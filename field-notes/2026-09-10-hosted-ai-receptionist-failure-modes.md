# Five ways a hosted AI receptionist fails

**Date learned:** 2026-09-10 · **Domain:** AI governance · **Framework reference:** [01-certification-framework.md](../01-certification-framework.md), guardrails by tier; [06-model-assessment-program.md](../06-model-assessment-program.md)

## What we were trying to do

Run a hosted AI phone receptionist on our own business line for several weeks before offering it to clients, then audit its real call and message history rather than trusting the demo.

## What actually happened

Reading the production transcripts turned up five behaviors the demo never showed:

1. **Garbled number capture dropped a real lead.** A caller with a genuine need gave a callback number verbally in a confusing way. The agent recorded an invalid number and never followed up. There was no fallback when capture confidence was low.
2. **Text messages to some number types silently failed.** A caller asked to be texted a booking link. The number was toll-free, the message failed to deliver, and the agent had no visibility into the failure and never retried or alerted anyone.
3. **The agent got stuck in a loop with another machine.** It exchanged roughly thirty identical messages in a few minutes with a vendor's auto-responder, each side repeating canned text. Real cost, zero value, no loop detection.
4. **The agent booked a real calendar commitment with no human review.** In that same exchange it confirmed an appointment on the operator's calendar. The operator discovered it only by going looking.
5. **It correctly refused phone-scam attempts.** Two robocalls claiming a business listing had been flagged were declined with a warning that they looked like scams. This is the positive case, and it is worth noting that it worked.

## Why it happened

Hosted agents are sold as hands-off. They are not. Each failure above is a missing guardrail at a point where the agent's confidence should have been checked or its authority should have been limited.

## What we changed

Each finding became a requirement before the product goes near a client:

- a fallback when number capture confidence is low: re-ask, or hand to a human
- delivery-failure alerting and retry for outbound messages
- loop detection for machine-to-machine exchanges
- human-in-the-loop confirmation before the agent commits anything to a calendar or makes a promise on someone's behalf

## How we know it worked

Not yet proven. These are requirements, and the note will be updated when each one has been verified against production traffic.

## What we'd tell someone doing this tomorrow

Audit the transcripts, not the demo. Set a date a few weeks after go-live and read everything the agent said and did. The failures that matter are the quiet ones: the lead that never got a callback, the booking nobody reviewed.
