## Environment Variables

### What You Will Learn

*****

* Environment variables

### Common Environment Variables

*****

Variable | Description
:--: | :--:
EDITOR | Program to run to perform edits
HOME | Home directory of the user
LOGNAME | The login name of the user
MAIL | The location of the user's local inbox(`收件箱`)
OLDPWD | The previous working directory
PATH | A list of directions to search for commands
PAGER | Program used to paginate through files
PS1 | The primary prompt string
PWD | Present(`现存的;当前的`) working directory
USER | The username of the current user

### Viewing Environment Variables

*****

* `printevn` - Print all or part of environment.
* `echo $ENV_VAR` - Print the ENV_VAR variable.

### Exporting Environment Varialbes

*****

* `export` - Allows vars to be used by subshells.

### Removing Varialbes

*****

* `unset` - delete an environment variable