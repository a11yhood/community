# Contributing to A11yhood
Thank you for your interest in contributing to A11yhood. This project exists as a resource to learn about and share open source accessibility technology. We define technology broadly, including everything from knitted objects to 3D printing, laser cutting, and software. Every contribution — whether it's an accessibility solution, code, documentation, design, or lived experience feedback — helps move that mission forward.

This guide covers everything you need to know to contribute effectively.

---

## Table of Contents

- [Who Can Contribute](#who-can-contribute)
- [Types of Contributions](#types-of-contributions)
- [Community Engagement](#community-engagement)
- [Contribution Workflow](#contribution-workflow)
  - [Fork and Clone](#fork-and-clone)
  - [Branching](#branching)
  - [Making Changes](#making-changes)
  - [Commit Messages](#commit-messages)
  - [Pull Requests](#pull-requests)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)
- [Issue Management](#issue-management)
- [Content Style Guide](#content-style-guide)
- [Releases](#releases)

---

## Who Can Contribute

A11yhood welcomes contributors of all skill levels and backgrounds. You do not need to be a developer to contribute meaningfully. We especially value perspectives from:

- Disabled innovators who are creators of, or want to learn about, open source accessibility technology
- Accessibility advocates and researchers
- Developers interested in building tools for social good
- Designers, writers, and documentation contributors

If you're new to open source, this is a great place to start. We'll do our best to support you.

---

## Types of Contributions

| Type | Description |
|------|-------------|
| **Code** | Frontend (React/TypeScript) and backend (Python/FastAPI) features and fixes |
| **Bug reports** | Identifying and documenting issues in the app or documentation |
| **Documentation** | Improving guides, fixing errors, adding clarity |
| **Design** | UI/UX improvements, accessibility reviews of the interface |
| **Accessibility feedback** | Sharing lived experience to help us ask better questions or surface better information |
| **Issue triage** | Helping label, clarify, and prioritize open issues |
| **Meta data Entry** | Help to label, tag, and add accessibility products | 

Not sure where to start? Look for issues tagged `good first issue` in the issue tracker.

---

## Community Engagement

The primary space for A11yhood discussions is **GitHub Issues**. This keeps conversations transparent, searchable, and tied directly to the work.

- **Have a question?** Open an issue with the `question` label.
- **Want to propose something?** Open an issue before starting work (see [Suggesting Features](#suggesting-features)).
- **Found a bug?** Open an issue before submitting a fix (see [Reporting Bugs](#reporting-bugs)).

Before opening a new issue, search existing issues to see if the topic has already been raised.

---

## Contribution Workflow

### Fork and Clone

1. Fork the repository you want to contribute to on GitHub.
2. Clone your fork locally:

```bash
git clone https://github.com/your-username/repo-name.git
cd repo-name
```

3. Add the upstream remote so you can pull in future changes:

```bash
git remote add upstream https://github.com/a11yhood/repo-name.git
```

4. Follow the [Setup Guide](./docs/setup/SETUP.md) to get your local environment running.

### Branching

All work should happen on a feature branch off `main`. Never commit directly to `main`.

Name your branch descriptively based on what you're working on:

```bash
# Format: type/short-description
git checkout -b fix/review-form-validation
git checkout -b feature/college-profile-page
git checkout -b docs/update-setup-guide
git checkout -b chore/update-dependencies
```

Common branch type prefixes:

| Prefix | Use for |
|--------|---------|
| `feature/` | New features |
| `fix/` | Bug fixes |
| `docs/` | Documentation changes |
| `chore/` | Maintenance, dependency updates, config changes |
| `design/` | UI/UX changes without functional changes |

Keep branches focused on a single change. If you find yourself working on multiple unrelated things, split them into separate branches and pull requests.

### Making Changes

Before you start:
- Check that an issue exists for the work you're doing. If not, open one first.
- Comment on the issue to let others know you're working on it — this avoids duplicate effort.
- Pull the latest changes from upstream before branching:

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

While you work:
- Follow the conventions in the [Development Guide](./DEVELOPMENT.md) for the relevant part of the codebase.
- We are still establishing standard checks that must be run before pushing. Help us define these! 
- Keep changes small and focused. Smaller pull requests are easier to review and faster to merge.

### Commit Messages

We don't enforce a strict commit format, but good commit messages make the project history useful. A helpful commit message:

- Describes **what** changed and **why**, not just how
- Uses the present tense ("Add validation for college slug" not "Added validation")
- Is specific enough that someone reading the git log understands the change without opening the diff

```bash
# Good
git commit -m "Add error handling for missing college slug in review submission"
git commit -m "Fix broken link in setup guide"
git commit -m "Update ALLOWED_INSERT_COLUMNS to include new attendance fields"

# Too vague
git commit -m "Fix bug"
git commit -m "Update file"
git commit -m "WIP"
```

For larger changes, use a short subject line with a body:

```bash
git commit -m "Add search page feature flag to env setup docs

NEXT_PUBLIC_SHOW_SEARCH_PAGE was documented in DEVELOPMENT.md
but belongs in SETUP.md alongside the other env vars.
Moved and added inline comment explaining the flag's purpose."
```
### Testing

- **Testing:** 
  - All UI changes must be tested with [Axe DevTools](https://www.deque.com/axe/devtools/). You can test this by running ```npm run test:a11y```
  - We also run a lint check (```npm run lint```)
- **CI/CD:** 
  - PRs will automatically test the same, and fail if these tests do not pass

### Pull Requests

When your branch is ready:

1. Push your branch to your fork:

```bash
git push origin your-branch-name
```

2. Open a pull request against the `main` branch of the upstream repo.

3. Fill out the pull request description:
   - **What does this PR do?** A brief summary of the change.
   - **Why?** Link to the issue this addresses (e.g. `Closes #42`).
   - **How was it tested?** Describe how you verified the change works.
   - **Screenshots** (if applicable) — especially helpful for UI changes.

4. Request a review from a maintainer or another contributor.

**PR checklist before requesting review:**

- [ ] Branch is up to date with `main`
- [ ] No unrelated changes included
- [ ] PR description is filled out

We are currently focusing community input on the **frontend**. In that context, check the following before committing: 
- [ ] Semantic HTML used — native elements preferred over generic `div`/`span`
- [ ] Interactive elements are keyboard accessible
- [ ] Check the accessibility of any pages you change


Pull requests will be reviewed by a maintainer. Be responsive to feedback — if a PR sits without updates for an extended period, it may be closed and reopened when you're ready to continue.

---

## Reporting Bugs

If you find a bug, please open a GitHub Issue in the appropriate repository before submitting a fix:

| Issue type | Repo to open the issue in |
|------------|--------------------------|
| Backend / API bug | [a11yhood/a11yhood-backend](https://github.com/a11yhood/a11yhood-backend/issues) |
| Frontend bug | [a11yhood/a11yhood.github.io](https://github.com/a11yhood/a11yhood.github.io/issues) |
| Accessibility bug | [a11yhood/frontend](https://github.com/a11yhood/a11yhood.github.io/issues) |
| Documentation bug | [a11yhood/community](https://github.com/a11yhood/community/issues) |

A good bug report includes:

- **What you expected to happen**
- **What actually happened**
- **Steps to reproduce** — be as specific as possible
- **Environment** — browser, OS, which repo/page/feature
- **Screenshots or error messages** if relevant

Label your issue with `bug`. A maintainer will triage and confirm before work begins.

---

## Suggesting Features

Have an idea for A11yhood? Open a GitHub Issue in the appropriate repository to start the conversation before building anything:

| Feature type | Repo to open the issue in |
|-------------|--------------------------|
| Backend / API feature | [a11yhood/a11yhood-backend](https://github.com/a11yhood/a11yhood-backend/issues) |
| Frontend feature | [a11yhood/a11yhood.github.io](https://github.com/a11yhood/a11yhood.github.io/issues) |
| Accessibility improvement | [a11yhood/a11yhood.github.io](https://github.com/a11yhood/a11yhood.github.io/issues) |
| Documentation improvement | [a11yhood/community](https://github.com/a11yhood/community/issues) |

Not sure which repo? Open the issue in the frontend repo and a maintainer will move it if needed.

A good feature proposal includes:

- **What problem does this solve?** Connect it to the project's mission where possible.
- **Who does it help?** Be specific about the user or contributor this benefits.
- **What would it look like?** A rough description, mockup, or example is helpful.
- **Alternatives you've considered** — is there a simpler way to solve the same problem?

Label your issue with `enhancement`. Proposals will be discussed before any work is assigned or started.

---

## Issue Management

Issues are the source of truth for all planned work on A11yhood.

| Label | Meaning |
|-------|---------|
| `bug` | Something is broken or behaving incorrectly |
| `enhancement` | A new feature or improvement |
| `documentation` | Changes or additions to docs |
| `good first issue` | A good starting point for new contributors |
| `question` | A question or discussion topic |
| `accessibility` | Related to accessibility of the platform or its content |
| `help wanted` | Maintainers are actively looking for someone to pick this up |

If you'd like to work on an issue, comment on it to claim it. Unassigned issues with no recent activity are fair game.

---

## Content Style Guide

When contributing to documentation or any user-facing text in the project, please follow these conventions.

**Voice and tone:**
- Write in plain, clear language. Avoid jargon where possible.
- Use second person ("you") when addressing the reader.
- Be direct and specific. Vague guidance is harder to follow than no guidance.
- Match the tone of the surrounding content — this project is warm and mission-driven, not corporate.

**Accessibility and identity language:**
- Use both person-first ("person with a disability") and identity-first ("disabled person") language — both are used within the disability community and neither is universally preferred. Follow the lead of the existing content and avoid choosing one exclusively.
- Avoid ableist language (e.g. "blind to," "falls on deaf ears," "crazy," "lame").
- When referring to racial, ethnic, or LGBTQ+ identities, follow current community-preferred terminology. When in doubt, defer to how the community describes itself.

**Formatting:**
- Use code blocks for all commands, file names, and code snippets.
- Use relative links for internal documentation references.
- Keep line lengths readable — wrap long lines in markdown files.'

---

## Releases

We are still defining this aspect of the project:


TODO: A formal release process and versioning conventions will be documented here.
