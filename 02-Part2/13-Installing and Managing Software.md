## Installing and Managing Software

### What You Will Learn

*****

* Packages
* Package managers
* Managing software for RPM based distros(`发行版`)
* Managing software for DEB based distros

### Package

*****

* A collection of files
* Data/Metadata
  * Package description
  * Version
  * Dependencies

### Package Manager

*****

* Installs, upgrades, and removes packages.
* Manages dependencies.
* Keeps track of what is installed.

### Installing Software on RPM Distros

*****

* RedHat
* CentOS
* Fedora
* Oracle Linux
* Scientific Linux

### yum

*****

Command | Description
:--: | :--:
`yum search string` | Search for string
`yum info [package]` | Display info
`yum install [-y] package` | Install package
`yum remove package` | Remove package

### rpm

*****

Command | Description
:--: | :--:
`rpm -qa` | List all installed packages
`rpm -qf /path/to/file` | List the file's package.
`rpm -ql package` | List package's files
`rpm -ivh package.rpm` | install package
`rpm -e package` | Rrase(uninstall) package

### Installing software on DEB Distros

*****

* Debian
* Linux Mint
* Ubuntu

### APT - Advanced Packaging Tool

*****

Command | Description
:--: | :--:
`apt-cache search string` | Searching for string
`apt-get install [-y] package` | Install package
`apt-get remove package` | Remove package, leaving configuration
`apt-get purge package` | Remove package, deleting configuration
`apt-cache show packaage` | Display information about package

### dpkg

*****

Command | Description
:--: | :--:
`dpkg -l` | List installed package
`dpkg -S /path/to/file` | List file's package
`dpkg -L package` | List all files in package
`dpkg -i package.deb` | Install package 