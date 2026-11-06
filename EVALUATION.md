# Evaluation guide

## Quick review

Open [the consolidated JSON report](samples/ata-delegation-review.json) and examine `scenarios[].decision`, `reason`, `passed`, and `evidence_signature`. Alternatively, open each of the four per-scenario JSON files. These are **captured sample outputs**, not independently authenticated execution records.

| Case | Expected | Rationale |
| --- | --- | --- |
| Authorized delegation | ALLOW | A child reads an approved catalog within the originating authority's delegated scope. |
| Out-of-scope action | DENY | A child tries to purchase when delegated only read access. |
| Privilege expansion | DENY | A child grant attempts to expand permitted resources beyond its parent. |
| Revocation | DENY | The originating grant is revoked before evaluation. |

## Evidence format

Each record contains a synthetic principal, parent-to-child chain, action, resource, decision, reason, fixed evaluation time, and illustrative HMAC signature. `passed` means the simulation's observed decision matched its expected result, **not** that a real connector was blocked.

## Limits and review questions

- No real user identities, real agent platform, external connector, transaction, or production credential.
- The simulation uses a shared example HMAC key and local revocation; signatures are not independently trusted.
- There is no externally witnessed execution, verified publisher signature, production enforcement, or online revocation freshness.
- The implementation is not included in this public evidence-only repository. Thus a visitor can inspect the examples, but cannot independently rerun them from this repository alone.
- The public files are versioned to support review, but do not establish source authenticity or operational security.

Reviewers should ask: who is authorized to issue a grant, where is policy checked immediately before tool execution, how does the child inherit and narrow scope, how is revocation freshness established, and who independently verifies the evidence?

## Publication guidance

Link to the [README](README.md) from the public website. Keep the four-row results summary and a short JSON excerpt in the article. Refer to these as *sample outputs of a simulated policy evaluation*, never as proof of a production integration.
