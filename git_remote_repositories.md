# Using GitHub

To create an remote repository on GitHub, we need to have an acount and either
create it online or localy.

If we create it online, we use

`git clone URL`

to clone that repository inside our machine.

If we already have a localy repository and want to link it to a new remote
repository, we need to create that repo inside GitHub and then run

`git remote add origin URL`

and then **push** our changes to the remote repository.

`git push -u origin master`

## Pushing and pulling

After doing our local changes, we need to push our changes to the remote
repository. We use the

`git push`

command to do so.

And if other people changed our repository (or if we changed it via GitHub),
we'll need to run

`git pull`

to pull those changes.

## Passwords and account

Everytime we do changes to an remote repository, we need to inform our username
and password. But that's not always necessary if you cache or store some key.

One way to do so is cloning the repository using an ssh key (or adding one to
our repository).

Another way is to cache our information so you don't need to type everytime. To
do so, run

`git config --global credential.helper cache`

to set this option to every repository inside your machine.

Now you just need to type your information once and it will cache it for fifteen
minutes.

## Remote branches

Remote repositories have a name and a URL associated with them. By default,
their name is **origin**.
You can check the remotes of our repository buy running:

`git remote -v`

That will show us the *fetch* and *push* URLs.

We can also show more data using running

**Observation:** The `-v` stands for *verbote*, but you could run that command
without it.

`git remote show origin`

That will show the repository remote and local branches.

Whenever we're using remote repositories, git uses **remote branches** to keep
copies of the data that's stored in the remote repository. We can check those
branches using

`git branch -r`

To modify them, we need to go through the workflow of using push and pull.

One more thing is the fact that when we use

`git status`

it will show us extra information about the remote branches.

It may show us:
`Your branch is up to date with 'origin/master'.`

To indicate there are not any changes to the remote repository.

**Remark:** It's important to use the same name for our local and remote
branches, so Git can know the local branch corresponds to the remote one.

**Observation:** `git remote` is just like an alias command for the URL name.
When we use `git remote add <name> <url>`, we're appending the url and name to a
file which is checked when we use other remote commands like `fetch`, `pull` and
`push` (but we could pass the URL directly to those commands).

We can also rename or remove remote repositories with the comands

`git remote rm <name>`

`git remote rename <name> <new-name>`

## Fetching changes

We can't `push` our commits if our repository is noy synchronized with the
remote.

To check if there are changes in the remote repo, we can use the
`git remove show origin` command that we showed before.

Git doesn't automaticly sync the new commits of other people. To do so, we run

`git fetch`

This will make git copy the new commits into the remote branches so we can
visualize it.

We can run `git checkout` on those branches to see the working tree and
`git log` to visualize the commits.

If we run

`git log origin/master`

we are visualizing the **master** branch of our remote repository (named
**origin**).

Running

`git status`

before a `fetch` will show us how many commits we are behind and if we can do a
fast-forward merge or if we have any conflicts.

To merge, we can call

`git merge origin/master`

**Remark:** So basicly, the differences between `fetch` and `pull` it that
`fetch` doesn't perform any `merge` operation while `pull` does that
automaticly.

One more thing is that if we just want to fetch the content of all remote
branches, we can call

`git remote update`

## Adding local branches to the remote repository

Whenever we create a new local branch, we need to inform our remote repository
that a new branch have been created.

To do so, we pushing inside a the new branch, we need to add the `-u` flag
(which stands for *upstream*) and the name of the remote repo.

## Rebasing
