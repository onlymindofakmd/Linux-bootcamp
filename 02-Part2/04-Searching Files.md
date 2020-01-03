## Searching Files Using Pipes

### What You Will Learn

*****

* How to search contents of files.
* What pipes are and how to use them.

### The `grep` Command

*****

* `grep` - Display lines matching a pattern.
  * `grep pattern file`

### `grep` Options

*****

Command | Description
:--: | :--:
`-i` | Perform a search, ignoring case.
`-c` | Count the number of occurrences in a file.
`-n` | Precede output with line numbers.
`-v` | Invert match. Print lines that don't match.

### The `file` Command

*****

* `file file_name` - Display the file type.

### Searching for Text in Binary Files

*****

* `strings` - Display printable strings.

### Pipes 

*****

* `|` - Pipe symbol
  * `command-output | command-input`
  * `cat file | grep pattern`

### The `cut` Command

*****

* `cut [file]` - Cut out selected portions of file. If file is omitted, use standard input.

### `cut` Options

*****

Command | Description
:--: | :--:
`-d delimiter` | Use delimiter as the field separator.
`-f N` | Display the Nth field.