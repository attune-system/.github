# Organization governance

## Scope and responsibilities

This policy covers `attune-system`. The organization currently has one active
maintainer and uses GitHub Free. Repository-specific architecture, validation,
and authorization rules continue to apply.

The public `.github` repository provides shared community-health files.
Repository-local files override the corresponding defaults. Rulesets, dependency
update configuration, and workflows do not inherit from this repository.

## Change and release policy

- Prepare changes through pull requests and run applicable validation before
  merging. Disclose incomplete work and validation gaps on draft changes.
- Require zero independent approvals while there is only one maintainer.
  Independent human review becomes an enforceable requirement when there is
  enough maintainer capacity; do not simulate it with bot approvals.
- Keep release publication separate from ordinary validation. Publishing jobs
  should receive only the credentials and write permissions they need.
- Publish from a recorded source revision with passing applicable checks.
  Preserve existing artifact signatures and add verifiable provenance as the
  publishing workflows are hardened.
- Treat emergency bypasses as exceptions: record the reason, affected revision,
  validation gaps, and follow-up. Routine synchronization should not bypass CI.

These describe the intended operating policy. They do not assert that every
repository already has matching GitHub enforcement. Roll out required checks
only after ordinary and automated PRs demonstrably run the required validation.

## Security maintenance

Use the shared security policy for private vulnerability reporting and disclosure.
Review new security alerts weekly and access permissions and accepted exceptions
monthly. An accepted security exception needs an owner, rationale, affected
scope, mitigation if applicable, and a review date. Existing alert backlogs must
be triaged; neither a scanner score nor an ignored advisory proves safety.

Group routine dependency updates to limit maintenance noise. Security updates
remain separate from routine updates. Dependency-update PRs require applicable
checks and maintainer assessment; no automatic merging is established by this
policy.

## Repository inventory

Inventory checked on 2026-11-17. This is a classification, not a compliance report.
Release destinations, automation credentials, and required-check identities need
to be recorded as each repository's workflow is audited.

| Repository | Purpose | Visibility and treatment |
| --- | --- | --- |
| `.github` | Shared policies and organization profile | Public; organization defaults |
| `attune` | Platform, CLI, web UI, and core pack | Public; platform validation |
| `python-attune-sdk` | Python SDK | Public; SDK validation and publishing |
| `js-attune-sdk` | JavaScript/TypeScript SDK | Public; SDK validation and publishing |
| `java-attune-sdk` | Java SDK | Public; SDK validation and publishing |
| `attune-docs-site` | Public documentation | Public; site validation and publishing |
| `attune-site` | Public website source | Private; Free-plan enforcement exception |
| `attune-charts` | Helm charts | Public; deployment validation |
| `attune-docker` | Compose deployment | Public; deployment validation |
| `index` | Standard pack index | Public; index integrity and synchronization |
| `agent-skills` | Agent skills | Public; skill validation |
| `homebrew-attune-client-tap` | Homebrew packaging | Public; package validation |
| `aur-attune-bin` | Arch Linux packaging | Public; package validation |
| `choco-attune-client` | Chocolatey packaging | Public; package validation and publishing |
| `snjsze4ibd` | Maven namespace confirmation | Public and empty; verify purpose before changes |

## Staged enforcement and exceptions

GitHub Free supports repository rulesets on public repositories. Maintain shared
definitions and apply them per repository; organization-wide rulesets require
a paid plan.

Before requiring PR-only updates, replace direct synchronization pushes with
validated PRs and confirm bot-created PRs trigger CI. Add a reliable final CI gate
before making it required. Preserve force-push/deletion protection and keep
review requirements feasible for a single maintainer.

The private `attune-site` repository cannot use the same ruleset protections on
the current plan. Keep its local/CI validation and dependency monitoring, and
revisit paid protections when funding allows. Changing visibility is a separate
decision requiring review.

The empty Maven confirmation repository is excluded from the initial settings
rollout. Do not add commits, archive it, or remove it without checking whether
namespace verification still depends on it.

Account recovery and organization-wide 2FA enforcement require the maintainer to
verify their recovery methods. Do not store recovery codes in these repositories.
