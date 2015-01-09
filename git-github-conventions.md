Git/GitHub Conventions
======================

Commits
-------

There are few good methods for handling how/when you commit.

1. Break your commits down into smaller chunks
2. Make sure each commit contains only necessary, related changes

### Interactive Staging

If you do make several, unrelated changes, use [Git's Interactive Staging](http://git-scm.com/book/en/Git-Tools-Interactive-Staging).

```bash
git add -p file.html
```

Then, you can split and stage multiple parts of the file.

### Interactive Rebase

Conversely, if you make separate commits that are related to the same thing, you can use [Git's Interactive Rebase](http://git-scm.com/book/en/Git-Tools-Rewriting-History).

```bash
git rebase -i HEAD~2
```

It looks weird, but just know that the final number reflects the number of commits from the top of the `HEAD` that you want to rebase. In this instance, we want to rebase the last two commits, so we type `HEAD~2`.

Now you'll be able to squash your last two commits together, and edit the single commit message.

Commit Messages
---------------

Read these articles:

- [A Note About Git Commit Messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
- [5 Useful Tips For A Better Commit Message](http://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message)
- [How to Write a Git Commit Message](http://chris.beams.io/posts/git-commit/)

I'm not a fan of the single-line commit command.

```bash
git commit -a -m 'My commit message'
```

Why? Because it encourages single-line, unnecessarily terse commit messages. Simply do the following:

```bash
git add file.html
git commit
```

If you've set your editor via `git config --global core.editor`, then it will open up when you type `git commit` so that you can write your nice commit message there. If you haven't set this command, run it like so: 

```bash
git config --global core.editor vim
```

**Note**: Instead of `vim`, set yours to `subl`, `atom`, etc. Make sure this command is properly set up, though!

### Verbose

Rather than just doing `git commit`, I like to run `git commit --verbose`, which will print out the diff of your changes below your commit message writing area. This is nice because you can write, scroll down and look at your changes, go back and write, etc.

### Writing Good Commit Messages

```
Subject line (50 chars.)

Additional explanation and summary here, if necessary. (72 chars.)

- Use hyphens to write out a list
- That will break down the commit
- If necessary

Refs: #12 (Use this format for referencing a GitHub Issue)
```

The three parts of a well-structured commit message.

1. Subject
2. Description (optional)
3. References (optional)

#### Subject

- Capitalize
- Use the imperative (`Fix`, not `Fixes` or `Fixed`)
- **DO NOT** end the line with a period
- Limit to 50 characters

```
Fix the spacing on the sign-in form
```

Treat it as you would a subject line in an email. If it accurately describes the commit, leave it at that. If not, use a description, as discussed in the next section.

#### Description

- Separate from subject line with a newline
- Wrap at 72 characters
- Explain _what_ and _why_ vs. _how_
- Use bullet points, if necessary

```
Fix the spacing on the sign-in form

This is where you would provide additional explanation on the
what and why. Also, use bullet points, if you'd like:

- Here is a bullet point
- These can be helpful
```

#### References

When using an issue tracker (like GitHub), put references at the bottom with a preceding newline.

```
Fix the spacing on the sign-in form

This is where you would provide additional explanation on the
what and why. Also, use bullet points, if you'd like:

- Here is a bullet point
- These can be helpful

Refs: #245
```

Feature Branches
----------------

Feature branches are branches that are created off of `master`, and they are, as you'd expect, branches that you use to work on a particular feature that will be merged into `master`. The creation looks something like this:

```bash
git checkout -b feature_branch_name
```

### Naming

- Use underscores, not hypens (Why? Hyphens are good for purposeful delineation of multiple words)
- Make it descriptive (e.g. `fix_user_bar`, `refactor_widget_module`)

Pull Requests
-------------

Pull Requests are great on GitHub, because they allow you to view changes and conversations in a centralized location. Additionally, they are great for code reviews.

Like your commit messages, your Pull Request description should do a thorough job:

- Explaining *what* your feature branch changes
- Eplaining *why* your feature branch is making these changes
- Showing relevant screenshots, if it's a design change
- Explaining the status of the feature branch
- Clueing in the right people on the team

Essentially, **Who**, **What**, **Why**, and **When**.
