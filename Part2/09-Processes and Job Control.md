## Processes and Job Control

### What You Will Learn

*****

* List running processes
* Foreground vs background processes
* Launch background processes
* Kill processes

### Listing Processes and Information

*****

* `ps` - Display process status

### ps Options

*****

Command | Description
:--: | :--:
`-e` | Everything, all processes
`-f` | Full format listing
`-u username` | Display username's processes
`-p pid` | Display information for PID

### Common ps Commands

*****

Command | Description
:--: | :--:
`ps -e` | Display all processes
`ps -ef`  | Display all processes, full
`ps - eH` | Display a process tree
`ps -e --forest` | Display a process tree
`ps -u username` | Display user's processes

### Other way to view processes

*****

Command | Description
:--: | :--:
`pstree` | Display processes in a tree format
`top` | Interactive process viewer
`htop` | Interactive process viewer

### Backgroud and Foregroud Processes

*****

Command | Description
:--: | :--:
`command &` | Start command in background
`Ctrl - c` | Kill the foreground process
`Ctrl - z` | Suspend the foreground process
`bg [%num]` | Background a suspended process
`fg [%num]` | Foreground a background process
`kill` | Kill a process by job number or PID
`jobs [%num]` | List jobs

### Killing Processes

*****

Command | Description
:--: | :--:
`Ctrl - c` | Kills the foreground proc
`kill [-sig] pid` | Send a signal to a process
`kill -l` | Display a list of signals