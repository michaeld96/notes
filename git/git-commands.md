# Git Commands

## Download Updates to your Local Repo

**Syntax:** `git fetch <remote-repo> <branch>`

**Example:**
```
git fetch origin dev
```

## Download Updates and Merge Changes to your Local Repo

**Syntax:** `git pull`

**Example:**
```
git pull
```

**More:** If you're me, you can be lazy and just run `git pull` without worrying about 
doing a `git fetch` and then a `git merge <branch-name>`. Also, I thought this image was nice.

<p align="center">
    <img src="imgs/git-pull.png">
</p>

## Divergent Branches but no Conflict

**Syntax/Example:** `git pull --rebase origin main`

**More:** When your local branch is behind the remote `main` branch, 
you will need to sync your local branch with the remote one. Using the 
`--rebase` option, Git will apply your local changes on top of the 
latest changes from the `main` branch. This keeps the commit history 
linear by replaying your commits as if they were made after the commits 
on main, rather than merging them into the branch with a merge commit.
This diagram below I believe is a good figure for `rebase`.


<p align="center">
    Before the Rebase
    <img src="imgs/basic-rebase-before.png">
    After the Rebase
    <img src="imgs/basic-rebase-after.png">
    <br>
    <a href="https://git-scm.com/book/en/v2/Git-Branching-Rebasing">Source of Images</a>
</p>

