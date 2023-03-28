# Lecture 2


## Other useful commands
- which: Locates the directory of the command
- whoami: Displays login name of the user inputting this command.
- who: Shows who's currently logged in.
- ... | wc: Counts words/lines/byte contents. Could be used to count entries.
	- --lines, -- bytes, --chars, --words: Data type of the counter.
- head: Prints the first 10 lines.
	- --lines=x (x is positive integer): Prints the first x lines.
- tail: Prints the last 10 lines.
	- --lines=x: Prints the last x lines.
- cut: Removes sections from each line
	--characters=a-b, a-b is a range: 
	--fields=
	--delimeter=
	--only-delimited:
- tr: Translates or removes characters.
	--delete: deletes characters in SET1.
	--squeeze-repeats: Replaces repeated occurences with only one occurrence.
- grep: Prints lines that matches a pattern.
	.[12345...]: matches any character
	--invert-match: negation
	--color: Highlights the matched expression. Useful for debugging errors in conditions.
- chmod: Changes file mode bits

Print the 13th and 14th line.
--
who | head --lines 14 | tail --lines=2


To get the count of a text file...

wc "Lecture 1.txt" --bytes
2484 Lecture 1.txt

...Without the string part...
cat "Lecture 1.txt" | wc --bytes








s26136@msh:~/Class activities/SOP$ ls -l
total 92
drwx------ 2 s26136 Domain Users     0 Mar 10 20:07 A
-rwx------ 1 s26136 Domain Users 80852 Mar 10 20:08 Assignment mkdir.png
-rwx------ 1 s26136 Domain Users  2484 Mar 10 19:51 Lecture 1.txt
-rwx------ 1 s26136 Domain Users  1260 Mar 17 11:27 Lecture 2.txt
-rwx------ 1 s26136 Domain Users  1302 Mar 11 20:10 man.txt

d: directory
-: file
rwx: read/write execution rights






Practice and learn RegEx