# Checkout

If you made some changes to a file and now you need to roll back, you can use

`git checkout file`.

If the file is not in the staged area, then it will reset to the point you leave
it in the previous checkout.
If the file is in the staged area, then it will reset to the point you staged
it.

If you want to checkout just parts of your file, you can use the `-p` flag.

`git checkout -p file`

# Reset

If you added a file to the staged area and want to remove it, you can use
`git reset`. This removes a file from the staged area, making it unstaged.

`git reset HEAD file`

# Overwriting the previous commit

If we made a mistake in our last commit, we can use the flag `--amend` to
overwrite the last commit.

`git commit --amend`

Now, everything in our staged area will be commited above the previous one.
So if we want to remove a file from the previous commit that we shouldn't add,
we can remove it, add the deletion to the staged area and do an amend.
If we made a typo in the commit message, we can edit it with the same command.

But **be careful**, you should always avoid amending commits that have been
pushed to public repositories. That can lead to problems with other people
working in the project because **amend changes the commit ID of a commit**.

# Rolling back a commit

There are many ways to undo commits, one of them is the `git revert HEAD`.
This command will make a new commit removing the lines we added or undoing the
changes we made. But it's important to remember that this is a new commit, so
we're keeping the history of our commits.

We can also revert to any commit using its commit ID.

