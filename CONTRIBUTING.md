# Contributing

Thanks for taking the time to consider contributing to an Orlixys project.
This document covers the defaults that apply across the organisation.
Individual repositories may override these rules with their own
`CONTRIBUTING.md`.

---

## Which projects accept contributions?

Orlixys has two categories of products, and they have different rules.

### Open source: Orlixys Optimizer

[Orlixys Optimizer](https://github.com/Orlixys/Orlixys-Optimizer-Source)
is open source under the MIT licence. External contributions are
welcome — see the rest of this document.

### Proprietary: Orbit, Photon

These are paid, closed-source products. The source is not public and
external code contributions are not accepted. Bug reports, feature
proposals and security disclosures are still very welcome through the
channels listed below.

---

## Before you open an issue

1. **Search first.** A quick search of open and closed issues usually
   shows whether the topic has already been raised.
2. **One issue, one topic.** Separate concerns into separate issues so
   they can be triaged independently.
3. **Security issues do not go here.** Anything that could expose users
   to harm goes through the responsible disclosure process described in
   [`SECURITY.md`](./SECURITY.md). Do **not** open public issues for
   vulnerabilities.

## Filing a useful bug report

Include, at minimum:

- The product name and version (visible in `Settings → About` or on the
  release tag)
- What you expected to happen
- What actually happened
- Minimal, deterministic steps to reproduce
- Environment details that matter (Windows version, architecture)
- Logs, screenshots or recordings when relevant

## Proposing a feature

Feature proposals are welcome, but please understand:

- Most projects here are intentionally small and opinionated. "It would
  be nice if it also did X" is usually not enough — explain the
  underlying problem you're trying to solve.
- For all Orlixys products: features that require telemetry, persistent
  administrator privileges, or non-anonymous user identifiers will not be
  accepted. These are non-negotiable design constraints.

---

## Pull requests (Optimizer only)

When you're ready to contribute code to Orlixys Optimizer:

1. **Open an issue first** for anything larger than a typo. Aligning on
   approach before code saves everyone time.
2. **One logical change per pull request.** Smaller PRs are easier to
   review, easier to revert and easier to merge.
3. **Write a clear commit history.** Squash noise commits before opening
   the PR. Commit subjects in imperative mood ("add", "fix", "remove")
   and under ~72 characters.
4. **Match the existing style.** Formatting, linting and naming
   conventions should follow whatever the repository already does. For
   Optimizer specifically: C# code follows the conventions enforced by
   the project's `.editorconfig`.
5. **Include tests** where the project has them, and update
   documentation in the same PR.
6. **Sign-off your work.** By opening a pull request you confirm that
   you wrote the code yourself or have the right to contribute it under
   the project's licence.

### Signed commits (recommended, not required)

If you can sign your commits with GPG or SSH, please do — it makes the
audit trail cleaner. It is not a hard requirement for external
contributors.

## Review process

- All pull requests are reviewed manually.
- Response times are best-effort. Orlixys is a one-person operation.
- Feedback is meant for the code, not the contributor.

---

## Code of conduct in two lines

Be technical. Be respectful. Anything else gets the issue or PR closed
without further discussion.

## Contact

- General: **support@orlixys.com**
- Security: see [`SECURITY.md`](./SECURITY.md)
