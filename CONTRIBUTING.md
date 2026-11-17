# Contributing to Attune

Attune is a pre-production open-source project with one active maintainer.
Contributions to code, documentation, testing, and packaging are welcome.

## Choose the owning repository

Open changes in the repository that owns the affected code or documentation.
For larger changes, discuss the intended behavior and scope with the maintainer
before investing in implementation. Follow that repository's contribution,
architecture, and validation instructions; repository-specific guidance takes
precedence over these organization defaults.

Report security issues through the
[private reporting channel](https://github.com/attune-system/.github/blob/main/SECURITY.md),
not a public issue or pull request.

## Prepare a pull request

- Keep the change focused and explain the problem and resulting behavior.
- Include relevant tests or explain why existing validation is sufficient.
- Report checks actually run, their results, and any remaining gaps. Do not
  describe skipped, failing, or unavailable checks as passing.
- Keep API clients, documentation, and other affected contracts consistent.
- Never include credentials, private keys, tokens, or sensitive production data.

Draft pull requests may contain incomplete work when that status is explicit.
Passing CI and applicable repository checks are required before work is ready
to merge. Independent approvals are not required while the project has only one
active maintainer; automated review does not constitute independent human review.

## Dependency and release changes

Dependency updates must satisfy the owning repository's validation and security
policy. Publishing, merging, and deploying are separate from preparing a change;
follow the repository's authorization and release procedures.
