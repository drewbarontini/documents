Bash Project Setup
==================

Have you ever needed to run some command, or commands, when `cd`-ing into a particular project? Well, there's a way to do this in Bash by hooking into the `PROMPT_COMMAND` variable.

1. PROMPT_COMMAND
-----------------

In your `.bash_profile`, add this:

```bash
export DISPATCHED=0
export PROMPT_COMMAND="${PROMPT_COMMAND:+$PROMPT_COMMAND ;} dispatch"
```

2. dispatch Function
--------------------

In your `.bash_profile`, or wherever you keep your Bash functions, add this:

```bash
# ----------------------------------------------------
#   Dispatch
#   -> Check if project has setup function and run it
# ----------------------------------------------------
#
# Usage: `dispatch`
#

function dispatch() {
  local path=$(pwd)
  local project=$(basename $path)

  if [ "$DISPATCHED" == 0 ]; then
    if type -t "$project"_setup | grep -i function > /dev/null; then
      "$project"_setup
      DISPATCHED=1
    fi
  fi
}
```

3. Project-specific Function
----------------------------

In your local dotfiles, or just on your machine somewhere, add a function that is named the same as the directory for the project. For example, `my-project` would need a function called `my-project_setup`.


```bash
function my-project_setup() {
  # Do something when `cd`-ing into the project.
}
```
