# 2.0 Linux in a nutshell cheatsheet.

## 2.1 Linux Filesystem Hierarchy 

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/file_hierarchy_linux.png)

## 2.2 Man pages

- `$ man ls`

Man pages contain not only information about user commands, but also documentation regarding system administration commands, programming interfaces, and more.

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/sections-man.png)

- `man -k passwd` - To perform a keyword search.

- `apropos partition` - Another way to perform a keyword search through the man pages.

## 2.3 Locating files 

- `locate <file_name or directory>` - Quickest way to find files.

- `which <file_name or directory>` - Returns pathnames of files or links which would execute in current environment. (By PATH variable)

- `find / -name <file>` 

- `find / -name <file> -type d` - Directory search

- `find / -name <file> -type f` - File search

- `find / -mtime +n` - Finds the files and directories modified more than n days ago.

- `find / -mtime -n` - Finds the files and directories modified less than n days ago. (Use `-mmin [+,-]n` for Minutes instead of days. 

## 2.4 Linux Services
- Start/Stop a Service

`$ sudo systemctl start/stop/enable/disable <service_name>` or `$ sudo service <service_name> start/stop`

- Check if a service is running

`$ netstat -tunap | grep <service_name>` or `$ ss -antlp | grep <service_name>`

- To see available service table

`$ systemctl list-unit-files`

Notes:

Service names for SSH:`ssh` , HTTP:`apache2`

Default index.html location: `/var/www/html`

## 2.5 Extracting archives 

- `tar xvfz <file>` - Extract tar file

- `gunzip <file>` - Extract gz file

## 2.6 Other useful commands

- `cat <file> | wc -l` - Returns line count of a specific file 

- `head <file>` - Returns first 10 lines in a file

- `less <file>` - Return file content in much easy to read view. Use `Shift+G` for go to the END

- `cat <file> | sort -u` - Show unique lines

- `cat <file> | uniq -c` - Show the count of unique lines

- `cat <file> | sort -urn` - Sort out unique lines in reverse order according to the numeric value

- `uname -a` - Linux version

- `host <url>` - Shows the corresponding IP address for a specific url. 

- `ldd <binary_file>` - Returns which dynamic libraries used by the program.

## 2.7 Other useful locations and files in linux

- `/etc/os-release` - OS Release information

-

## 2.8 Linux Variables

- Shell Variables (Variables which are only in scope of the shell)
	> `set` Command will show the all variables in the shell.
	
	> `set | grep <variable_name>` To see the specific variable

- Environment Variables (Variables which are available for system-wide)
	> `env` Command will show the all variables which are available system-wide.

	> `env | grep <variable_name>` Will return the specific variable name with its value.

- **Export** command
	
	We can use export command to export a variable to system-wide scope (Environment Variable) and also available for shell (Shell Variable). 

	Usage:

	![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/export2.png)

	**Good resource to understand export lot more way better** :

	![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/export0.png)
	
	![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/export1.png)
