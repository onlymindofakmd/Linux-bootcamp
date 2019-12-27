## Deleting, Copying, Moving, and Renaming Files

### What You Will Learn

*****

* Deleting files
* Copying files
* Moving files
* Renaming files
* Compressing files
* Create archives

### Removing Files

*****

Command | Description
:--: | :--:
`rm file` | Remove file
`rm -r dir` | Remove the directory and its contents recursively(`递归`)
`rm -f file` | Force removal and never prompt(`提示，提示符`) for confirmation

### Copying Files

*****

Command | Description
:--: | :--:
`cp source_file destination_file` | Copy source_file to destination_file.
`cp src_file1 [src_fileN ...] dest_dir` | Copy source_files to destination_directory.
`cp -i` | Run in interractive mode.
`cp -r source_directory destination` | Copy src_directory recursively to destination.

### Moving and Renaming Files

*****

Command | Description
:--: | :--:
`mv` | Move or rename files and directories.
`mv source destination` | Move source to destination
`mv -i source destination` | Interractive mode

### Sorting Data

*****

`sort file` Sort text in file

Command | Description
:--: | :--:
`-k F` | Sort by key. F is field number
`-r` | Sort in reverse order.
`-u` | Sort unique

### Creating a Collection of Files

*****

`tar [-] c|x|t f tarfile [pattern]` | Create, extract or list contents of a tar archive using pattern, if supplied.

### tar Options

*****

Command | Description
:--: | :--:
`c` | Create a tar archive.
`x` | Extract files from the archive.
`t` | Display the table of contents(list)
`v` | Be verbose.
`z` | Use compression
`f file` | Use this file

### Compressing Files To Save Space

*****

Command | Description
:--: | :--:
`gzip` | Compress files.
`gunzip` | Uncompress files.
`gzcat` | Concatenates compressed files.
`zcat` | Concatenates compressed files.

### Disk Usage

*****

Command | Description
:--: | :--:
