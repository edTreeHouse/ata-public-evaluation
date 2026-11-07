# Agent Transaction Assurance (ATA)

**Verifiable authority across multi-agent systems.**

As AI agents collaborate and act on behalf of people and organizations, a critical question emerges: **How do we know that a downstream action is still authorized by the person who initiated it?**

A service may have the technical ability to complete a transaction without having the authority to do so on a particular user's behalf. When work passes from one agent to another, that distinction becomes harder to preserve.

ATA explores an approach to connecting **originating authority, delegated permissions, and the actions ultimately performed**—so that authority is not silently expanded, reused, or treated as valid after it has been withdrawn.

## From intention to action

ATA is designed around four principles:

- **Authority originates with the user.** An agent's access to a tool is not, by itself, permission to use it for every purpose.
- **Delegation preserves boundaries.** Each downstream agent should act only within the authority it received, without expanding its scope.
- **Authorization matters at execution.** The authority behind a request should still be valid when an action is carried out—not merely when it was first proposed.
- **Decisions should be explainable.** A trustworthy system should make it possible to examine what was authorized, what was requested, and why an action proceeded or was denied.

## Explore the scenarios

The illustrative examples examine two connected questions: **Was the agent authorized?** And **was that authority respected when it acted?**

| Scenario | What it illustrates |
| --- | --- |
| Authorized delegation | A downstream agent operates within the user's intended permissions. |
| Out-of-scope action | Access to a capable service does not authorize an unrelated action. |
| Privilege expansion | Delegation cannot grant broader authority than the originating permission. |
| Revoked authority | Permission withdrawn by the originator should no longer authorize an action. |
| Authorized execution | An action proceeds when its delegated authority remains valid. |
| Scope violation at execution | A downstream action is refused when it exceeds the user's authorization. |
| Repeated transaction | One authorized action does not automatically authorize repeating it. |
| Revocation before execution | An action should not proceed if its authority is withdrawn before it takes effect. |

Explore the [original illustrative delegation examples](samples/ata-delegation-review.json) and the [additional execution scenarios](samples/execution-enforcement-scenarios.json).

## Why it matters

In multi-agent systems, identity answers **who or what performed an action**. ATA asks a different question: **Under whose authority, and within which limits, was that action permitted?**

That distinction matters wherever agents can interact with business systems, financial workflows, healthcare environments, or other services in which technical access and legitimate authorization are not the same thing.

ATA's objective is to make delegated authority a meaningful part of execution and accountability—not merely a statement recorded after an action has occurred.

## About these examples

These public examples are **synthetic illustrations of ATA's intended behavior**, not evidence of a deployed production authorization service or independent security certification. The original delegation files contain captured simulated decisions; the additional execution files describe expected outcomes associated with private development tests. They are not interchangeable forms of evidence.

For methodology, evidence qualifications, and technical limitations, see the [evaluation guide](EVALUATION.md). The private implementation is not included in this repository.

Copyright © 2026 TreeHouse Consulting Services, LLC. No license is granted for reuse or redistribution beyond rights provided by applicable law.
