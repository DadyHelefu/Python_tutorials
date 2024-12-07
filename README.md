# Bash_tutorials

## Shell Prompt
### The prompt, $, which is called the command prompt, is issued by the shell.Shell reads your input after you press Enter.A simple example of the date command, which displays the current date and time, $date
```
date
```
### Output
### Thu Dec  5 02:53:12 PM EAT 2024

## Shebang
### Assume we create a demo.sh script. Note all the scripts would have the .sh extension. Before you add anything else to your script, you need to alert the system that a shell script is being started. This is done using the shebang construct.
```
#!/bin/bash
```

### Save the above content and make the script executable 
```
chmod +x demo.sh
```
### Alternatively
```
chmod 755 demo.sh
```
### After, the file is ready to be executable
```
./demo.sh
```

## Shell comments
###You can put your comments in your script as follows
```
#!/bin/bash

# Author : Zara Ali
# Copyright (c) Tutorialspoint.com
# Script follows here:
pwd
```

## Extended shell scripts
### Shell scripts have several required constructs that tell the shell environment what to do and when to do it. Of course, most scripts are more complex than the above one.The following script uses the read command which takes the input from the keyboard and assigns it as the value of the variable PERSON and finally prints it on STDOUT
```
#!/bin/sh

# Script follows here:

echo "What is your name?"
read PERSON
echo "Hello, $PERSON"
```

## Variables
### Defining Variables
### Variables are defined as follows 
### variable_name=variable_value
### For example, NAME="Dady Helefu"

###Accessing values
### To access the value stored in a variable, prefix its name with the dollar sign ($)
```
#!/bin/sh

NAME="Dady Helefu"
echo $NAME
```
### Output
### Dady Helefu

## Read-only variables
### Shell provides a way to mark variables as read-only by using the read-only command.
### Example
```
#!/bin/sh

NAME="Dady Helefu"
readonly NAME
NAME="Qadiri"
```
### Output
###/bin/sh: NAME: This variable is read only.

### Command line Arguments
### The command-line arguments $1, $2, $3, ...$9 are positional parameters, with $0 pointing to the actual command, program, shell script, or function and $1, $2, $3, ...$9 as the arguments to the command.
```
#!/bin/sh

echo "File Name: $0"
echo "First Parameter : $1"
echo "Second Parameter : $2"
echo "Quoted Values: $@"
echo "Quoted Values: $*"
echo "Total Number of Parameters : $#"
```
### Output
### File Name : ./test.sh
### First Parameter : Zara
### Second Parameter : Ali
### Quoted Values: Dady Helefu
### Quoted Values: Dady Helefu
### Total Number of Parameters : 2

## Special Parameters $* and $@
### There are special parameters that allow accessing all the command-line arguments at once. $* and $@ both will act the same unless they are enclosed in double quotes, "".Both the parameters specify the command-line arguments. However, the "$*" special parameter takes the entire list as one argument with spaces between and the "$@" special parameter takes the entire list and separates it into separate arguments.
```
#!/bin/sh

for TOKEN in $*
do
   echo $TOKEN
done
```
### Output
### Dady Helefu 20 Years Old
### Dady
### Helefu
### 20
### Years
### Old

## Defining Array Values
### If you are using the bash shell, here is the syntax of array initialization
```
array_name=(value1 value2 ... valuen)
```
### For example
### myarray=(23 4 6 15 5 7)
### Accessing individual elements
```
echo ${myarray[0]}
```
### Prints 23
```
echo ${myarray[2]}
```   
### Prints 6

### Using variables as index
``` 
index=4
echo ${myarray[$index]}
```   
### Prints 5

### Accessing all elements
```
myarray=(23 4 6 15 5 7)
echo ${myarray[*]}
```    
### Prints 23 4 6 15 5 7

```
echo ${myarray[@]}
```
### Prints 23 4 6 15 5 7

# Accessing first and last elements
```
echo ${myarray[0]}
```
### Prints 23

```
echo ${myarray[-1]}
```   
### Prints 7

##Arithmetic operations
### The following arithmetic operators are supported by Bourne Shell.Assume variable a holds 10 and variable b holds 20

