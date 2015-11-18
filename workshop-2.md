# Workshop 2

## Branching and merging

Note: Make sure to stick to the commit-message rules in the future (don't worry
about the older commits)

- Play around with branches, you should understand all the commands in the cheat sheet below.
- Create a branch, commit some changes both on that branch and on `master`,
  then merge them back together.
- Do the same steps but this time change something in the same place in both
  branches, then merge and resolve the merge conflict.

## GitHub

- Push the repository you have been playing with today up to GitHub
- Create a nicely markdown-formatted README.md file

### Group work

Pair up with 1 to 3 friends, timing is not super important - you can just
jump into a group when you are done with the other tasks. One of you grants the
others collaborator access to their repository.

- Make a text file with a list of your favourite foods, movies...
- All the collaborators add to this list by trying out the following techniques:
    - Pushing directly to master
    - Creating a local branch, merging it to master and pushing
    - Pushing a branch and opening a pull request

What are the pros and cons of these 3 ways of working? When should you use which?

If by some miracle messing around like this does **not** at some point give you
a merge conflict - try to provoke one so you can practice resolving them.

---

## Reference

This is just some extra material and help to get through the exercises.

### Cheat sheet

#### Branching

- `git branch` - show available branches
- `git branch develop` - create a branch called develop
- `git checkout master` - switch to the master branch
- `git checkout -b develop` - create and switch to a branch called develop

#### Working with remotes

- `git clone https://github.com/alcesleo/git-101.git` - clone my git-101 repository
- `git fetch` - download changes from the remote
- `git pull` - fetch and merge
- `git push` - upload changes to the remote

### Fixing warnings

#### Password prompt shows up every time I push

This is annoying, and there are two ways of doing it. One is to use SSH, which is a bit harder to set up, or to do this:

On Mac: `git config --global credential.helper osxkeychain`
On Windows: `git config --global credential.helper wincred`
On Linux: `git config --global credential.helper cache`

Here are more detailed instructions: https://help.github.com/articles/caching-your-github-password-in-git/

#### Push default is unset

```
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple
```

You want the simple behaviour, follow Git's instructions to set that.

#### Push rejected

```
To ssh://git@coderepo.com:7999/repo/myproject.git
! [rejected]        feature/my_feature_branch -> feature/my_feature_branch (non-fast-forward)
error: failed to push some refs to 'ssh://git@coderepo.com:7999/repo/myproject.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Merge the remote changes (e.g. 'git pull')
hint: before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

This means that the server has commits that you don't. You need to **pull
before you push** to merge in the changes on GitHub.

#### Current branch has no upstream

```
fatal: The current branch foo has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin foo
```

This means that the current branch is not tracking a branch on GitHub, follow
Git's instructions but replace "foo" with the name of your branch - next time
it will work to just run `git push`

### Visualizer

Here is the link to the visualizer I showed you in case you want to play with it yourself.

http://onlywei.github.io/explain-git-with-d3/

**Warning**: The visualizer can be really helpful to get a mental model of Git,
but bear in mind that it is **completely fake**. It never actually performs any
git commands, not all commands in git will work except for the most basic use
cases, and they can also differ from how the real git would handle them.
