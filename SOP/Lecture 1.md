1. What is Linux?
2. History of Linux


(msh = linux server)
msh.pjwstk.edu.pl


WSL: Windows Services for Linux (An interim layer allowing 
you to execute Linux binaries directly to Windows.)

Live! Linux/Live Linux (A live environment of Linux installed to memory stick)

HW -> Experiment with Linux. Install Linux on some device and send a screenshot to the professor

Create a bunch of directories/directory tree in one line.

tut1/A/B/C/D/E/F/G/H/I
mkdir --parents tut1/A/B/C/D/E/F/G/H/I

SSH: Secure Shell Protocol (both sides, the client and host, 
exchange certificates to proceed with communication)


# Common commands
- echo: Prints a line of text straight to the command line interface.
	- > file: Puts text in a file.
- cat .txt: Print text from file.
- mkdir: Make a directory/folder.
- rm: Removes a file
	- -r, --recursive: Removes a directory and their contents recursively.
- mv file file2: Renames / moves file to file2.
- cp a b: Copies files.
- pwd: Print (current) working directory.
- (#) (appended after command): Comment
- ls: List directory contents.
	- -a: List all, including hidden files (. and ..). The one dot is the current directory, the double is..?
	- -d: Lists only directory without the contents.
	- -?:
	- -t: Sorts by time of file modification, newest first.
	- -r, --reverse: Sorts order in reverse.
	- -R, --recursive: List current directory as well as its subdirectories (recursively).
	- -l: List one file/directory per line.
- source: Evaluates a file/resource as a Tcl script
- cd: Change directory. "cd" alone goes back to the home directory.
	- -: Goes back one step.
	- ..: Goes to the "home" directory.
(Takes contents of a specified file and passes it to the Tcl interpreter.)
- man/info: Displays information about the specified command.
- touch: Create a file.
- clear: Clears console output.
- history: Lists all the previously executed commands.
	- | more: Shows a bigger commmand history
	- | less: Controllable command history list
- *: Wildcard


- Arrow Up/Down: Sift through previously executed commands
- Highlight text to Right click: Copy and paste text from the terminal into the field.
- Tab: Completes inputted text if a file/directory is found.
- Ctrl + C: Quit executed command.

$PATH: Stored environment variables that the operating system can load/execute anywhere.

Useful combos
- ls -ld */: Lists only directories in the current working directory.
-	rm directory/*
	rmdir directory
	(Another way to remove dir)
