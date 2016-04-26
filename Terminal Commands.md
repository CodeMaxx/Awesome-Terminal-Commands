Some commands can be found in the `bin` directory.

`ls` - list files

`cd <path>` -> change directory
(`cd ..` -> takes to parent directory
 `cd` -> takes to user directory[denoted by ~]
 `cd -` -> takes to the previous directory we were in)

- **Trivia:** `user` directoty is present in the `home` directory which is present in the `root` directory. Then there is no upper directory.

`pwd` - print which directory

`^` symbol is used for representing 'ctrl'  ... e.g. `^C` = ctrl key + c

`touch <filename>`- creates a new file with any extension we want.

- **Trivia:** Some text editor like **nano** ,**vim** and **emacs** can be used to edit the code on the terminal itself.(writing `nano hello.cpp` opens file `hello.cpp` in terminal)

`rm` - used to remove a file.
`rm -r` - used to remove a directory.
`mkdir` - makes a directory
`rmdir` - removes an empty directory

`grep <text to search> <files to search in>`

`clear` or `^l` - scrolls down to an empty screen

`reset` - change terminal to default settings

`find <query>` - finds files and directories with name `query` in the current directory and its subdirectories
`find -d <query>` - looks for a directory with name `query`
`find -f <query>` - looks for a file with name `query`

`history` - shows all typed commands history

`!<text>` - repeats a previous command in history which started with 'text'

`man <command>` - shows manual for that command. Manual contains all the flags realated to that command.

`.` - refers to current directory
`..` - refers to parent directory

- **Trivia:** Files with file names starting with `.` are hidden.

`echo "hello"` - prints hello on the terminal

`>` - used to store the output of a task in some file(overwrites if file with same name there) rather than displaying it on the terminal.
`>>` - same task as `>` but does not overwrites just appends to the file with the same name.

`cat` - used to open a file in terminal in read-only format

`|` - piping is used to give the output of a command as input to another command ..for e.g `history | grep "find"` will search for "find" in the output of `history`

"Flags"

`-f` forcefully do a task i.e. without asking for confirmation
`-r` recursively do a task(looks in subdirectories too)
