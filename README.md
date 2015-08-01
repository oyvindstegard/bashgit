# Simple colored git branch status in Bash prompt.
Version: 1.0

Requires Git, Bash and terminal with color support. This file should be source'd
from `~/.bashrc` or similar *after* your initial `PS1` prompt setup. It may not
be able to inject status before your prompt suffix (`$ `, etc), depending on use
of colors and non-standard formatting. In that case, the git status is simply
appended. Note that altering `PS1` *after* enabling this code will currently not
work properly without unsetting `_BASHGIT_ORIG` first.

Minimum required git version is **1.7.2**.

Tries to be reasonably efficient with few forks and use of Bash builtins where
possible.

Displays color coded name of current branch (or best description if detached
HEAD or tag), and optionally number of commits ahead/behind a remote tracking
branch. Green for clean, red for uncomitted changes etc., yellow for work tree
modifications and/or unknowns. Does branch name truncation to keep prompt from
growing too much.

## The following git config options are understood by bashgit:
- `bashgit.showremote`    (`boolean`) show remote ahead/behind status in prompt or not
- `bashgit.branchlimit`   (`integer`) max branch name length in prompt
- `bashgit.untracked`     (`boolean`) include untracked files as dirty state, false
   gives better performance with large repositories.

## Screenshot
![Screenshot](http://stegard.net/dl/bashgitdemo.png)
