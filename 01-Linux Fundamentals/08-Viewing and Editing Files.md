## Viewing and Editing Files

### What You Will Learn

*****

* Different way to display the contents of files.
* How to use the Nona editor.

### Displaying the Contents of Files

*****

* `cat file` ----------- Display the contents of file.
* `more file` ---------- Browse through a text file.
* `less file` ---------- More features than more.
* `head file` ---------- Output the beginning(or top) portion(`部分`) of file.
* `tail file` ---------- Output the ending(or bottom) portion of file.

### Head and Tail

*****

* Display only 10 lines by default
* Change this behavior with -n
  * n = number of lines
  * `tail -15 file.txt`

### Viewing Files in Real Time

*****

```
tail -f file 　　　　Follow the file
```
Displays data as it is being written to the file.

### Nano Editor

*****

* Nano is simple editor.
* Easy to learn.
* Not as advanced as vi or emacs.
* If Nano is not available, look for pico.