# Git

#### **How to avoid merge commits**

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

#### **Reset**

```bash
git reset HEAD~1
```

where `~1` is a number of commits from HEAD

```bash
# hard reset (loosing files/changes)
git reset --hard HEAD~1
```

#### **Rebase**

```bash
# on a remote branch
git pull --rebase

# on a master
git pull --rebase origin master
```

#### **Stash**

```bash
# preview last stashed changes
git stash show -p stash@{0}
```

#### **Checkout unwanted files**

```bash
git checkout -- .
```

#### **Checkout to previous branch**

```bash
git checkout -
```

### **Edit last local commit message**

```bash
git commit --amend
```

## Git global configurations

#### in ~/.gitconfig

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

#### ~/.gitignore_global

#### **Ignore IDEA files globally**

```bash
echo ".idea" > ~/.gitignore_global

git config --global core.excludesfile ~/.gitignore_global
```

#### **How to resolve conflicts in yarn.lock**

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

#### **Advanced git**

- `git-reflog` - Manage reflog information
- `git-bisect` - Use binary search to find the commit that introduced a bug

#### **Additional reading**

[Git Flight Rules](https://github.com/k88hudson/git-flight-rules/)
