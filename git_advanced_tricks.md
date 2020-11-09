# Commiting without add

The `add` command adds untracked and tracked files to the staged area. But
sometimes we don't really the staged area because we want to commit all of the
tracked files.

If that's the case, we can use the `-a` flag.

`git commit -a`

Then, all the **tracked** files will be commited automaticly without the need
use the `add` command. And indeed and `-a` isn't an alias for adding and than
commiting, it's smarter than that.


# Show the changes in each commit

Sometimes we need more information about each commit, like the changes
themselves. If we want `git log` to also print the changes in each commit, we
can use the `-p` flag (which stands for _patch_).

`git log -p`

One more thing about `git log` is that we can use `-num` where `num` is any
number to restrict the amount of commits we'll see. If we run

`git log -p -2`

it will show us just the last two commits.

That can be useful, but many more times we need the changes of just a single
commit. In those cases, we can use `git show` passing a commit ID (which is
shown by the `log` command).

`git show ID`

That will show the changes only for that commit.

One more option to `git log` is the `--stat`. It's very useful because it shows
the basic information of each commit plus how many insertions and deletions each
file recieved.

# Git diff

The `git diff` command shows the changes we made to each file between the last
commit and the current stage of the working tree.

If you want to check the differences for a specific file, you can pass the file
as a parameter to the command.

One problem `git diff` might have is that is just show unstaged changes by
default. So if you want to show differences in staged files you can use the
`--staged` flag.

# Checking differences before staging files

The `add` command can be used with the `-p` flag. It will go through all the
changes we made and ask us if we want or not to stage those changes.

# Remove and move files

Git have the `rm` and `mv` commands just like in bash. If you need to remove or
move (or rename) a file, you can use

`git mv file1 file2`

or

`git rm file`

If you remove or move a file using Git, the file will be removed from your
working tree and git will stage that change.

# Git ignore

If we have files in your working directiory that we want Git to ignore and don't
show them as untracked files, we can add their names to a file called
`.gitignore`. We just need to create it in our root directory and add each name
in one line (is accepts regex).

Before creating the .gitignore file, we need to add and commit it just like a
regular file.

# Commits IDs

You can see a commit ID using `git log`.
When ever a command need to refers to a certain commit, it'll probrably use the
commit ID. But you don't need to type the complete ID, you just need to give Git
the first few chars and Git can detect what commit we're refering to.
