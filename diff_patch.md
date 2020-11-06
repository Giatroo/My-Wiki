# Diff and Patch commands

## Diff

The `diff` command returns a message with the changes between two files.

`diff file1 file2`

In each change, it prints a line like:
`l1,l2cl3,l4`

`c` stands for *change* and the numbers `l1` through `l4` are the begining and
end of the changes in the first file and the begining and end of the changes in
the second file.

Then, the changed lines follow with either `>` or `<` in the begining of the
line.
* `>` stands for a new line and
* `<` stands for a deleted line.

Another way to use it is using the `-u` option, then it will print it in a git
like way.

`diff -u file1 file2`

## Generation .diff files

The return of the `diff` command can be redirected to some file for future
usage:

`diff -u file1 file2 > file.diff`

This will create a `file.diff` file in the current directiory and we can use it
with the `patch` command.

We actually don't need the extension `.diff`, it could be `.patch` or any
extension.

## Patch

The `patch` command can use a `.diff` file to apply the changes of a `.diff`
file to some input file. We would use it like:

`patch file < file.diff`

And now patch will apply the changes to `file`.
