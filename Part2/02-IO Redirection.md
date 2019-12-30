## I/O Redirection

### What You Will Learn

*****

* Three I/O Types
* Redirection

### Input/Output Types

I/O Names | Abbreviation | File Descriptor
:--: | :--: | :--:
Standard Input | stdin | 0
Standard Output | stdout | 1
Standard Error | stderr | 2

### Redirection 

*****

* `>` - Redirects standard output to a file. Overwrites(truncating) existing contents.
* `>>` - Redirects standard output to a file. Appends to any existing contents.
* `<` - Redirects input from a file to a command.
* `&` - Used with redirection to signal that a file descriptor is being used.
* `2>&1` - Combine stderr and stdout.
* `2>file` - Redirect standard error to a file.

### The Null Device

*****

* `>/dev/null` - Redirect output to nowhere.
		