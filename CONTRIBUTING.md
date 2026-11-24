# Contributing to XMOS repositories

Pull requests to public XMOS repositories are welcome. This guide applies to every repository in
the XMOS organisation unless a repository provides its own contribution guidance, which takes
precedence.

## Before you start

- For questions and design discussion, use the [XCORE developer forum](https://www.xcore.com).
- For a suspected bug, raise a GitHub issue in the affected repository. Include the XTC Tools
  version, the hardware, the `manifest.txt` from your build directory and a minimal reproduction.
- For issues that need formal tracking, use [XMOS support](https://www.xmos.com/support).

## Branches

- `develop` is the development and integration branch, and the default branch. Target it with
  your pull request.
- `main` (or `master` in older repositories) points at the latest release. XMOS release
  automation advances it. Do not target it, and do not commit to it.
- Make your change on a short-lived branch in your own fork, for example
  `feature/awesome-feature`, and submit it to `develop` through a pull request.

## Pull requests

Make the smallest coherent change, on a separate branch. Do not combine broad formatting,
product-specific changes and a generally useful fix in one pull request.

Do not leave the description blank. Explain:

- why the change is needed;
- what it changes; and
- how it was validated, including the XTC Tools version, hardware and commands used.

Link any related issue, specification or forum discussion. A short description is sufficient for
a trivial change.

A useful pull request normally includes:

- a focused history with meaningful commit messages;
- updates to user documentation and public API comments where behaviour or an API changes;
- tests that fail without the change and pass with it, where practical; and
- a changelog entry when requested by a maintainer (see below).

### Commit history

Temporary commits such as `WIP`, `fixing build` or `address review comments` are fine while you
are developing in your fork. Reword, fix up or squash them before requesting final review. The
commits submitted for merge should form a coherent, reviewable history.

Pull requests with a blank or inadequate description, or with temporary commits still in their
history, are likely to be returned for revision before substantive review.

## Review and automated tests

Automated tests for an external pull request require approval from an XMOS engineer before they
run, so that untrusted code is not executed automatically. A delay before checks start does not
necessarily indicate a failure.

Review and response times are best effort and depend on the repository and maintainer
availability. Review may request changes for compatibility, real-time behaviour, supported
configurations, documentation or test coverage, even when the proposed code works in your
configuration.

XMOS may use AI-assisted tooling to provide an initial review of a pull request. Its comments are
preliminary and do not replace review or approval by an XMOS maintainer.

## Changelog entries

A maintainer may ask you to add or revise an entry in `CHANGELOG.rst`. Not every pull request
needs one: internal-only changes, such as documentation-build maintenance or dependency updates
used only by tests, are not normally recorded.

- Add entries under `UNRELEASED`. Do not assign a future release number.
- Follow the repository's existing format, which is based on
  [Keep a Changelog](https://keepachangelog.com/).
- Start each entry with one of these categories, preferably kept in this order:
  - `ADDED:` for new features.
  - `CHANGED:` for changes to existing functionality.
  - `DEPRECATED:` for functionality planned for removal.
  - `FIXED:` for bug fixes.
  - `REMOVED:` for functionality that has been removed.
- Describe what changes for the component's users, including any action they must take, not
  implementation details or issue titles alone.

## Documentation

Documentation sources live with the code: `README.rst`, the `doc/` directory and comments in
public API headers. Update them together with the code. XMOS's pull-request infrastructure
performs the official documentation build; you are not expected to reproduce it.

## Licence

Each repository identifies the licence that applies to its contents. Check the licence files in
the repository before contributing.
