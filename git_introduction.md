# Introduction to Git

## Setting up

Before using Git, we to inform Git who we are

`git config --global user.email "your@email"`
`git config --global user.name "your name"`

We can also configure it to use our favourite text editor.

`git config --global core.editor "vim"`

Every Git command will begin with the `git` prefix.

* `config` stands for configurations,
* `--global` tells Git we want those configurations to be set to every
  repository;

## Creating a repository

A **repository** is basicly a directory where Git will make the version
management of all files listed inside (and directories).

To indicate to Git we want the current folder to be a repository, we execute:

`git init`

Now we will split this folder into two main areas the `.git` folder and every
other file (what we call the **working tree**).

Inside `.git`, Git will track all the history of all files and many other
information about who edited them.

Each time we want git to take a snapshot of our files, we need to make a
**commit**. But git will commit only the files we tell it to commit.

To tell git we want to commit a file, we need to add it to the **staged area**.

`git add file`

When me make a commit, all the file in the staged area will be saved as a
commit.

To visualize which files are in the staged area, we can use

`git status`

Them we can see that the files can be **tracked** or **untracked**.

* Untracked files are files that were never commited
* and tracked files are files that appear on any previous commit.

When we change a file that was commited before, turns into a tracked but
**modified** file. And thus, we need to add it again to the staged area.

Finally, to commit the staged files, we run

`git commit`

It will open our editor asking for a **commit message** that describes what
changed in your commit or what's the reason for it.

You can also give this message to git inside the command:

`git commit -m "My message"`

If you don't add any message, the commit will be aborted.

A good commit message usually have a short line at the top with about fifty
characters. Then, you can add as many paragraphs as you need to describe the
commit in a good way. But make sure to use at most seventy columns in each line
and always leave a blank line between paragraphs.

If a line starts with # in the commit message, then it's a comment and will not
be included in the real message.

One more observation is that it's always good to use the imperative tense in the
first line of our commit.


If you want to check previous commits, you can run

`git log`

Each commit will begin with a large string which is the commit's unique
identifier. Then, we have the authors name and email followed by the date of the
commit. Before that header, we have the commit message.
