# Git

## How to avoid merge commits

[Why](https://stackoverflow.com/questions/6406762/why-am-i-merging-remote-tracking-branch-origin-develop-into-develop)

Download the latest commits

```bash
git remote update -p
```

Update the local branch

```bash
git merge --ff-only @{u}
```

If the above fails with a complaint that the local branch has diverged:

```bash
git rebase -p @{u}
git reset --hard HEAD~1
git reset HEAD~1
```

### Add

#### [Co authored](https://blog.github.com/2018-01-29-commit-together-with-co-authors/)

Adds co-author to your commit message. Handy for pair programming.

```bash
Commit message

Co-authored-by: Joel Califa <602352+califa@users.noreply.github.com>
```

### Push

In order to not override someone else commits(with force) in remote repository use:

```bash
git push --force-with-lease
```

#### Reset

```bash
git reset HEAD~1
```

where `~1` is a number of commits from HEAD

```bash
# hard reset (loosing files/changes)
git reset --hard HEAD~1
```

#### Rebase

```bash
# on a remote branch
git pull --rebase

# on a master
git pull --rebase origin master
```

#### Stash

```bash
# preview last stashed changes
git stash show -p stash@{0}
```

Create named stash with adding files with hunks preview

```bash
git stash push -p -m "my awesome config"
```

#### Checkout unwanted files

```bash
git checkout -- .
```

#### Checkout to previous branch

```bash
git checkout -
```

### Edit last local commit message

```bash
git commit --amend
```

#### Git log

To view a git log of just one user's commits:

```bash
git log --author="Alex"
```

## Commit

### Empty commit

Is useful to re-trigger CI pipeline or any other cloud integrations.

```bash
git commit --allow-empty -m "Trigger something"
```

## Branch

### Rename a local Git branch

#### Rename a current branch

```bash
git branch -m <newname>
```

#### Rename a brach while pointed to any branch

```bash
git branch -m <oldname> <newname>
```

## Git global configurations

### in ~/.gitconfig

#### To change your Git **username** and **email**

```bash
git config --global user.name "Alexander Grischuk"
git config --global user.email [your email address here]
```

#### Enable git pull use rebase by default

```bash
git config --global pull.rebase true
```

is equivalent to running `git pull --rebase` every time.

#### [Set the upstream automatically on push](https://git-scm.com/docs/git-config#Documentation/git-config.txt-pushdefault)

```bash
git config --global push.default current
```

#### ~/.gitignore_global

#### Ignore IDEA files globally

```bash
echo ".idea" > ~/.gitignore_global

git config --global core.excludesfile ~/.gitignore_global
```

### Create a new `.gitignore` file fetched from the GitHub repo for a "node" js app

```bash
npx gitignore node
```

#### Creating a SSH Public Key on OSX

```bash
ssh-keygen -t rsa -b 4096
```

#### Copy public SSH key and add it to the GitHub

```bash
pbcopy < ~/.ssh/id_rsa.pub
```

#### UseKeychain: do not re-enter password while commiting/clonning

Add following to the `~/.ssh/config`

```bash
Host *
    UseKeychain yes
```

#### How to resolve conflicts in yarn.lock

[https://github.com/yarnpkg/yarn/issues/1776#issuecomment-269539948](https://github.com/yarnpkg/yarn/issues/1776#issuecomment-269539948)

```bash
git rebase origin/master
```

When the first conflict arises, I checkout the yarn.lock then re-perform the installation

```bash
git checkout origin/master -- yarn.lock

yarn
```

This generates a new yarn.lock based on the origin/master version of yarn.lock, but including the changes I made to my package.json. Then it's just a matter of:

```bash
git add yarn.lock
git rebase --continue
```

## Release

### Create a release tag

```bash
git tag <tagname>
```

### Push all tags

```bash
git push origin --tags
```

### Push a _single_ tag

```bash
git push origin <tag>
```

### List all tags

```bash
git tag
```

## Clone

[Get up to speed with partial clone and shallow clone](https://github.blog/2020-12-21-get-up-to-speed-with-partial-clone-and-shallow-clone/)

## Clean up

### clean unreachable object (sometimes speeds up .git)

```bash
git prune --dry-run
```

### clean outdated branches

```bash
git fetch --prune
```

#### Advanced git

- `git-reflog` - Manage reflog information
- `git-bisect` - Use binary search to find the commit that introduced a bug

#### Further reading

[Git Flight Rules](https://github.com/k88hudson/git-flight-rules/)
