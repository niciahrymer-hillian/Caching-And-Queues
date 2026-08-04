# Caching-And-Queues

### Redis caching and message queues: cache-aside, invalidation, background jobs, and the failure modes each one hides.

![Chain O](https://img.shields.io/badge/Chain%20O-D97706?style=for-the-badge) [![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue?style=for-the-badge)](LICENSE-GPL) [![License: AGPL v3](https://img.shields.io/badge/License-AGPLv3-blue?style=for-the-badge)](LICENSE-AGPL)

[📖 Lesson Plan](docs/LESSON_PLAN.md) · [🎮 Interactive Tour](docs/interactive/index.html)

<!-- SCREENSHOT PLACEHOLDER: docs/screenshots/overview.png -->

> ⬜ **Scaffold pending.** Directory created to portfolio standard; full content (README, lesson plan, tour + quiz, skeleton code) still to be built. Part of **Chain O — System Design & Architecture**.

## Why This Was Built

Caching and queueing are the two levers you reach for when something is too slow, and both trade
correctness risk for speed. A cache can serve stale data; a queue can drop or duplicate a job. Using them
well means knowing exactly which risk you accepted.

Cache invalidation in particular deserves its reputation. I want to work through the real failure modes —
stampedes when a hot key expires, stale reads after a write, and the thundering herd on a cold start — and
implement queues with the retry and dead-letter handling that production actually requires.

## Why This Matters (Industry Application)

These are foundational backend skills. Nearly every application at scale runs a cache and a job queue,
and the interview questions ("how would you make this faster?") almost always land here. Understanding
idempotent consumers and at-least-once delivery is what separates a working queue from a corrupted one.

## Topics Covered

| Area | What this project covers |
|------|--------------------------|
| Cache-aside | Read-through patterns, TTLs, and warming |
| Invalidation | Stale reads, write-through, and stampede protection |
| Queues | Producers, consumers, and backpressure |
| Delivery guarantees | At-least-once vs exactly-once, and idempotent consumers |
| Retries | Exponential backoff and dead-letter queues |
| Observability | Queue depth, lag, and cache hit rate as health signals |

## How This Connects

Chain O (System Design & Architecture). Supports **URL-Shortener-At-Scale**, **News-Feed-Fanout**, and the background jobs in my Chain G work.

---
Dual licensed — [GPL v3](LICENSE-GPL) and [AGPL v3](LICENSE-AGPL).
