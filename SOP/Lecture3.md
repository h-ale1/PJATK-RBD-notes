## grep
	Count matching lines: --count
	 echo aabbccddaabbcc | grep --only-matching aa | wc --lines: Count number of matches rather than lines

## find: searches for files in a directory hierarchy
	find [path] [expression]

	{1..x}: Numbers from 1 to x, where x is any positive integer. Could also go through other alphanumeric chars (E.g. a..z)
	{txt, txt2}: Goes through files in adirectory


s26136@msh:~/Class activities/SOP/lec3$ echo ABC{1..3}.{txt,exe}
ABC1.txt ABC1.exe ABC2.txt ABC2.exe ABC3.txt ABC3.exe

	find . -type f -delete: Deletes files while retaining directories

	find . -name "*.exe": Finds files of type ".exe" with any name.
	find . -type f: Finds files.
	find . -type d: Find directories, including the hidden ".".
	find . -type d -name "*dir*": same as above, without the hidden ".".

## sort: sorts lines of text files
--numeric-sort: sorts numerical value
--random-sort: Sorts randomly by hash of keys
--reverse: Reverses the result
--key: Sort via key, specified by "KEYDEF"
--unique: omits dupes
--general-numeric-sort: compare using generic numerical value (e.g. 3e5 [3 x 10^5])
KEYDEF Field number 

## seq startnum stepnum maxnum: 

## uniq: removes duped data

## >: standard input
## 1>: standard output
## 2>: standard error

#variable
	a=something: a now contains string "something"
	echo $a: print a
learn variable manipulation on bash
#expr: does mathematical operations and outputs it. The value of variables do not change.
## echo `command`: Command execution is outputed. Command executes first and then echo outputs the result as a string.

## For loops

	for i in  1 2 3 aaa bbb 555sss ; do echo "i-$i"; done
	for ((i=0; i < 9; i++ )) do echo "i="$i; done

	Double braces (()): Bash interprets it as a command for arithmetics

## While loop
	i=0; while ((i <= 9)) ;  do echo i = $i; ((i++)) ; done

## If.. then.. else..
i=10
if test $i -eq 10 ; then echo OK; else echo not OK; fi
