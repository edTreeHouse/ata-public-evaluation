# ATA Public Evaluation

**Agent Transaction Assurance (ATA)** — public, vendor-neutral, **simulated** evidence examples for delegated authority across multi-agent workflows.

> This repository contains synthetic evaluation artifacts only. It is not a production authorization service, a live agent-platform integration, or independently verified security attestation. The private ATA engineering implementation is **not** published here.

## Four scenarios

| Scenario | Expected decision | Observed in captured sample |
| --- | --- | --- |
| Authorized delegation | ALLOW | ALLOW |
| Out-of-scope action | DENY | DENY |
| Privilege expansion | DENY | DENY |
| Revoked originating authority | DENY | DENY |

- [Complete JSON report](samples/ata-delegation-review.json)
- [Authorized delegation](samples/authorized_delegation.json)
- [Out-of-scope action](samples/out_of_scope_action.json)
- [Privilege expansion](samples/privilege_expansion.json)
- [Revoked authority](samples/revoked_authority.json)
- [Evaluation methodology and limitations](EVALUATION.md)
- [Artifact manifest](manifest.json)

## What the evidence means

The JSON files capture the results of a **standalone illustrative simulation**, with synthetic principals and agents, a fixed evaluation time, local revocation state, and a public example HMAC key. The included `evidence_signature` fields are **not independent attestations**; anyone with the example key could regenerate them. They must not be treated as proof of authentic execution.

The public package enables **inspection of captured results**, not independent re-execution. The implementation remains private pending an intellectual-property and release-scope decision. Source-controlled artifacts do not establish that the reported execution happened.

## Scope and feedback

These artifacts invite architectural review of whether downstream agent actions can be constrained by originating authority, with a traceable allow/deny rationale. They do not prove real identity propagation, connector enforcement, distributed revocation, production key custody, or third-party verification.

For further context see [EVALUATION.md](EVALUATION.md). No vendor-specific or real user information is included.

Copyright © 2026 TreeHouse Consulting Services, LLC. No license is granted for reuse or redistribution beyond rights provided by applicable law.