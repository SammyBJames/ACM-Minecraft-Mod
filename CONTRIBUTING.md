# Contributing Guidelines

Thanks for wanting to contribute! This project exists so students can practice
contributing to open source.

Everyone taking part is expected to follow the
[Code of Conduct](CODE_OF_CONDUCT.md).

## Contents

- [Ways to contribute](#ways-to-contribute)
- [The contribution workflow](#the-contribution-workflow)
- [Your first contribution: add your name](#your-first-contribution-add-your-name)
- [Development setup](#development-setup)
- [Project conventions](#project-conventions)
- [What happens in review](#what-happens-in-review)
- [Getting help](#getting-help)

## Ways to contribute

- **Add your name** to the contributors list. Start here if you have never
  opened a pull request before.
- **Report a bug** with the bug report issue template.
- **Suggest a feature** with the feature request issue template.
- **Work on an open issue.** Browse the
  [issue list](https://github.com/Scott-Jeppson/ACM-Minecraft-Mod/issues) and
  look for the `good first issue` and `help wanted` labels.
- **Improve the documentation.** Clarifying, improving, or adding new documentation are real contributions. 

## The contribution workflow

Every change follows these same steps. There's a walkthrough below for first-time contributors.

1. **Find or open an issue** that describes the change. Leave a comment saying you would like to work on it and wait for a maintainer to assign you, so two people aren't stepping on each others toes.
2. **Create (or sync) a fork** so you start from the latest code.
3. **Create a branch** in your fork with a short descriptive name.
4. **Make the change**, keeping it focused on the one issue.
5. **Test it** (see [Development setup](#development-setup)).
6. **Commit and push** to your fork.
7. **Open a pull request** against `master` on this repo and fill in the template.
8. **Work through review** until a maintainer merges it.

## Your first contribution: add your name

This walkthrough takes you through the standard open source loop: issue, fork,
branch, commit, pull request, review, merge.

Replace `<your-username>` with your GitHub username everywhere below.

### 1. Open an issue

Go to
[New issue](https://github.com/Scott-Jeppson/ACM-Minecraft-Mod/issues/new/choose)
and pick **First contribution: add my name**. Fill in the template and submit the issue.
Note the issue number, you'll need it later.

On most projects you open or claim an issue *before* writing code so the
maintainers can agree on the change and nobody duplicates work.

### 2. Fork the repository

Click **Fork** at the top right of the
[repository page](https://github.com/Scott-Jeppson/ACM-Minecraft-Mod). This
creates your own copy on GitHub that you are allowed to push to.

### 3. Clone your fork

Using **Git**:
```bash
git clone https://github.com/<your-username>/ACM-Minecraft-Mod.git
cd ACM-Minecraft-Mod
git remote add upstream https://github.com/Scott-Jeppson/ACM-Minecraft-Mod.git
```

Using **GitHub CLI**:
```bash
gh repo clone ACM-Minecraft-Mod
```

You now have your fork on your local machine with two remotes: `origin` is your fork, and `upstream` is the
original project.

### 4. Create a branch

```bash
git switch -c <branch-name>
```

Never commit directly to `master`. One branch per change keeps your work separate and easy to update.

Use a branch name that represents your change and matches the repo format.

### 5. Add your contributor file

Copy the template to a new file named after your GitHub username:

```bash
cp contributors/_TEMPLATE.md contributors/<your-username>.md
```

Open the new file in an editor and fill it in. See
[contributors/README.md](contributors/README.md) for the rules. Do not edit
`_TEMPLATE.md` or anyone else's file.

### 6. Commit and push

```bash
git add contributors/<your-username>.md
git commit -m "Add <your-username> to the contributors list"
git push
```

### 7. Open a pull request

Open your fork on GitHub. A banner offers **Compare & pull request** for the
branch you just pushed, click it. Check that the base repository is
`Scott-Jeppson/ACM-Minecraft-Mod` and the base branch is `master`.

Fill in the pull request template. In the **Linked issue** section,
link your issue number from step 1 so the issue closes
automatically when the pull request is merged.

### 8. Respond to review

A maintainer will review your pull request. If they ask for changes, edit the
file, create a new commit, and push to the same branch. The pull request will update on its
own. You don't need to open a new one.

### 9. Wait for maintainers to merge your change

A maintainer will merge your change once they are happy with its final state.

## Development setup

The [README](README.md) lists the requirements and
explains how to build and run the mod. The two commands you will use most:

```bash
gradle build       # compile the mod and produce the JAR in build/libs/
gradle runClient   # launch a development Minecraft client with the mod loaded
```

The project has no automated tests yet, so test gameplay changes by hand in
the development client and describe what you checked in your pull request.

## Project conventions

### Issues

- Ensure your issue gives enough detail to reliably reproduce the issue or clearly outline the suggested improvement.

### Branches

Use kebab case: lowercase words separated by hyphens that describe the change, for
example `add-dolphin-item` or `fix-beacon-range`.

### Commits

- Start with a short summary line that says what the commit does, for example
  `Add Saturation as a tier 3 beacon effect`.
- Keep each commit to one logical change.

### Code

- Match the style of the surrounding code: four-space indentation, one class
  per file, packages under `com.acm`.
- Keep client-only code (renderers, screens, key bindings) out of the common
  entrypoint; register it from `AcmClient`.
- Prefix mixin handler methods with `acm$`, as in
  `BeaconBlockEntityMixin`, so they cannot collide with other mods.
- Put models, translations, and other assets under
  `src/main/resources/assets/acm`.

### Documentation

Make sure to update documentation along with your changes!
If your change adds or alters gameplay, update the **Current gameplay
changes** section of the [README](README.md) in the same pull request. If you
add files or directories, update the **Repository layout** section too.

### Pull requests

- Link the issue being addressed with `Closes #<number>`.
- One issue per pull request. Small pull requests get reviewed faster.
- Do not include unrelated formatting changes or local-only files such as IDE settings and build output.
- Any request that doesn't include "pineapple" at the end of the description will be automatically closed.
- Ensure your PR passes the automated CI checks, maintainers will wait for these to pass before reviewing your change

## Code review

A maintainer reads your change and may leave comments, ask questions, or request changes.
Review comments are about the code, not about you;
going back and forth a few times is normal on any project. If you have not
heard anything after a few days, it is fine to leave a polite comment on the
pull request asking for a review. A maintainer will merge your change once they deem it acceptable and complete.

## Getting help

- Ask in
  [Discussions](https://github.com/Scott-Jeppson/ACM-Minecraft-Mod/discussions)
  for questions about the project in general or the contribution process.
- Comment on the issue or pull request you are working on if you are stuck on
  something specific.

Don't be shy asking questions.
