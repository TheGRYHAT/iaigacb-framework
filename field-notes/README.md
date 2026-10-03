# Field notes

A running record of what worked and what didn't, in security and in AI governance, from real deployments. Added to over the years. Community contributions welcome under the same license as the framework.

## The rule for what goes here

Share the **lesson**, never the **map**.

Publish:
- the failure mode, the control that fixed it, and why the control is shaped the way it is
- the metric that proved it, where one exists
- anything another practitioner could apply tomorrow

Do not publish:
- client names, client systems, or anything that identifies a client
- network topology, addresses, host names, or target lists
- pricing, pipeline, go-to-market, or anything that reads as a business plan
- credentials, keys, or configuration that is live anywhere

If a note can't be written without the second list, it isn't ready for this repo.

## Format

One file per note, named `YYYY-MM-DD-short-slug.md`, using [TEMPLATE.md](TEMPLATE.md). Date is when the lesson was learned, not when it was written up.

## Index

| Date | Note | One line |
|---|---|---|
| 2026-08-06 | [An agent authenticated as its human](2026-08-06-agent-authenticated-as-its-human.md) | Non-repudiation breaks silently when agents share a person's identity. Fix it in schema, not policy. |
| 2026-09-10 | [Five ways a hosted AI receptionist fails](2026-09-10-hosted-ai-receptionist-failure-modes.md) | Audit the production transcripts, not the demo. What we found and what each finding demands. |
