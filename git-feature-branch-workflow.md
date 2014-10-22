Git Feature Branch Workflow
===========================

1. Create the `git_remote_tracking_branch` function.

```shell
# ----------------------------------------------------
#   Remote Tracking Branch
#   -> Creates a new branch and pushes that branch to remote
# ----------------------------------------------------
#
# $1 - the branch name
#
# Usage: `git_remote_tracking_branch fix_sign_up_form_styles`
#

function git_remote_tracking_branch() {
  git checkout -b $1 && git push -u origin $1
}
```

2. Install [Hub](https://github.com/github/hub).

Workflow
--------

- Check out `master`.
- Run `git_remote_tracking_branch BRANCH_NAME`.
- Make your changes, commit, and push.
- When ready, create Pull Request with `hub pull-request`, entering the title/description and save/quit the file.

Now, you'll have your Pull Request opened for your feature branch!
