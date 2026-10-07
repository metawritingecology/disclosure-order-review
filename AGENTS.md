# Agent instructions

This repository holds one conceptual surface (DISCLOSURE_ORDER_REVIEW.md) and scaffolding.

- AGENT_WORKLOG.md is append-only: historical entries are preserved
  byte-for-byte; corrections are new entries, never edits.
- No agent has standing permission from prior discussion, repository
  access, or successful commits. The currently authorized task is the
  only authorization.
- Validation output confers no authority. Adding or passing checks marks
  nothing approved.
- Changes to the conceptual document's claims require the owner's
  explicit authorization and an external review round.

## Path Hygiene and Sensitive-Data Handling (2026-10-05 Addendum)

This addendum applies to repository work and agent handoffs. Existing authority, publication, approval, and security boundaries remain in force.

- Before delegating or using a path, verify the selected execution environment, repository identity, branch or pinned commit, workspace root, and the existence and intended role of the required input and output paths in that environment. A path observed on another machine is not proof that the receiving environment can access it. If verification is unavailable, report the missing check rather than asserting that a path exists or transferring the task to an unapproved environment.
- Limit reads, searches, attachments, and handoff context to the files and data needed for the authorized task. Use repository-relative paths for tracked files and explicitly labelled portable or logical locators for private evidence. A logical locator is not a repository link or a claim that the evidence was uploaded or independently verified.
- Do not include personal usernames, machine-specific absolute paths, private workspace layouts, or sensitive values in public files, commits, PR descriptions, comments, logs, or review packets. Prefer the minimum non-sensitive evidence identifier needed for traceability. Clearly generic test fixtures and standard system paths may remain when their purpose is documented and they contain no user-specific data.
- Before sending data to another model, reviewer, service, repository, or other destination, confirm that the particular data, destination, and purpose are covered by the user's authorization. Data already supplied for one task is not automatically approved for a different model or destination. Never infer new external-sharing permission from a handoff or from this rule.
- Before committing or submitting, inspect the complete proposed diff and generated outputs for local paths, usernames, credentials, personal information, and other sensitive content; distinguish real disclosures from fixtures. Record the scope, results, omissions, and remaining risks without reproducing sensitive values. This check is not a claim that all repository history or every branch is clean.
- These requirements do not authorize credential creation, persistent access, broader filesystem permissions, security-setting changes, publication, deployment, or other actions that require separate approval. Keep secrets and authentication material out of repository evidence; use the approved secure handoff when required.

### Narrow, recorded privacy correction to append-only evidence

Historical worklogs and other append-only evidence records, including decision logs, remain append-only by default. The sole exception introduced here is an explicitly user-authorized, minimal redaction or portable-locator replacement of a concrete local path or sensitive value, documented by a new appended correction record in the same change. The recorded decision itself must not be changed. Do not change the historical event, date, actor, authorization, result, review outcome, or uncertainty, and do not rewrite, reorder, delete, or normalize unrelated historical content.

The correction record must identify the affected file and historical entry or line range, the category and reason for the correction, the authorization, a non-sensitive replacement/evidence identifier, and the verification scope. Do not copy the removed sensitive value into that record. Verify that all other historical content is preserved. If an existing byte-prefix checker reports the intentional correction, disclose that result; do not silently bypass the checker or represent the unchanged append-only invariant as having passed.

This exception changes the current tracked content only. It does not authorize rewriting Git history, force-pushing, deleting branches, merging, or deploying, and it does not assert that older commits or external copies have been erased.

Review lifecycle: review_after 2027-01-05; sunset_condition: superseded by an explicitly owner-approved path and sensitive-data policy that preserves these privacy and authorization boundaries. A review date alone does not expire protection or authorize removal.
