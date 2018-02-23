# *nix Terminal Commands for Beginners


- Software Specific Commands
 - [nmap](https://github.com/CodeMaxx/Terminal-Commands-Beginner/blob/master/nmap.md)
 - [sqlmap](https://github.com/CodeMaxx/Terminal-Commands-Beginner/blob/master/sqlmap.md)
 
<hr>
 
### General
 
`ls` - lists files<br>
- **Important flags**<br>
`-a` - display hidden files<br>
`-R` - recursively displays files<br>
`-l` - displays extra details like size, owner, group, date the file was last modified and permissions<br/>

`tree <path>` - display files and directories as a tree structure.<br/>

`cd <path>` - change directory to `path`<br/>
- Here `path` may be relative or absolute.

(`cd ..` - takes to parent directory<br/>
 `cd` - takes to `<user>` directory[denoted by `~`]<br/>
 `cd /` - takes to `root` directory[denoted by `/`]<br/>
 `cd -` - takes to the previous directory you were in)<br/>

- **Trivia:** `user` directory is present in the `home` directory which is present in the `root` directory(denoted by `/`). [`/home/<user>` in Linux and `Users/<user>` in macOS] Then there is no further upper directory after `root`.

`pwd` - print working directory. Prints absolute path to current directory.

`pushd dirname` changes directory to dirname, and pushes it onto the head of the directory stack.<br/> 
`popd` changes directory to the directory at the head of the directory stack, and pops it off.<br/>
`dirs` see the contents of the directory stack.<br/>

`^` symbol is used for representing 'ctrl' ... e.g. `^C` = ctrl key + c

`touch <filename>`- creates a new file with any extension we want.

**Note:** `touch` is a much more advanced command and can be used to change the file access and modification times. For more info see `man touch`.

`rm <filename>` - removes a file.<br/>
`rm -r <directory>` - recursively removes all files in a directory. Then removes the empty directory.<br>
**Note:** This command might ask you for permission for every file that it deletes. To prevent this use `-f`(force) flag.<br>
`mkdir <dir_name>` - makes a new directory<br/>
`rmdir <dir_name>` - removes an **empty** directory<br/>

`cp /path/to/file /path/to/copy/to` - used to copy file.<br>
(Use `cp -r` to copy a directory recursively)<br>
`mv /old/path/to/file /new/path/to/file` - used to move file.

- **Trivia:** `mv [old_filename] [new_filename]` is the best method to rename a file.

`grep [flag] <text to search> <files to search in>`<br>
- **Important flags**<br>
`-i` - Performs case insensitive matching<br>
`-r` - Helps to search recursively through a directory<br>
`-n` - Outputs the line number along with the file name in which the search text is present<br>
`-l` - Outputs the name of the files in which the search text is present<br>
`-L` - Outputs the name of the files in which the search text is not present<br>
`--color=auto` - Highlights the search text in the output

`cut` - cuts out selected portions of each line from file and writes them to the standard output.<br>
`cut -c 2-5 file` - cut characters 2 to 5 from each line of file<br>
`cut -d"x" -f 1 file` - returns each part of every line before first occurrence of 'x' (-d is delimiter and -f is field)

`wc filenames` - used to find out number of newline count, word count, byte and characters count in a files<br/>

- **Important flags**<br/>
`-l` - Prints the number of lines in a file.<br/>
`-w` - prints the number of words in a file.<br/>
`-c` - Displays the count of bytes in a file.<br/>
`-m` - prints the count of characters from a file.<br/>
`-L` - prints only the length of the longest line in a file.<br/>

`clear` or `^l` - scrolls down to an empty screen<br/>

`reset` - initialises terminal variables to thier default value<br/>

`passwd <username>` - Change password for a user<br/>

`find <query>` - finds files and directories with name `query` in the current directory and its subdirectories<br/>
`find -d <query>` - looks for a directory with name `query`<br/>
`find -f <query>` - looks for a file with name `query`<br/>

`history` - shows all typed commands history<br>
`history n` -shows last n commands<br>

`gnome-terminal` - opens a new terminal window in the same directory of parent terminal<br>

`exit` - exit terminal session<br/>
**Note:** If you are inside virtual terminals like asciinema, tmux, screen, ssh and so on then upon exiting you will only exit virtual terminal session rather than exiting real terminal session.<br/>

`sudo <command>` - Run the command as superuser(a.k.a. root)<br>

`!<text>` - repeats a previous command in history which started with 'text'<br>
`!!` - repeats the previous command<br>
`sudo !!` - repeats the previous command as superuser

`whoami` - gives the username of the current user.<br>
`su <username>` - Used to switch to a different user. This prompts for the password of the user you switch to.<br>
`sudo -i` - Switch to `root` user. This user has complete access to all files.

**Note:** While `sudo -i` will ask you for your login password to become superuser, `su root` will ask for the root password. These are not the same. You may have to set or change the root password by running `sudo passwd root` first.

- **Trivia:**`sudo` stands for `SUperuser DO` and `su` stands for `Substitute User`.

`gksudo` - is used to pop up the `sudo` password prompt in a GUI window. <br/>

`man [section_number] <command>` - shows manual entry for the command. Manual contains all the flags related to that command and their use. Manpages have different sections. Refer to the list below:

`apropos <argument>` - find the argument in all man pages.<br>

```
MANUAL SECTIONS
    The standard sections of the manual include:

    1      User Commands
    2      System Calls
    3      C Library Functions
    4      Devices and Special Files
    5      File Formats and Conventions
    6      Games et. al.
    7      Miscellanea
    8      System Administration tools and Daemons

    Distributions customize the manual section to their specifics,
    which often include additional sections.
```

`time <command>` - gives the time taken for the command to execute. Very useful when you want to find the execution time of your programs. This uses the `time` shell keyword<br/>

`/usr/bin/time <command>` - to use the "real" time command with all its flags and options. [Reference](https://askubuntu.com/questions/434289/why-doesnt-the-time-command-work-with-any-option)<br/>

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

`<output of some command> | more` - is similar to using `less`, but allows viewing one screen at a time.<br/>

- **Trivia:** All commands typed in the terminal are saved in `history` or the `.bash_history` file in the home directory.
`history | less` or `cat ~/.bash_history` will let you scroll through previously typed commands.

`sudo service <service_name> <option>` : manage services<br/>

**common services** - press tab to list all services in terminal after typing `sudo service `<br/>
`bluetooth`<br/>
`network`<br/>
`lightdm`<br/>
`network-manager`<br/>
`ssh`<br/>

**options**<br/>
`status`<br/>
`start`<br/>
`restart`<br/>
`stop`<br/>

<hr>

### Opening files with common Text Editors

`<vim|vi|nano|emacs> <filename>` : opens a file in the respective text editor inside the terminal.<br/>
`gedit <filename>` : opens a file with filename in Gedit .
`subl <filename>` : opens a file with filename in Sublime Text.<br/>
`subl <foldername>`: Opens the entire folder in Sublime Text. Very helpful when you are working on projects with multiple file.

<hr>

### Running Scripts

`sh [path/to/script]` - To run a non-executable `sh` script.<br/>
`bash [path/to/script]` - To run a non-executable `bash` script<br/>
`./<location/of/executable>` - Just type the file location to run an executable file.

<hr>

### Aliases

An alias is a word assigned to a statement, and acts as a keyboard shortcut.

`alias py='python'` - would pass `python` whenever `py` is entered.

This alias lasts as long as the terminal is running. To create a permanent alias, append this line to `~/.bash_profile` or `~/.bash_aliases`.

`unalias <alias_name>` - Removes the alias. E.g. `unalias py` - After this `py` would not work as `python`.

<hr>

### Downloading

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

<hr>

### Installation Commands

##### Debian, Ubuntu and other debian-based distros

**Note:** Installation/removal/modification of a package requires admin privilages.  Add `sudo` in the beginning of every such command

`apt-get install <package-name>` - Installs a package<br>
- **Important flags**<br>
`-y` - Replies **yes** to all confirmations `apt-get` asks for during install.

`apt-cache search <query>` - Searches package names and descriptions for the query string. Used to find the package-names.

`apt-get remove <package-name>` - Removes a package (but not the configuration files)

`apt-get autoremove` - Remove packages that were automatically installed to satisfy dependencies for some package and that are no more needed.

`apt-get purge <package-name>` - Removes a package (along with the configuration files)

`apt-get update` - APT keeps a local database on your hard drive with a list of all available packages and where to find them. This command explicitly updates the database.

`apt-get upgrade` - Installs newer versions of the packages.

##### Fedora, Red Hat and CentOS

`yum install <package-name>` - Installs a package

<hr>

### Changing Permissions

`chmod a+x file` - Grants execution permission to all users of a file.<br/>
`chmod a+w file` - Grants write permission to all users of a file.<br/>
`chmod a+r file` - Grants read permission to all users of a file.

This are just examples. `chmod` has a lot of different configurations for different kinds of permissions. For all details see its `man` page.

`chown -R <username> path/of/file/or/directory` - Gives the ownership of the file or all files in the directory and its subdirectories to the mentioned user.

<hr>

### Networking

`ifconfig` - when used without any flags, used to display the status of all active network interfaces.<br/>

`iwconfig` - similar to `ifconfig`, but used for wireless network interfaces. <br/>

`hostname` - used to display the system's DNS name. <br/>
`hostname -I` - used to display  all  network addresses of the host. <br/>

`ping [domain_name_or_ip_address]` - Used to ping a domain name or IP address continuously. It can be stopped by `^C`. Generally used to check if the server is up and responding.

`dig example.com` - Queries DNS servers for information. Gives back the `A` record which points the domain name to an IP address. Using the `+short` flag returns just the IP address linked to the domain name.

`+nocomments` – Turn off the comment lines<br/>
`+noauthority` – Turn off the authority section<br/>
`+noadditional` – Turn off the additional section<br/>
`+nostats` – Turn off the stats section<br/>
`+noanswer` – Turn off the answer section (Of course, you wouldn’t want to turn off the answer section)

`dig -x [IP address]` - Queries and returns a `PTR` record against the IP address queried. The PTR record helps in Reverse DNS Lookup i.e. it provides the domain name linked to an IP address. Example `dig -x 127.0.0.1 +short` returns `localhost.`.

- **Trivia:** When you reverse lookup an IP say 1.2.3.4, the PTR record for the domain name `4.3.2.1.in-addr.arpa`, more generally `reverse_ip.in-addr.arpa`. (in-addr -> Inverse Address. arpa -> Address and Routing Parameter Area)

- **Trivia:** The arpa top-level domain was the first domain installed in the Domain Name System (DNS).

`arp` - It manipulates or displays the kernel's <i>IPv4</i> network neighbour cache. It can add entries to the table, delete one, or display the current content.

- **Trivia:** ARP stands for Address Resolution Protocol.

`traceroute [IP address/ Domain name]` tracks the route packets taken from our computer on their way to a given host. It utilizes the IP protocol's <b>time to live</b> (TTL) field and attempts to elicit an `ICMP TIME_EXCEEDED` response from each gateway along the path to the host. This response contains the IP address of the gateway which are then listed as output on the terminal.<br/>
**Note:** You might see `*`(asterisk) instead of IPs sometimes. This means that the packet was not acknowledged and no response was sent before timeout. This is generally done purposefully to hide the identity of the servers.

`whois domain_name.com` - Generates a long list of output regarding the server registration.

`netstat` - The netstat command symbolically displays the contents of various network-related data structures. It helps answer the question “What in blazes is going on on my network?”. The columns present in the output are:

- `Proto` - tell us if the socket listed is [TCP](https://www.wikiwand.com/en/Transmission_Control_Protocol) or [UDP](https://www.wikiwand.com/en/User_Datagram_Protocol)<br>

- `Recv-Q` and `Send-Q` - tell us how much data is in the queue for that socket, waiting to be read (Recv-Q) or sent (Send-Q). In short: if this is 0, everything’s ok, if there are non-zero values anywhere, there may be trouble.<br>
- `Local Address` and `Foreign Address` - tell to which hosts and ports the listed sockets are connected. The local end is always on the computer on which you’re running netstat , and the foreign end is about the other computer (could be somewhere in the local network or somewhere on the internet).<br>
**Note:** The `Foreign Address` can be `localhost` sometimes. It means the computer is talking to itself over the network, so to speak. This is also known as `loopback`.<br>

- `State` - tells in which state the listed sockets are. The TCP protocol defines states, including “LISTEN” (wait for some external computer to contact us) and “ESTABLISHED” (ready for communication). The stranger among these is the “CLOSE WAIT” state shown by two sockets. This means that the foreign or remote machine has already closed the connection, but that the local program somehow hasn’t followed suit. Strange states and non-empty queues(non-zero values in `Send-Q` or `Recv-Q`) often go together.

<hr>

### Extracting compressed files

`tar -xvzf <file.tar.gz>` - used to extract the .tar.gz file<br>
`gzip -d <file_to_decompress>.gz` - used to extract the .gz file<br>
`gunzip <file_to_decompress>.gz` - used to extract the .gz file<br> 
`unzip <file.zip>` - used to extract the .zip file<br>
<hr>

### Compressing files

`tar -cvzf <tarballname.tar.gz> <item_to_compress_1> [item_to_compress_2]` - used to compress any number of files into a .tar.gz compressed archive.<br>

- tarball.tar.gz: This is the name of the final compressed archive.

`-x`: tar can collect files or extract them. x does the latter.<br>
`-c`: Collects files to be compressed<br>
`-v`: makes tar talk a lot. Verbose output shows you all the files being extracted.<br>
`-z`: tells tar to decompress the archive using gzip<br>
`-f`: this must be the last flag of the command, and the tar file must be immediately after. It tells tar the name and path of the compressed file.<br>

`gzip file1 file2 file3` - used to compress any number of files into .gz compressed format.<br>

- This method compresses each of the files separately and not into a single .gz archive.

`zip archive.zip file1 file2 file3` - used to compress any number of files into a .zip compressed archive.<br>
`zip -r archive.zip dir1 dir2 dir3` - used to compress any number of directories recursively into a .zip compressed archive.<br>

- archive.zip: This is the name of the final compressed archive.<br>

<hr>

### See Compressed file contents without extracting

`unzip -l archive.zip` - lists the contents of a ZIP archive.<br>
`tar -tf archive.tar.gz` - lists the contents of a tar.gz archive.<br>
`vim archive` - lists the contents of most types of archives.<br>

<hr>

### Process Management

`top` - displays processor activity in real time.

`ps` returns the snapshot of current processes.<br>
`ps -e` returns every process running on the system<br>
`ps -u <useraccount>` returns list of processes running on user account.<br>
`ps -u <useraccount> | grep <Application>` - fetches all processes of "Application"<br>
`pstree` display running processes as a tree

The leftmost number returned by the `ps` command is called the Process ID (PID).
A particular process can be terminated using `kill`

`kill <PID>` - kills the process having PID as that entered.<br>
`kill -9 <PID>` - performs a violent kill<br>
`killall <processname>` - kills all instances of processname

<hr>

### Secure SHell

SSH is some kind of an abbreviation of Secure SHell. It is a protocol that allows secure connections between computers.
ssh (SSH client) is a program for logging into a remote machine and for executing commands on a remote machine.<br>

`ssh <server's IP/Domain_name>` - connects to a server that supports ssh. Uses the username from your local machine<br>
`ssh <username>@<server's IP/Domain_name>` - specify a different username<br>
`ssh -p <port_number> <username>@<server's IP/Domain_name>` - specify a port. Default port is 22<br>

- **Important flags**<br>
`-4` - Forces ssh to use IPv4 addresses only<br>
`-6` - Forces ssh to use IPv6 addresses only<br>
`-A` - Enable forwarding of the authentication agent connection. This forwards the connection to your ssh agent to the remote computer<br>
`-q` - Quiet mode (Suppresses most warnings and diagnostic messages)<br>
`-V` - Display the version number<br>
`-v` - Verbose mode (Prints debugging messages about its progress)<br>
`-X` - Enables X11 forwarding which lets you run graphical applications remotely<br>
`-t` - Forces a tty allocation even if a command is specified. This can be used to execute shell commands on the remote machine<br>
`-Y` - Enables X11 connection forwarding and treats X11 clients as trusted.<br>

<hr>

### Cryptography

`md5sum <filename>` - compute and check MD5 message digest <br/>

`sha1sum <filename>` - compute and check SHA1 message digest<br/>
`sha224sum <filename>` - compute and check SHA224 message digest<br/>
`sha256sum <filename>` - compute and check SHA256 message digest<br/>
`sha384sum <filename>` - compute and check SHA384 message digest<br/>
`sha512sum <filename>` - compute and check SHA512 message digest<br/>

`base32 <filename>` - base32 encode/decode data and print to standard output<br/>
`base64 <filename>` - base64 encode/decode data and print to standard output<br/>

**Note:** By default base32/base64 will encode data. use `-d` flag to decode data<br/>

**Note:** Above mentioned commands takes file as input. To calcute hash of text directly use `echo -n "text" | {command}`. Use of `-n` flag is mandatory. Without it, your hash will be totally wrong since it includes the newline character.<br/>
