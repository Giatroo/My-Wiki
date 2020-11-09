# Branches

## What is a branch?

A branch is basicly a pointer to a commit.

The default branch ever project comes with is the **master** branch. It's
commonly used as the known good state of a project, or the realizes to the
public.

When we want to add a new feature to a project, the good practice is creating a
new branch that extends the master and working inside that branch until our
feature is done and we want to add it to the master branch.

By doing that we avoid messing up the current good state of our project.

After finishing a branch, we do a **merge** to join two branches into one.

## Creating branches

We can list the local branches using the

`git branch`

command.

And if we want to create a new branch, we just pass the branch new:

`git branch new-branch`

The `git branch` command shows us in with branch we're currently in with an
asterisk. When we create a new branch we're not automaticly moved to it.

If we want to move to another branch, we use the

`git checkout new-branch`

command.

However, there's a way to create and switch to a new branch running

`git checkout -b new-branch`

## Deleting a branch

If we don't need a branch anymore, we can delete it using the `-d` option.

`git branch -d some-branch`

But Git will only allow you to delete a branch if it has no changes or if those
changes have been marged back to the master branch.

If you really want to delete a branch that has changes inside it, you can use
the `-D` option.

`git branch -D some-branch`

## Merging

To merge some branch with other, we can run

`git merge merging-branch`

This will merge the branch we passed as a parameter into the current branch.

### Merge conflicts

If there are changes in the same file of a file inside two branches, git won't
know how to merge the branches and we'll need to pick the changes we want
handly.

You can abort the merge using

`git merge --abort`

or fix the merge conflicts handly.

We you open a file with merge conflicts, the lines with those conflicts will
look like this:

```
<<<<<<< HEAD
    Code1
=======
    Code2
>>>>>>> merging-branch
```

The first part (code 1) is the code that was inside our branch before we tried
to merge. And the second part (code2) is the code that was inside the
merging-branch.

To fix the conflicts, we can delete the lines we don't want and keep the ones we
want (and delete the extra lines git inserted).

Before fixing the conflicts, we just need to run `git add` in our file and add
an extra commit to end the merge.

**Observation:** Every merge is treated as a commit. What's why we need to make
that commit manually when there are conflicts. If there were no conflicts, Git
would automaticly create a new commit.

If we want to have a better visualization of our branches and merges, we can
call `git log` using the `--oneline` and `--graph` options.

`git log --oneline --graph`