### Operator vs Description
>+ (Addition)_Adds values on either side of the operator Example `expr $a + $b` will give 30
>- (Subtraction)_Subtracts right hand operand from left hand operand Example `expr $a - $b` will give -10
>* (Multiplication)_Multiplies values on either side of the operator Example `expr $a \* $b` will give 200
>/ (Division)_Divides left hand operand by right hand operand Example	`expr $b / $a` will give 2
>% (Modulus)_Divides left hand operand by right hand operand and returns remainder Example `expr $b % $a` will give 0
>= (Assignment)_Assigns right operand in left operand Example a = $b would assign value of b into a
>== (Equality)_Compares two numbers, if both are same then returns true.Example [ $a == $b ] would return false.
>!= (Not Equality)_Compares two numbers, if both are different then returns true.Example [ $a != $b ] would return true.

## Relational operations
### Bourne Shell supports the following relational operators that are specific to numeric values. These operators do not work for string values unless their value is numeric.Assume variable a holds 10 and variable b holds 20

### Operator vs Description
>-eq_Checks if the value of two operands are equal or not; if yes, then the condition becomes true. Example [ $a -eq $b ] is not true.
>-ne_Checks if the value of two operands are equal or not; if values are not equal, then the condition becomes true. Example [ $a -ne $b ] is true.
>-gt_Checks if the value of left operand is greater than the value of right operand; if yes, then the condition becomes true. Example [ $a -gt $b ] is not true.
>-lt_Checks if the value of left operand is less than the value of right operand; if yes, then the condition becomes true.Example [ $a -lt $b ] is true.
>-ge_Checks if the value of left operand is greater than or equal to the value of right operand; if yes, then the condition becomes true.Example [ $a -ge $b ] is not true.
>-le_Checks if the value of left operand is less than or equal to the value of right operand; if yes, then the condition becomes true.Example [ $a -le $b ] is true.

## File Test Operators
### Assume a variable file holds an existing file name "test" the size of which is 100 bytes and has read, write and execute permission

###Operator vs Description
>-b file_Checks if file is a block special file; if yes, then the condition becomes true. 	[ -b $file ] is false.
>-c file_Checks if file is a character special file; if yes, then the condition becomes true. 	[ -c $file ] is false.
>-d file_Checks if file is a directory; if yes, then the condition becomes true. 	[ -d $file ] is not true.
>-f file_Checks if file is an ordinary file as opposed to a directory or special file; if yes, then the condition becomes true. 	[ -f $file ] is true.
>-g file_Checks if file has its set group ID (SGID) bit set; if yes, then the condition becomes true. 	[ -g $file ] is false.
>-k file_Checks if file has its sticky bit set; if yes, then the condition becomes true. 	[ -k $file ] is false.
>-p file_Checks if file is a named pipe; if yes, then the condition becomes true. 	[ -p $file ] is false.
>-t file_Checks if file descriptor is open and associated with a terminal; if yes, then the condition becomes true. 	[ -t $file ] is false.
>-u file_Checks if file has its Set User ID (SUID) bit set; if yes, then the condition becomes true. 	[ -u $file ] is false.
>-r file_Checks if file is readable; if yes, then the condition becomes true. 	[ -r $file ] is true.
>-w file_Checks if file is writable; if yes, then the condition becomes true. 	[ -w $file ] is true.
>-x file_Checks if file is executable; if yes, then the condition becomes true. 	[ -x $file ] is true.
>-s file_Checks if file has size greater than 0; if yes, then condition becomes true. 	[ -s $file ] is true.
>-e file_Checks if file exists; is true even if file is a directory but exists. 	[ -e $file ] is true.

## Loops
### While loop

>Basic syntax
```
#!/bin/bash
while [condition];do
  command to execute while the condition is true.
done
```

>Example
```
count=1
while [ $count -le 5]; do
	echo "count:$count"
	((count++))
done
```
###Output
>count:1
>count:2
>count:3
>count:4
>count:5

### Until loop
### It is the opposite of the while loop
### Example
```
#!/bin/bash
number=1
until [ $number -ge 10 ]; do
	echo "$number"
	number=$((number+1))
done
```
### Output
>1
>2
>3
>4
>5
>6
>7
>8
>9

### For loop
### Basic syntax
```
for variable in list; do
	command to execute
done
```

### Example
```
for item in apple banana cherry; do
	echo "I like $item"
done
```
### Output
>I like apple
>I like banana
>I like cherry

### Note, this is only the basics of bash scripting 
