## Listing Files and Understanding `ls` Output

### What You Will Learn

*****

* What the long listing format components(`组成部分;成分;部件`) are.
* How to see hidden files and directories.
* How to list files by type.
* How to list files sorted by time.
* How to handle spaces in file names.
* What symbolic(`使用象征的;作为象征的;象征性的`) links are.

### Decoding ls -l Output

*****

```
$ ls -l
-rw-rw-r-- 1 jason users 10400 Sep 27 08:52 sales.data
```
* Permissions ------------------- -rw-rw-r--
* Number of links --------------- 1
* Ownner name ------------------- jason
* Group name -------------------- users
* Number of bytes in the file --- 10400
* Last modification time -------- Sep 27 08:52
* File name --------------------- sales.data

### Listing All Files, Including Hidden Files

*****

* Hidden files begin with a period(`.`).
*   Sometimes called "dot files."
* Hidden files are not display by default.
* To show hidden files with `ls`, use `ls -a` 
* Command options can be combined.
*   `ls -a -l` is the same as `ls -al`.

### Listing Files by Type

*****

Use `ls -F` to reveal file types.
* / ----- Directory
* @ ----- Link
* * ----- Executable

### Symbolic Links

*****

* A link is a point to the actual file or directory.
* Use the link as if it was the file.
* A link can be used to create a shortcut.
*   Use for long file or directory names.
*   Use to indicate(`表明;显示;象征;暗示;间接提及;示意`) the current version of software.

### Listing Files by Time and in Reverse

*****

* `ls -t` ---------- List files by time.
* `ls -r` ---------- Reverse order.
* `ls -latr` ------- Long listing including all files reverse sorted by time.

### Listing Files Recursively

*****

* `ls -R` ---------- Lists files recursively.

### The Tree Command

*****

Similar to `ls -R`, but creates visual(`视力的;视觉的`) output.
* `tree -d` -------- List directories only.
* `tree -C` -------- Colorize output.

### List Directories, Not Contents

*****

* `ls -d` ---------- List directory name, not contents.

### Listing Files with Color

*****

* `ls --color` ----- Colorize the output.

### Working with Spaces in Names

*****

* Just say no to spaces.
* Alternatives(`其他选择;另类投资;备选方案;替代法;替代品`):
*   Hyphens(-)
*   Underscores(_)
*   CamelCase
* Encapsulate(`封装`) the entire(`全部的;整个的;完全的`) file name in quotes(`引用;引述;举例说明;开价;出价;报价`).
* Use a backslash(\\) to escape spaces.