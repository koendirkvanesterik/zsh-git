# zsh-git plugin

**Note:** This code is blatantly copied from [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh/). I switched to a more lightweight zsh setup and lost the benefit of Oh My Zsh's git aliases. This repository resolves that issue. I'll be happy to learn a better solution, because this does feel a bit sketchy.

Various aliases and functions for git in zsh.

To use them - plug `koendirkvanesterik/zsh-git` in the zap configuration of your zshrc file:

```zsh
plug "koendirkvanesterik/zsh-git"
```

## Aliases

| Alias                | Command                                                                                                                                                                                  |
| :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| g                    | git                                                                                                                                                                                      |
| ga                   | git add                                                                                                                                                                                  |
| gaa                  | git add --all                                                                                                                                                                            |
| gapa                 | git add --patch                                                                                                                                                                          |
| gau                  | git add --update                                                                                                                                                                         |
| gav                  | git add --verbose                                                                                                                                                                        |
| gap                  | git apply                                                                                                                                                                                |
| gapt                 | git apply --3way                                                                                                                                                                         |
| gb                   | git branch                                                                                                                                                                               |
| gba                  | git branch --all                                                                                                                                                                         |
| gbd                  | git branch --delete                                                                                                                                                                      |
| gbda                 | git branch --no-color --merged \| grep -vE "^([+*]\|\s*(<span>$</span>(git_main_branch)\|<span>$</span>(git_develop_branch))\s*<span>$</span>)" \| xargs git branch --delete 2>/dev/null |
| gbD                  | git branch --delete --force                                                                                                                                                              |
| gbg                  | git branch -vv | grep ": gone\]"                                                                                                                                                         |
| gbgd                 | local res=$(git branch -vv | grep ": gone\]" | awk '{print $1}') && [[ $res ]] && echo $res | xargs git branch -d                                                                        |
| gbgD                 | local res=$(git branch -vv | grep ": gone\]" | awk '{print $1}') && [[ $res ]] && echo $res | xargs git branch -D                                                                        |
| gbl                  | git blame -b -w                                                                                                                                                                          |
| gbnm                 | git branch --no-merged                                                                                                                                                                   |
| gbr                  | git branch --remote                                                                                                                                                                      |
| gbs                  | git bisect                                                                                                                                                                               |
| gbsb                 | git bisect bad                                                                                                                                                                           |
| gbsg                 | git bisect good                                                                                                                                                                          |
| gbsr                 | git bisect reset                                                                                                                                                                         |
| gbss                 | git bisect start                                                                                                                                                                         |
| gc                   | git commit --verbose                                                                                                                                                                     |
| gc!                  | git commit --verbose --amend                                                                                                                                                             |
| gcn!                 | git commit --verbose --no-edit --amend                                                                                                                                                   |
| gca                  | git commit --verbose --all                                                                                                                                                               |
| gca!                 | git commit --verbose --all --amend                                                                                                                                                       |
| gcan!                | git commit --verbose --all --no-edit --amend                                                                                                                                             |
| gcans!               | git commit --verbose --all --signoff --no-edit --amend                                                                                                                                   |
| gcam                 | git commit --all --message                                                                                                                                                               |
| gcas                 | git commit --all --signoff                                                                                                                                                               |
| gcasm                | git commit --all --signoff --message                                                                                                                                                     |
| gcsm                 | git commit --signoff --message                                                                                                                                                           |
| gcb                  | git checkout -b                                                                                                                                                                          |
| gcf                  | git config --list                                                                                                                                                                        |
| gcl                  | git clone --recurse-submodules                                                                                                                                                           |
| gccd                 | git clone --recurse-submodules "<span>$</span>@" && cd "<span>$</span>(basename <span>$</span>\_ .git)"                                                                                  |
| gclean               | git clean --interactive -d                                                                                                                                                               |
| gpristine            | git reset --hard && git clean -dffx                                                                                                                                                      |
| gcm                  | git checkout $(git_main_branch)                                                                                                                                                          |
| gcd                  | git checkout $(git_develop_branch)                                                                                                                                                       |
| gcmsg                | git commit --message                                                                                                                                                                     |
| gco                  | git checkout                                                                                                                                                                             |
| gcor                 | git checkout --recurse-submodules                                                                                                                                                        |
| gcount               | git shortlog --summary -n                                                                                                                                                                |
| gcp                  | git cherry-pick                                                                                                                                                                          |
| gcpa                 | git cherry-pick --abort                                                                                                                                                                  |
| gcpc                 | git cherry-pick --continue                                                                                                                                                               |
| gcs                  | git commit -S                                                                                                                                                                            |
| gcss                 | git commit -S -s                                                                                                                                                                         |
| gcssm                | git commit -S -s -m                                                                                                                                                                      |
| gd                   | git diff                                                                                                                                                                                 |
| gdca                 | git diff --cached                                                                                                                                                                        |
| gdcw                 | git diff --cached --word-diff                                                                                                                                                            |
| gdct                 | git describe --tags $(git rev-list --tags --max-count=1)                                                                                                                                 |
| gds                  | git diff --staged                                                                                                                                                                        |
| gdt                  | git diff-tree --no-commit-id --name-only -r                                                                                                                                              |
| gdnolock             | git diff $@ ":(exclude)package-lock.json" ":(exclude)\*.lock"                                                                                                                            |
| gdup                 | git diff @{upstream}                                                                                                                                                                     |
| gdv                  | git diff -w $@ \| view -                                                                                                                                                                 |
| gdw                  | git diff --word-diff                                                                                                                                                                     |
| gf                   | git fetch                                                                                                                                                                                |
| gfa                  | git fetch --all --prune                                                                                                                                                                  |
| gfg                  | git ls-files \| grep                                                                                                                                                                     |
| gfo                  | git fetch origin                                                                                                                                                                         |
| gg                   | git gui citool                                                                                                                                                                           |
| gga                  | git gui citool --amend                                                                                                                                                                   |
| ggf                  | git push --force origin $(current_branch)                                                                                                                                                |
| ggfl                 | git push --force-with-lease origin $(current_branch)                                                                                                                                     |
| ggl                  | git pull origin $(current_branch)                                                                                                                                                        |
| ggp                  | git push origin $(current_branch)                                                                                                                                                        |
| ggpnp                | ggl && ggp                                                                                                                                                                               |
| ggpull               | git pull origin "$(git_current_branch)"                                                                                                                                                  |
| ggpur                | ggu                                                                                                                                                                                      |
| ggpush               | git push origin "$(git_current_branch)"                                                                                                                                                  |
| ggsup                | git branch --set-upstream-to=origin/$(git_current_branch)                                                                                                                                |
| ggu                  | git pull --rebase origin $(current_branch)                                                                                                                                               |
| gpsup                | git push --set-upstream origin $(git_current_branch)                                                                                                                                     |
| gpsupf               | git push --set-upstream origin $(git_current_branch) --force-with-lease --force-if-includes (git version >= 2.30)                                                                        |
| gpsupf               | git push --set-upstream origin $(git_current_branch) --force-with-lease (git version < 2.30)                                                                                             |
| ghh                  | git help                                                                                                                                                                                 |
| gignore              | git update-index --assume-unchanged                                                                                                                                                      |
| gignored             | git ls-files -v \| grep "^[[:lower:]]"                                                                                                                                                   |
| git-svn-dcommit-push | git svn dcommit && git push github $(git_main_branch):svntrunk                                                                                                                           |
| gk                   | gitk --all --branches &!                                                                                                                                                                 |
| gke                  | gitk --all $(git log --walk-reflogs --pretty=%h) &!                                                                                                                                      |
| gl                   | git pull                                                                                                                                                                                 |
| glg                  | git log --stat                                                                                                                                                                           |
| glgp                 | git log --stat --patch                                                                                                                                                                   |
| glgg                 | git log --graph                                                                                                                                                                          |
| glgga                | git log --graph --decorate --all                                                                                                                                                         |
| glgm                 | git log --graph --max-count=10                                                                                                                                                           |
| glo                  | git log --oneline --decorate                                                                                                                                                             |
| glol                 | git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset'                                                                                   |
| glols                | git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset' --stat                                                                            |
| glod                 | git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset'                                                                                   |
| glods                | git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset' --date=short                                                                      |
| glola                | git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset' --all                                                                             |
| glog                 | git log --oneline --decorate --graph                                                                                                                                                     |
| gloga                | git log --oneline --decorate --graph --all                                                                                                                                               |
| glp                  | git log --pretty=\<format\>                                                                                                                                                              |
| gm                   | git merge                                                                                                                                                                                |
| gmom                 | git merge origin/$(git_main_branch)                                                                                                                                                      |
| gmtl                 | git mergetool --no-prompt                                                                                                                                                                |
| gmtlvim              | git mergetool --no-prompt --tool=vimdiff                                                                                                                                                 |
| gmum                 | git merge upstream/$(git_main_branch)                                                                                                                                                    |
| gma                  | git merge --abort                                                                                                                                                                        |
| gp                   | git push                                                                                                                                                                                 |
| gpd                  | git push --dry-run                                                                                                                                                                       |
| gpf                  | git push --force-with-lease --force-if-includes (git version >= 2.30)                                                                                                                    |
| gpf                  | git push --force-with-lease (git version < 2.30)                                                                                                                                         |
| gpf!                 | git push --force                                                                                                                                                                         |
| gpoat                | git push origin --all && git push origin --tags                                                                                                                                          |
| gpod                 | git push origin --delete                                                                                                                                                                 |
| gpr                  | git pull --rebase                                                                                                                                                                        |
| gpu                  | git push upstream                                                                                                                                                                        |
| gpv                  | git push --verbose                                                                                                                                                                       |
| gr                   | git remote                                                                                                                                                                               |
| gra                  | git remote add                                                                                                                                                                           |
| grb                  | git rebase                                                                                                                                                                               |
| grba                 | git rebase --abort                                                                                                                                                                       |
| grbc                 | git rebase --continue                                                                                                                                                                    |
| grbd                 | git rebase $(git_develop_branch)                                                                                                                                                         |
| grbi                 | git rebase --interactive                                                                                                                                                                 |
| grbm                 | git rebase $(git_main_branch)                                                                                                                                                            |
| grbom                | git rebase origin/$(git_main_branch)                                                                                                                                                     |
| grbo                 | git rebase --onto                                                                                                                                                                        |
| grbs                 | git rebase --skip                                                                                                                                                                        |
| grev                 | git revert                                                                                                                                                                               |
| grh                  | git reset                                                                                                                                                                                |
| grhh                 | git reset --hard                                                                                                                                                                         |
| groh                 | git reset origin/$(git_current_branch) --hard                                                                                                                                            |
| grm                  | git rm                                                                                                                                                                                   |
| grmc                 | git rm --cached                                                                                                                                                                          |
| grmv                 | git remote rename                                                                                                                                                                        |
| grrm                 | git remote remove                                                                                                                                                                        |
| grs                  | git restore                                                                                                                                                                              |
| grset                | git remote set-url                                                                                                                                                                       |
| grss                 | git restore --source                                                                                                                                                                     |
| grst                 | git restore --staged                                                                                                                                                                     |
| grt                  | cd "$(git rev-parse --show-toplevel \|\| echo .)"                                                                                                                                        |
| gru                  | git reset --                                                                                                                                                                             |
| grup                 | git remote update                                                                                                                                                                        |
| grv                  | git remote --verbose                                                                                                                                                                     |
| gsb                  | git status --short -b                                                                                                                                                                    |
| gsd                  | git svn dcommit                                                                                                                                                                          |
| gsh                  | git show                                                                                                                                                                                 |
| gsi                  | git submodule init                                                                                                                                                                       |
| gsps                 | git show --pretty=short --show-signature                                                                                                                                                 |
| gsr                  | git svn rebase                                                                                                                                                                           |
| gss                  | git status --short                                                                                                                                                                       |
| gst                  | git status                                                                                                                                                                               |
| gsta                 | git stash push (git version >= 2.13)                                                                                                                                                     |
| gsta                 | git stash save (git version < 2.13)                                                                                                                                                      |
| gstaa                | git stash apply                                                                                                                                                                          |
| gstc                 | git stash clear                                                                                                                                                                          |
| gstd                 | git stash drop                                                                                                                                                                           |
| gstl                 | git stash list                                                                                                                                                                           |
| gstp                 | git stash pop                                                                                                                                                                            |
| gsts                 | git stash show --text                                                                                                                                                                    |
| gstu                 | git stash --include-untracked                                                                                                                                                            |
| gstall               | git stash --all                                                                                                                                                                          |
| gsu                  | git submodule update                                                                                                                                                                     |
| gsw                  | git switch                                                                                                                                                                               |
| gswc                 | git switch -c                                                                                                                                                                            |
| gswm                 | git switch $(git_main_branch)                                                                                                                                                            |
| gswd                 | git switch $(git_develop_branch)                                                                                                                                                         |
| gts                  | git tag -s                                                                                                                                                                               |
| gtv                  | git tag \| sort -V                                                                                                                                                                       |
| gtl                  | gtl(){ git tag --sort=-v:refname -n --list ${1}\* }; noglob gtl                                                                                                                          |
| gunignore            | git update-index --no-assume-unchanged                                                                                                                                                   |
| gunwip               | git log --max-count=1 \| grep -q -c "\-\-wip\-\-" && git reset HEAD~1                                                                                                                    |
| gup                  | git pull --rebase                                                                                                                                                                        |
| gupv                 | git pull --rebase --verbose                                                                                                                                                              |
| gupa                 | git pull --rebase --autostash                                                                                                                                                            |
| gupav                | git pull --rebase --autostash --verbose                                                                                                                                                  |
| gupom                | git pull --rebase origin $(git_main_branch)                                                                                                                                              |
| gupomi               | git pull --rebase=interactive origin $(git_main_branch)                                                                                                                                  |
| glum                 | git pull upstream $(git_main_branch)                                                                                                                                                     |
| gluc                 | git pull upstream $(git_current_branch)                                                                                                                                                  |
| gwch                 | git whatchanged -p --abbrev-commit --pretty=medium                                                                                                                                       |
| gwip                 | git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit --no-verify --no-gpg-sign --message "--wip-- [skip ci]"                                                            |
| gam                  | git am                                                                                                                                                                                   |
| gamc                 | git am --continue                                                                                                                                                                        |
| gams                 | git am --skip                                                                                                                                                                            |
| gama                 | git am --abort                                                                                                                                                                           |
| gamscp               | git am --show-current-patch                                                                                                                                                              |
| gwt                  | git worktree                                                                                                                                                                             |
| gwtls                | git worktree list                                                                                                                                                                        |
| gwtmv                | git worktree move                                                                                                                                                                        |
| gwtrm                | git worktree remove                                                                                                                                                                      |

