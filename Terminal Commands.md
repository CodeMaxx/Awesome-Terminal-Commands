Some commands can be found in the `bin` directory.

`ls` - list files

`cd <path>` -> change directory<br/>
(`cd ..` -> takes to parent directory<br/>
 `cd` -> takes to user directory[denoted by ~]<br/>
 `cd -` -> takes to the previous directory we were in)<br/>

- **Trivia:** `user` directory is present in the `home` directory which is present in the `root` directory. Then there is no upper directory.

`pwd` - print working directory

`^` symbol is used for representing 'ctrl'  ... e.g. `^C` = ctrl key + c

`touch <filename>`- creates a new file with any extension we want.

- **Trivia:** Some text editor like **nano** ,**vim** and **emacs** can be used to edit the code on the terminal itself.(writing `nano hello.cpp` opens file `hello.cpp` in terminal)

`rm` - used to remove a file.<br/>
`rm -r` - used to remove a directory.<br/>
`mkdir` - makes a directory<br/>
`rmdir` - removes an **empty** directory<br/>

`grep <text to search> <files to search in>`

`clear` or `^l` - scrolls down to an empty screen

`reset` - change terminal to default settings

`find <query>` - finds files and directories with name `query` in the current directory and its subdirectories<br/>
`find -d <query>` - looks for a directory with name `query`<br/>
`find -f <query>` - looks for a file with name `query`<br/>

`history` - shows all typed commands history

`!<text>` - repeats a previous command in history which started with 'text'

`man <command>` - shows manual for that command. Manual contains all the flags realated to that command.

`.` - refers to current directory<br/>
`..` - refers to parent directory<br/>

- **Trivia:** Files with file names starting with `.` are hidden.

`echo "hello"` - prints hello on the terminal

`>` - used to store the output of a task in some file(overwrites if file with same name is present) rather than displaying it on the terminal.<br/>
`>>` - same task as `>` but does not overwrites just appends to the file with the same name.<br/>

`cat` - used to open a file in terminal in read-only format

`|` - piping is used to give the output of a command as input to another command ..for e.g `history | grep "find"` will search for "find" in the output of `history`

`<command> | tee <filename>` - used to show output of `command` on terminal as well as writing the output to a file `filename`.<br/>

##### Some common network debugging commands <br/>
`ifconfig` - when used without any flags, used to display the status of all active network interfaces.<br/>

`iwconfig` - similar to `ifconfig`, but used for wireless network interfaces. <br/>

##### Flags

`-f` forcefully do a task i.e. without asking for confirmation<br/>
`-r` recursively do a task(looks in subdirectories too)


 subl <filename> : opens a file with filename in sublime text.
 gedit <filename> : opens a file with filename in gedit 
