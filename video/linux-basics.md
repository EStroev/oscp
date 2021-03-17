# Linux Basics

## Documentation

| Command | Description |
| :--- | :--- |
| man -k passwd | keyword search |
| appropos partition | search the list of man page descriptions |

## Listing

| Command | Description |
| :--- | :--- |
| ls -a | hidden files |
| ls -1 | each file on a single line |
| ls -r | recursive |

## Creating directories

| Command | Description |
| :--- | :--- |
| mkdir -p test/{recon,exploit,report} | create any required parent directories |

## Finding files

| Command | Description |
| :--- | :--- |
| which | searches through the directories that are defined in the $PATH environment variable for a given file name |
| find | the most complex and flexible search tool |
| locate | quickest way to find the locations of files and directories in Kali. In order to provide a much shorter search time, locate searches a built-in database named locate.db rather than the entire hard disk itself |
| updatedb | To manually update the locate.db database |

## Searching, Installing, and Removing Tools

| Command | Description |
| :--- | :--- |
| apt-cache search | displays much of the information stored in the internal cached package database |
| apt remove | remove a package |
| apt remove –purge | remove a package |
| dpkg -i | To install a package |

## Services

| Command | Description |
| :--- | :--- |
| systemctl list-unit-files | Most services in Kali Linux are operated in much the same way as SSH and HTTP, through their service or init scripts. To see a table of all available servicessudo ss -antlp |
| sudo ss -antlp |  |
| systemctl enable ssh | To have the SSH service start at boot time |