### Main branch preference

Following the recent push for removing racially-charged words from our technical vocabulary, the git plugin favors using
a branch name other than `master`. In this case, we favor the shorter, neutral and descriptive term `main`. This means
that any aliases and functions that previously used `master`, will use `main` if that branch exists. We do this via the
function `git_main_branch`.

## Functions

### Current

| Command                | Description                                                                                              |
| :--------------------- | :------------------------------------------------------------------------------------------------------- |
| `grename <old> <new>`  | Rename `old` branch to `new`, including in origin remote                                                 |
| current_branch         | Return the name of the current branch                                                                    |
| git_current_user_name  | Returns the `user.name` config value                                                                     |
| git_current_user_email | Returns the `user.email` config value                                                                    |
| git_main_branch        | Returns the name of the main branch: `main` if it exists, `master` otherwise                             |
| git_develop_branch     | Returns the name of the develop branch: `dev`, `devel`, `development` if they exist, `develop` otherwise |

### Work in Progress (WIP)

These features allow to pause a branch development and switch to another one (*"Work in Progress"*,  or wip). When you want to go back to work, just unwip it.

| Command          | Description                                     |
| :--------------- | :---------------------------------------------- |
| work_in_progress | Echoes a warning if the current branch is a wip |
| gwip             | Commit wip branch                               |
| gunwip           | Uncommit wip branch                             |
