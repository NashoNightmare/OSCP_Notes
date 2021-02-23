# 3.0 Bash Environment
When opening a new terminal window, a new Bash process, which has its own **Environment variables**, is initialized. One of the most commonly-referenced environment variable is **PATH (Colon seperated directory paths that bash will search through whenever a command is run without a full path.** 

To view the contents of a environment variable :

- `$ echo $PATH` - To view the contents of a given environment variable.

Some other useful environment variables : `USER` , `PWD` , `HOME` , `$`-Process id of the current shell

- `$ export <name>=<value>` - To define a environment variable. NB: *If we do not use `export` to define the variable the variable will be limited to the current shell.

- `$ env` - To view all environment variables

## 3.3 RegEx
A pattern which describes a certain amount of text.

- **Metacharacters** [Those characters should used with escape characters when it is used as a literal.]
	> `\` `^` `$` `.` `|` `?` `*` `+` `(` `)` `[` `]` `{` `}`

	All other characters(non-meta) should not escaped with backslash. Because it may create regex token with specific meaning.
	> `'` `"` - Not metacharacters

	To use regex in programming language string such as C:\temp
	> Regex : `C:\\\\temp`

- **Non printable character tokens**
	> `\t`-Tab, `\r`-Return, `\n`-NewLine, `\a`-Bell, `\e`-Escape, `\f`-FormFeed, `\r\n`-WindowsTextNewLine, `\R`-LineBreak(UnicodeIncluded)

- **Character classes**
	> `[ ]` - To define a character class (Matches only for one character by default, Use quantifier for more options)

	> `[^/]` - Negated character class(In this given example it excludes '/' character.

	Only `]`  `\` `^` are metacharacters in a character class. To match these use backslash.

For more about character classes : [Character classes](http://www.regular-expressions.info/charclass.html)

Reference: [http://www.rexegg.com/](http://www.rexegg.com/)

Reference(NB:This resource is very good): [http://www.regular-expressions.info](http://www.regular-expressions.info)

Reference: [RexEgg Cheatsheet](http://www.rexegg.com/regex-quickstart.html#chars) 

## 3.4 Text-Fu - Tools
- **Grep** (Searches text files for the occurence given regex and outputs any line containing a match to stdout)
> `grep <regex>` - Use `-r` for recursive and `-i` for case ignorance.

> `grep -o <regex>` - Use `-o` for output the only matching text.

- **Sed** (Powerful text stream editor)
> `sed '' <file>` - Prints lines automatically

> `sed -n 'p' <file>` - Suppresses the automatic printing functionality and print manually

> `sed -n '1p' <file>` - Print first line only 

> `sed -n '1,5p' <file>` - Print the first 5 lines

> `sed 's/old-word/new-word/'` - Replace the old word with the new word (You can substitute the delimiter in front of the `s`)

> `sed 's/,$//'` - Replace the ending character only with a newline.

Reference : [Sed Tutorial](https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux)


- **Cut** (Used to extract a section from a line - But only support single character delimiter)
> `cut -f <field_number> -d "<delimiter used to seperate fields>"`

- **Awk** (Programming language designed for text processing)
> `awk -F "<delimiter>" '{print $<number of seperated item>}'`

> `awk -F "<delimiter>" '{print "Your_text" $<field1> "Your_text" $<field2>}'` - To add optional strings to the output

- **Tr** (Used to translate characters into another, Lot more like sed)
> `tr '<character_to_replace>` '<replace_with_this_character>'`

## 3.5 Diffing

- `comm file1 file2` - Outputs 3 columns (1-lines unique to file1, 2-lines unique to file2, 3-lines common in both files

- `diff -c file1 file2` - Another tool to find the differences in two files.

- `vimdiff file1 file2` - More visual aided tool.

-

## 3.6 Managing Processes
- **Processes**

	- The kernel maintain information about each process to help keep things organized, and each process is assigned a number called **Process ID (PID)**

	- Foreground Processes(interactive processes) - These are initialized and controlled though a terminal session. There has to be a user connected to the system to start such processes. They haven't started automatically as a part of system functions/services.

	- Background Processes(automatic processes) - are processes not connected to a terminal. They don't expect any user input.

	- Daemons - These are special types of background processes that start at system startup and keep ruinning forever as a service. They don't die. Started as a system tasks. They can controlled by a user via the init process.

	- In the linux directory `/proc/` we could find out details about linux system kernel, processes and configuration parameters. It is not actually resides in hard drive that means that it exists only when the computer turned on and running which means exists in RAM.

For more indepth [linux processes](https://github.com/NashoNightmare/Linux-Kernel#linux-process-creation).

- **Jobs**

	- The linux shell also introduces the concept of **Jobs** to ease the user's workflow during the terminal session. A combination of processes (Such a composite command) is considered as a job in linux.
	
	- **Background Jobs (`bg`)**

		> `<command> &` - append '&' to run the command in background.
		
		> We could suspend a job by `Ctrl + Z`. Resume it in the background by using the `bg %<job_number>` command.

	- **Foreground Jobs (`fg` and `jobs`)**	

		> `jobs` - Returns the jobs that are running in the current shell.

		> `fg` - To bring back last stopped job to foreground. or `fg %<job_number>` to bring back specified process to the foreground(Stopped or background running).

- **Process Control**
	
	- **PS Command(The swiss army knife of Process Management)**

		> `ps -ef` - To see every processes system now runs. (`-e` - Every process , `-f` - Display full format)

		> `ps -fC <command_name>` - Select by command.

		> `kill <PID>` - Kill the process by process ID.
		
		> `ps aux` - `-a`: All tty with other users, `-u`: Show user id, `-x`: Processes without controlling ttys

		> `pstree -aclp` : More detailed process display, Grab the process id from here and grep it from traditional `ps aux` for gather more details.
			

## 3.7 File and Command Monitoring

Please refer to [Section 2.6](https://github.com/NashoNightmare/OSCP-Notes#26-other-useful-commands) to more commands.

- **Tail**
	
	> `tail -f <file_name>` - Live monitoring of a file that updates continuously.
	
	> `tail -n<number_of_lines> <file_name>` - Last desired number of lines of a file.

- **Watch**
	
	> `watch -n <interval_time_in_sec> "<command>"` - Runs a command after specified interval and updates the terminal.

## 3.8 Downloading Files

- **Wget**

	> `wget -O <specified_name_to_be_saved> <url_for_the_file>` - Downloads files using HTTP/HTTPS/FTP protocol.

- **Curl**

	Used to transfer data to or from a server using a host of protocols including IMAP/S, POP3/S, SCP, SFTP, SMB/S, SMTP/S, TELNET,TFTP, and others. Can use this to download or upload files and build complex requests.

	For man pages : [Curl](https://curl.se/docs/manpage.html)

	> `curl -o <save_as> <url_to_the_file>` - Equivalent to the wget command.

	> You can specify multiple URLs or parts of URLs by writing part sets within braces and quoting the URL as in: `http://site.{one,two,three}.com`

	> You can get sequences of alphanumeric series by using [] as in : `ftp://ftp.example.com/file[1-100].txt`, `ftp://ftp.example.com/file[a-z].txt`, `ftp://ftp.example.com/file[001-100].txt`(Leading zeros)

	> `curl -X <request> <url>` - Make requests for specified url.

- **Axel**

	Download accelerator that transfers a file from a FTP or HTTP server through multiple connections. This tool has a vast array of features, but the most common is -n, which is used to specify the number of multiple connections to use. 

	> `axel -a -n 20 -o <save_as> <url_to_the_file>` - `-a` for more concise progress indicator, `-n` for number of multiple connections to use. 
