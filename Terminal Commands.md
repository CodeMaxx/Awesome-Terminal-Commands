Some commands can be found in the `bin` directory.

`ls` - list files<br>
`ls -a` - display hidden files and folders<br>
`ls -R` - provide a tree listing of directory structure.<br>
`ls -l` - displays extra details like size, user, date, permissions<br>

`cd <path>` -> change directory<br/>
(`cd ..` -> takes to parent directory<br/>
 `cd` -> takes to user directory[denoted by ~]<br/>
 `cd -` -> takes to the previous directory we were in)<br/>

- **Trivia:** `user` directory is present in the `home` directory which is present in the `root` directory. Then there is no upper directory.

`pwd` - print working directory

`^` symbol is used for representing 'ctrl'  ... e.g. `^C` = ctrl key + c

`touch <filename>`- creates a new file with any extension we want.

`rm` - used to remove a file.<br/>
`rm -r` - used to remove a directory.<br/>
`mkdir` - makes a directory<br/>
`rmdir` - removes an **empty** directory<br/>

`cp /loc1/file /loc2/file` - used to copy file from /loc1 to /loc2.<br>
`mv /loc1/file /loc2/file` - used to move file from /loc1 to /loc2.

- **Trivia:** `mv oldfilename newfilename` is the best method to rename a file.

`grep <text to search> <files to search in>`

`cut` - cuts out selected portions of each line from file and writes them to the standard output.<br>
`cut -c 2-5 file` - cut characters 2 to 5 from each line of file<br>
`cut -d"x" -f 1 file` - returns each part of every line before first occurance of 'x' (-d is delimiter and -f is field)


`clear` or `^l` - scrolls down to an empty screen

`reset` - change terminal to default settings

`find <query>` - finds files and directories with name `query` in the current directory and its subdirectories<br/>
`find -d <query>` - looks for a directory with name `query`<br/>
`find -f <query>` - looks for a file with name `query`<br/>

`history` - shows all typed commands history<br>
`history n` -shows last n commands

`!<text>` - repeats a previous command in history which started with 'text'<br>
`!!` - repeats the previous command<br>
`sudo !!` - repeats the previous command as sudo

`man <command>` - shows manual for that command. Manual contains all the flags realated to that command.

`.` - refers to current directory<br/>
`..` - refers to parent directory<br/>

- **Trivia:** Files with file names starting with `.` are hidden.

`echo "hello"` - prints hello on the terminal

`>` - used to store the output of a task in some file(overwrites if file with same name is present) rather than displaying it on the terminal.<br/>
`>>` - same task as `>` but does not overwrites just appends to the file with the same name.<br/>

`|` - piping is used to give the output of a command as input to another command ..for e.g `history | grep "find"` will search for "find" in the output of `history`

`<command> | tee <filename>` - used to show output of `command` on terminal as well as writing the output to a file `filename`.<br/>

`cat` - used to open a file in terminal in read-only format

- **Trivia:** Unless you have infinite scrolling turned on (available in Profile Preferences -> Scrolling tab of the terminal), there is a limit to how many lines you can see on the screen.

`<output of some command> | less` - allows the user to advance through the content by pressing SPACE, move backwards by pressing 'b' and quit using 'q'. Pressing ESC followed by SPACE allows you to scroll down one screen at a time.

Example: `cat file | less`

`<output of some command> | more` - is similar to using `less`, but allows viewing one screen at a time.

- **Trivia:** All commands typed in the terminal are saved in `history` or the `.bash_history` file in the home directory.
`history | less` or `cat ~/.bash_history` will let you scroll through previously typed commands.

##### Flags

`-f` forcefully do a task i.e. without asking for confirmation<br/>
`-r` recursively do a task(looks in subdirectories too)

##### Opening files with common Text Editors

`<vim|vi|nano|emacs> <filename>` : opens a file in the respective text editor inside the terminal.<br/>
`gedit <filename>` : opens a file with filename in Gedit .
`subl <filename>` : opens a file with filename in Sublime Text.<br/>
`subl <foldername>`: Opens the entire folder in Sublime Text. Very helpful when you are working on projects with multiple file.

##### Running Scripts

`sh myscript` - To run a non-executable `sh` script.<br/>
`bash myscript` - To run a non-executable `bash` script<br/>
`location/of/executable` - Just type the file location to run an executable file.

##### Aliases

An alias is a word assigned to a statement, and acts as a keyboard shortcut.

`alias py='python'` - would pass "python" whenever py is entered.

This alias lasts as long as the terminal is running. To create a permanent alias, append this line to `~/.bash_profile` or `~/.bash_aliases`

##### Changing Permissions

`chmod a+x file` - Grants execution permission to all users of a file.<br/>
`chmod a+w file` - Grants write permission to all users of a file.<br/>
`chmod a+r file` - Grants read permission to all users of a file.

This are just examples. `chmod` has a lot of different configurations for different kinds of permissions. For all details see its `man` page.

`chown -R <username> path/of/file/or/directory` - Gives the ownership of the file or all files in the directory and its subdirectories to the mentioned user.

##### Some common network debugging commands

`ifconfig` - when used without any flags, used to display the status of all active network interfaces.<br/>

`iwconfig` - similar to `ifconfig`, but used for wireless network interfaces. <br/>

`ping domain_name_or_ip_address` - Used to ping a domain name or IP address continuously. It can be stopped by `^C`. Generally used to check if the server is up and responding.

`dig example.com` - Queries DNS servers for information. Using the `+short` flag returns the IP address linked to the domain name.

`whois domain_name.com` - Generates a long list of output regarding the server registration.

##### Extracting .tar files

`tar -xvzf file.tar.gz` - used to extract the .tar.gz file<br>
-f: this must be the last flag of the command, and the tar file must be immediately after. It tells tar the name and path of the compressed file.<br>
-z: tells tar to decompress the archive using gzip<br>
-x: tar can collect files or extract them. x does the latter.<br>
-v: makes tar talk a lot. Verbose output shows you all the files being extracted.

##### Process Management

`ps` returns the snapshot of current processes.<br>
`ps -e` returns every process running on the system<br>
`ps -u <useraccount>` returns list of processes running on user account.<br>
`ps -u <useraccount> | grep <Application>` - fetches all processes of "Application"

The left most number returned by the `ps` command is called the Process ID (PID).
A particular process can be terminated using `kill`

`kill <PID>` - kills the process having PID as that entered.<br>
`kill -9 <PID>` - performs a violent kill<br>
`killall <processname>` - kills all instances of processname
