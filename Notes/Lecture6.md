

Read the inpread -p


Match only numbers
```bash
echo $a | grep -E '^[0-9]+'
```

Same as before, but matching happens first
```bash
# Single quotes not needed
if [[ $a =~ ^[0-9]+$ ]]; 
	then echo "Matching!"; 
	else echo "No match"
fi
```

## Arrays
```bash
array=(a1 a2 a3)

echo ${array[0]} # Prints a1
echo ${#array[@]} # Iterates over the entire array
echo ${#array[@]} # Array length in positive integers
echo ${arr[-1]} # Prints the last element of the array

# Suppose the user only inputs positive integer numbers.
secondArr=(a4 a5 a6)
INPUT="USER INPUT"
read -p "Reading input: " INPUT
echo ${arr[INPUT-1]} # Prints the nth element relative to user input
```


# Shift

# Substring
```bash
a=ABCDEF
index=4
length=1

echo ${a:index:length} # Prints E

# Prints no. of characters
echo -n $a | wc -c
echo ${#a} 
```