> creates or overwrites
>> creates or appends

read x: inputs something in x

a=`cat data.txt`: assigns value of the output of the command.

echo $a | xargs -n1: Prints each word in a new line.


$?: returns exit status (use echo $? to get the exit value)
	- exit status 0: Correct execution of previous command
	- exit status number bigger than 0: Error

test: check file types and compare values

while read x ; do echo $x $line; done < data.txt: reads a text file line-by-line

$PATH: the location of the environment variables

$@: supply of arguments


echo "List of args: " %@
echo "# of args = " $#

for arg in $@
do
	echo $arg
done

^ loops through lsit of arguments supplied

How to parse string to int?
(())


sum=0

for arg in $@
do
	((sum=sum+arg))
done

echo $sum

^ an addition calculator

if(($#>2))
then
	echo $1
	echo $2
	echo $3
fi
echo '$0 = ' $0


HW: Calculate the min and max from the arguments supplied