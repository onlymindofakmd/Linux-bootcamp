## WildCards

### What You Will Learn

*****

* What wildcards are.
* When and where they can be used.
* The different types of wildcards.
* How to use wildcards with various(`各种不同的`) commands.

### Wildcards

*****

* A character or string used for pattern(`模式;方式;范例;典范`) matching.
* Globbing expands the wildcards pattern into a list of files and/or directories.
* Wildcards can be used with most commands
  * ls 
  * rm
  * cp
* `*` - matches zero or more characters.
  * \*.txt
  * a\*
  * a\*.txt
* `?` - matches exactly one character.
  * ?.txt
  * a?
  * a?.txt

### More Wildcards - Character Classes

*****

* [] - A character class.
  * Matches any of the character included between the brackets. Matches exactly one character.
  * [aeiou]
  * ca[nt]\*
    * can
    * cat
    * candy
    * catch
* [!] - Matches any of the characters NOT include between the brackets. Matches exactly one character.
  * [!aeiou]\*
    * baseball
    * cricket

### More Wildcards - Ranges

*****

* Use two characters separated by a hyphen to create a range in character class.
* [a-g]*
  * Matches all files that start with a, b, c, d, e, f, or g
* [3-6]*
  * Matches all files that start with 3, 4, 5, or 6

### Named Character Classes

*****

* [[:alpha:]]
* [[:digit:]]
* [[:alnum:]]
* [[:lower:]]
* [[:upper:]]
* [[:space:]]

### Matching Wildcard patterns

*****

* \ - escape character. Use if you want to match a wildcard character.
  * Matching all files that end with a question mark:
    * \*\?
      * done?