```bash
# Equivalent commands to find java and mpg files
find . -name "*.java" -type f -o -name "*.mpg" -type f

find . -type f \( -name "*.java" -o -name "*.mpg" \)
```

```bash
# Find empty files
find . -type f -empty
```

```bash
# [ ] <-- these square brackets are a shortcut for testing the condition (man test for more info)

if ! [ -s a.java ]; then 
	echo empty; 
fi
```

```bash
# Stores result of the command in one line. Finds java files.
list=`find . -name "*.java" -type f`

# Modern way of doing it
list2=$(find . -name "*.java" - type f)

for file in $list;
do
	echo "Found file: " $file;
done
```

```bash
# Prints files and folders in the current directory. Incrementing the -maxdepth by one will result in printing subdirectories. 
find . -maxdepth 1
```


>[!What is a basename and a dirname?]-
>
> The basename command strips any "path" name components from a filename, leaving you with a "pure" filename.

```bash
# Functions

# This will print all of the supplied arguments and then the first argument. (e.g. John Doe and then John).
function hello () {
	echo '$@=' $@
	echo Hello $1
	return 0
}

# returning a non-zero number means there was an error

# this will execute the function because it was already defined.
hello John Doe
```

Functions can have local variables, or variables that are not affected by the boundaries of the function. They have to be declared with the keyword `local` first and then defined.

```bash
function test () {
	local var
	var

}
```

pos integer, result is fibonnaci n

Fibonnaci: Fn-2 + Fn-1

```bash
function fibo () {
	local n1
	local n2
	local n3
	local counter
	n1=0
	n2=1
	

	while ((counter < $1))
	do
		echo $n1 
		n3=(($n1+$n2))
		n1=$n2
		n2=$n3
		((counter++))	
	done
}
```