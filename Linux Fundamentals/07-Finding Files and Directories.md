## Finding Files and Directories

### What You Will Learn

*****

* Two commands that allow you to find files and directories.

### The find Command

*****

```
find [path...] [expression]
```

Recursively finds files in path that match expression. if no arguments are supplied it find all files in the current directory.

### find Options

*****

Options | Description
:--: | :--:
-name pattern | Find files and directories that match pattern.
-iname pattern | Like -name, but ignores case.
-ls | Performs a `ls` on each of the found items.
-mtime days | Finds files that are days old.
-size num | Finds files that are of size number.
-newer file | Finds files that are newer than file.
-exec command {} \; | Run command against all the files that are found.

### A Fast Find - locate

*****

```
locate pattern
```

* Lists files that match pattern
* Faster than the `find` command.
* Queries an index.
* Results are not in real time.
* May not be enabled on all systems.