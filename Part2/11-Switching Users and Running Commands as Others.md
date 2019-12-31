## Switching Users and Running Commands as Others

### What You Will Learn

*****

* How to switch to another account
* How to run commands as others

### The su Command

*****

`su [username]` - Change user ID or become superuser

### su Options

*****

Command | Description
:--: | :--:
`-` | A hyphen is used to provide an environment similar to what the user would expect had the user logged in directly
`- c command` | Specify a command to be executed

### Who Am I

*****

`whoami` - Displays the effective username

### whoami Example

*****

```
$ whoami
jason
$ su oracle
Password:
$ whoami
oracle
$
```

### Sudo - Super User Do

*****

* `sudo` - Execute a command as another user, typiclly the superuser

### Using sudo

*****

Command | Description
:--: | :--:
`sudo -l` | List available commands
`sudo command` | Run command as root
`sudo -u user command` | Run as user
`sudo su` | Switch to the superuser account
`sudo su -` | Switch to the superuser account with root's environment
`sudo su - username` | Switch to the username account
`sudo -s` | Start a shell
`sudo -u user -s` | Start a shell as user

### Changing the sudo Coniguration

*****

* `visudo` - Edit the `/ect/sudoers` file

### Sudoers Format

*****

* user host=(users) [NOPASSWD:]commands
* adminuser ALL=(ALL) NOPASSWD:ALL
* jason linuxsvr=(root) /etc/init.d/oracle