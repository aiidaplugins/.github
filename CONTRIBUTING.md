# Contributing Guidelines

Welcome to aiidaplugins!
We're excited you're here and want to contribute 🎉.

This page outlines conventions and best practices for contributing across all repositories in the aiidaplugins organisation,
to help the community make the best tools possible.
These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

Thank you for you interest in contributing ✨

## Design Philosophy

There are few high-level principles that this project tries to follow in making
both technical and community decisions. They goals to shoot for, and may not all
be followed perfectly all the time. Here are a few of those principles:

- **Document first** - When deciding whether or not a new feature is needed, first
  consider whether improving documentation could solve the same problem for others.
  New features (and especially new APIs) are costly to develop and maintain. Sometimes
  it's better to show people how to manually do a complex thing via the documentation,
  rather than extending the API. If new features/API are needed, make sure this avenue
  has been exhausted first so the decision is intentional.
- **Standardize developer practices**. We should keep developer/release/community
  practices consistent across all of the EBP repositories. Where possible, share
  infrastructure and documentation between them (like this page!). Keep the same
  level of quality control across all core repositories, regardless of how small
  they are.
- **Keep the semantic document model consistent**. There are a few places where
  markdown syntax / file structure maps on to the structure of a book. The two
  most obviously places this happens are in the Jupyter Book `_toc.yml` file and in
  the underlying Sphinx `toctree` structures. These two models should closely resemble
  one another. Try not to include user-facing structures (e.g., in `_toc.yml` that
  must be translated to a *different* document structure in Sphinx).
- **Release early and often**. We should emphasize smaller, more iterative releases
  over large and complex ones. This keeps our documentation in-line with the latest
  releases and also minimizes the disruption (and subsequent maintenance burden)
  associated with big changes. The [process for creating a release](#releases-and-change-logs)
  is relatively simple and quick, so don't hesitate to release patch versions (or minor
  versions) as appropriate.

## Testing

All packages should contain a test infrastructure, usually automated for PRs and commits *via* [GitHub Actions workflows](https://docs.github.com/en/actions/configuring-and-managing-workflows/configuring-a-workflow).

Testing philosophy:

- Whenever you encounter a bug, add a (failing) test for it. Then fix the bug.
- Whenever you modify or add a feature, write a test for it!
  Writing tests [before writing the actual implementation](http://en.wikipedia.org/wiki/Test_Driven_Development) helps keeping your API clean.
- Make [unit tests](https://en.wikipedia.org/wiki/Software_testing#Testing_levels) as atomic as possible. A unit test should run in the blink of an eye.
- Document why you wrote your test - developers will thank you for it once it fails.

For Python packages, the test infrastructure should be implemented *via* [pytest](https://docs.pytest.org).

## Documentation

A minimal description of the project should be contained in the README.md, then most documentation should generally be contained in a `docs` folder, using [Sphinx](http://www.sphinx-doc.org) as the documentation generator.

## Git Branches

Repositories should use the `main` branch as their primary branch.
This branch should be "protected" on GitHub and require PR reviews and status checks before merging (see [GitHub branch configuration](https://docs.github.com/en/github/administering-a-repository/configuring-protected-branches)).

Additions to the `master` branch should follow these simple concepts:

- Use feature branches for all new features and bug fixes.
- Merge feature branches into the master branch using pull requests.
- Keep a high quality, up-to-date master branch.

It is also advised to name branches by the convention:

- fix/\<issue number\>/\<description\>, e.g. `fix/123/func-error`
- feature/\<description\>, e.g. `feature/new-options`
