# Unix Terminal Commands for Beginners

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

`sudo <command>` - Run the command as superuser.

`!<text>` - repeats a previous command in history which started with 'text'<br>
`!!` - repeats the previous command<br>
`sudo !!` - repeats the previous command as superuser.

`whoami` -  gives the username of the current user.<br/>
`sudo su <username>` - Used to switch to a different user. This prompts for the password of the user you switch to.

- **Trivia:**`sudo` stands for `SUperuser DO` and `su` stands for `Switch User`.

`man <command>` - shows manual entry for the command. Manual contains all the flags realated to that command and their use.

`time <command>` - gives the time taken for the command to execute. Very useful when you want to find the execution time of your programs.

`diff [file1] [file2]` - compares the two files line by line. Usually used to compare ideal output and user-generated output.<br>
`diff -z [file1] [file2]` - Ignores trailing-whitespaces while comparing the two files

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

##### Common Flags

`-f` forcefully do a task i.e. without asking for confirmation<br/>
`-r` recursively do a task(looks in subdirectories too)<br/>
`-o <filename>` - stores the output with a personalised filename rather than the default filename. For e.g. `g++ -o myfile program.cpp` will generate an executable with the name `myfile` rather than the default `a.out`.

##### Opening files with common Text Editors

`<vim|vi|nano|emacs> <filename>` : opens a file in the respective text editor inside the terminal.<br/>
`gedit <filename>` : opens a file with filename in Gedit .
`subl <filename>` : opens a file with filename in Sublime Text.<br/>
`subl <foldername>`: Opens the entire folder in Sublime Text. Very helpful when you are working on projects with multiple file.

##### Running Scripts

`sh myscript` - To run a non-executable `sh` script.<br/>
`bash myscript` - To run a non-executable `bash` script<br/>
`./<location/of/executable>` - Just type the file location to run an executable file.

##### Aliases

An alias is a word assigned to a statement, and acts as a keyboard shortcut.

`alias py='python'` - would pass `python` whenever `py` is entered.

This alias lasts as long as the terminal is running. To create a permanent alias, append this line to `~/.bash_profile` or `~/.bash_aliases`.

`unalias <alias_name>` - Removes the alias. E.g. `unalias py` - After this `py` would not work as `python`.

##### Downloading

`Wget` and `cURL` are two great utilities for downloading stuff. They are a replacement to the Download Managers you must have used on Windows.

- **Trivia:** `cURL` is powered by `libcurl` - a cross-platform library with a stable API that can be used by each and everyone. `Wget` on the other hand is command line only. There's no library.

`wget <url_to_download>` - Downloads the file at the specified url.<br/>
`wget -c <url_to_download>` - Resumes an incomplete download. Very helpful when a large file download stops due to some error.<br/>
`wget --tries=100 <url_to_download>` - Set the retry download attempts. This is very useful when the download file is large and the internet connection has problems.

- **Trivia:** `wget` does 20 retries by default.

`wget -i <download_list_file.txt>` - For Multiple downloads. Downloads all the files/URLs mentioned in file.<br/>
`wget --recursive --page-requisites --html-extension --convert-links --no-parent <URL>` - Use this command to download the entire website so that you can view it offline.<br/>
- --recursive: download the entire Web site.
- --page-requisites: get all the elements that compose the page (images, CSS and so on).
- --html-extension: save files with the .html extension.
- --convert-links: convert links so that they work locally, off-line.
- --no-parent: prevents wget from downloading anything from the folders beneath the folder you want to acquire.

- **Trivia:** `cURL` supports more protocols and authentication methdods than `Wget` and is almost always pre-installed on the OS. `Wget` on the other hand is famous because of its ability to download an entire website for offline view.

`curl -O <url_to_download>` - Downloads the file at the specified url.<br/>
`curl -O <URL1> -O <URL2>` - Downloads files at both urls.<br/>
`curl -C - -O <url_to_download>` - Resumes an incomplete download.

- **Trivia:** `cURL` can also be used to upload files to `ftp` server. Use `curl -u <ftpuser>:<ftppass> -T <myfile> <ftp://ftp.testserver.com>`

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

##### Extracting .tar.gz files

`tar -xvzf <file.tar.gz>` - used to extract the .tar.gz file<br>

#### Compressing files to .tar.gz

`tar -cvzf <tarballname.tar.gz> <item_to_compress_1> <item_to_compress_2>` - used to compress any number of files into a .tar.gz compressed archive.<br>

-tarball.tar.gz: This is the name of the final compressed archive.

-x: tar can collect files or extract them. x does the latter.<br>
-c: Collects files to be compressed<br>
-v: makes tar talk a lot. Verbose output shows you all the files being extracted.<br>
-z: tells tar to decompress the archive using gzip<br>
-f: this must be the last flag of the command, and the tar file must be immediately after. It tells tar the name and path of the compressed file.

##### Process Management

`top` - displays processor activity in real time.

`ps` returns the snapshot of current processes.<br>
`ps -e` returns every process running on the system<br>
`ps -u <useraccount>` returns list of processes running on user account.<br>
`ps -u <useraccount> | grep <Application>` - fetches all processes of "Application"

The left most number returned by the `ps` command is called the Process ID (PID).
A particular process can be terminated using `kill`

`kill <PID>` - kills the process having PID as that entered.<br>
`kill -9 <PID>` - performs a violent kill<br>
`killall <processname>` - kills all instances of processname
