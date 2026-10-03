# An agent authenticated as its human

**Date learned:** 2026-08-06 · **Domain:** AI governance · **Framework reference:** [00-charter.md](../00-charter.md) principle 7, "the agent gets a badge, not a key"; [02-registry-and-serialization.md](../02-registry-and-serialization.md)

## What we were trying to do

Run an outbound-communication agent with a disclosed AI persona and its own mailbox, so that recipients always knew they were talking to an agent and the human operator stayed accountable for it.

## What actually happened

The agent sent mail authenticating as the human operator's own address instead of the disclosed persona's. Recipients could not tell the agent from the person. Reading the sent folder afterward, neither could the operator.

## Why it happened

Early on, the agents ran under the operator's identity because it was the fast path: one mailbox, one set of credentials, one address, and every tool assumed a single human user. Nothing enforced the separation. It was policy, held in people's heads, and policy failed the first time a configuration defaulted to the human's account.

The property that broke was non-repudiation. For a security practice, that is the entire product.

## What we changed

Every agent now has its own Unix home, its own mailbox, its own address, its own credentials, and its own audit trail, bound one-to-one to a human operator. The binding is enforced in the database, not in a document:

- an agent with no live human binding cannot be active
- every agent action carries both operator identity and agent identity, read from the live binding at write time, so a caller cannot assert who supervises it
- an asserted sender or source address that does not match the registry is refused and raises a critical alert

The last rule is this incident turned into a control, enforced as a database constraint with a test that reproduces the original failure.

## How we know it worked

The condition that caused the incident is now a failing test. It cannot be reintroduced without the test suite going red.

## What we'd tell someone doing this tomorrow

Give the agent a badge, not a key. If your agents share a human's identity for convenience, you have already lost non-repudiation; you just haven't noticed yet. Enforce the separation somewhere a human can't forget it.
