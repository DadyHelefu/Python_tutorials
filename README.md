# Python_tutorials
## Printing text
##### Example

>print("Hello world")

>Hello world is a statement

>print is a name of a function

>"Hello world" is an argument

#### Two ways to run a script
>command line

>using text editor

## Print statement 
##### Example
```
print("Hello world")
```

##### Output

>Hello world

## Print quotes
##### Example
```
print("She said, 'Hello world'")
```

##### Output

>She said, 'Hello world'


## Comments
#### This is represented by a # sign
#### Importance of comments
>Helps in documentation of what the codeis doing

>Improves codes readability

>Helps in debugging

>Acts a reminder to update a documentation

## Splitting a statement
### Include a new line in the middle of the string
##### Example
```
print("Hello\nworld")
```

##### Output
>Hello
>world

### Insert a horizntal tab character
##### Example
```
print("Hello\tworld")
```

##### Output
>Hello	world

### Carriage return
#### To overwrite the context that was printed earlier on the line
##### Example
```
print("Hello\rworld")
```

##### Output
>world

## Storing strings in a variable
##### Example
```
my_dna="ATCG"
print(my_dna)
```
**We do not use quotation marks because they are built in**

## Concatenation
#### To stick together two strings using + sign
##### Example
```
my_dna="ATCG" + "GGCC"
print(my_dna)
```
##### Output 
>ATCGGGCC


## Length of a string
##### Example
```
dna_length=len("ATCG")
print(dna_length)
```
##### Output
>4

## Changing case
#### Use the lower() or upper()
##### Example 
```
my_dna="ATCG"
print(my_dna.lower())
```

##### Output
>atcg

## Replacement
#### Using replace() method
##### Example
```
protein="vlspd"
print(protein.replace"v","y")
```

##### Output
>ylspd

## Extracting part of string
#### EXtract the part of a string according to position, in python start counting position from 0 and -1 is for the last position.
##### Example
```
protein="vlspd"
print(protein[1:3])
```

##### Output
>ls

## Counting substring
#### Count() method is used to count the number of times a substring occurs in a string
##### Example
```
protein="vlspd"
print(protein.count("v"))
```

##### Output
>1

## Finding substring
#### Use find() method to find the location of the substring
##### Example
```
protein="vlspd"
print(protein.find("p"))
```

##### Output
>3
**If the answer is -1 means the substring doesnot exist**


## Reading files
#### Reading a text froma file, you use open function to read a file.
##### Example
```
my_file = open("dna.txt")
```

## Differentiating between file name, file object and file contents
### file name
#### The name or path of the file in the filesystem which used as identifier of the file.
##### Example
>file_name="dna.txt"

### file object
#### An object used to interact with the file (created by open()), which provides methods to manipulate the file (read,write etc)
##### Example
>file_obj=open("dna.txt", "r")

### file contents
#### The actual data (text, numbers, etc.) stored in the file.
##### Example
>file_contents=dna.txt.read()
>If the file contents inside can be printed "Hello, world!"

## Opening a file for writting
#### We can use two arguments where the second argument is a specially formatted string describing what we want to do to the file.
##### Example 
```
my_file=open("out.txt", "w")
my_file.write("Hello world")
```

## Closing a file
#### Close is the opposite of open but close is a method where as open is a function
##### Example
``` 
my_file=open("out.txt", "w")
my_file.write("Hello world")
my_file.close
```

## Paths and folders
#### You need to give a file path as the argument rather than a file name
##### Example
```
my_file=open("/home/dady/myfolder/myfile.txt")
```

## Concatenate two lists
#### Used to join lists
##### Example 
```
apes=["Homo sapiens","Pan troglodytes","Gorilla gorilla"]
monkeys=["Papio ursinus","Macaca mulatta"]
primates=apes + monkeys
print(primates)
```

##### Output
>['Homo sapiens', 'Pan troglodytes', 'Gorilla gorilla', 'Papio ursinus', 'Macaca mulatta']

## reverse list 
#### reverse() method is used to reverse the order of the elements in the list
##### Example 
```
ranks=["kingdom","phylum","class","order","family"]
ranks.reverse()
print(ranks)
```

##### Output
>['family', 'order', 'class', 'phylum', 'kingdom']


## sort list 
#### sort() method is used to sort the list elements in ascending or descending order.
##### Example 
```
ranks=["kingdom","phylum","class","order","family"]
ranks.sort()
print(ranks)
```

##### Output
>['class', 'family', 'kingdom', 'order', 'phylum']

## Writing loop
#### To write python's loop syntax
>for x in y

>where

>y=name of the list we want to process

>y=name we want to use for the current element each time round the loop(variable name)

#### Block of code refers to a group of statements that are executed together
#### Body of a loop refers to the block of code that is executed repeatedly during each iteration of the loop
##### Example
```
apes=["Homo sapiens","Pan troglodytes","Gorilla gorilla"]
for ape in apes:
...     print(ape)

```

##### Output
>Homo sapiens

>Pan troglodytes

>Gorilla gorilla


## Writing down functions
#### Function is a self contained block of code designed to perform a specific task. It can take inputs (parameters) process these inputs and returna result(called return value)
##### Example 
```
def get_at_content(dna):
    # Get the length of the DNA string
    length = len(dna)
    
    # Count the occurrences of 'A' and 'T'
    a_count = dna.count('A')
    t_count = dna.count('T')
    
    # Calculate the AT content
    at_content = (a_count + t_count) / length
    
    # Return the AT content
    return at_content

# Calling the function with different DNA sequences
my_at_content = get_at_content("ATGCGCGATCGATCGAATCG")
print(str(my_at_content))

print(get_at_content("ATGCATGCAACTGTAGC"))

print(get_at_content("aactgtagctagctagcagcgta"))
```

## Calling and improving our function
#### Fix the lower case problem by converting the input sequence to upper case before starting the calculation.
##### Example
```
def get_at_content(dna):
    # Convert the DNA string to uppercase for case-insensitive counting
    dna = dna.upper()
    
    # Get the length of the DNA string
    length = len(dna)
    
    # Count the occurrences of 'A' and 'T'
    a_count = dna.count('A')
    t_count = dna.count('T')
    
    # Calculate the AT content
    at_content = (a_count + t_count) / length
    
    # Return the AT content
    return at_content

    # Calling the function with different DNA sequences
my_at_content = get_at_content("ATGCGCGATCGATCGAATCG")
print(str(my_at_content))

print(get_at_content("ATGCATGCAACTGTAGC"))

print(get_at_content("aactgtagctagctagcagcgta"))
```

## Using round() function or sig_figs
#### The round() function in Python rounds to a specified number of decimal places, not significant figures. If you want to round to a specific number of significant figures, you'll need a different approach. However, if you're looking for decimal places (not significant figures), the round() function will work as expected.
##### Example 1
```
def get_at_content(dna):
    # Convert the DNA string to uppercase for case-insensitive counting
    dna = dna.upper()
    
    # Get the length of the DNA string
    length = len(dna)
    
    # Count the occurrences of 'A' and 'T'
    a_count = dna.count('A')
    t_count = dna.count('T')
    
    # Calculate the AT content
    at_content = (a_count + t_count) / length
    
    # Return the AT content rounded to 2 decimal places
    return round(at_content, 2)

    # Calling the function with different DNA sequences
my_at_content = get_at_content("ATGCGCGATCGATCGAATCG")
print(str(my_at_content))

print(get_at_content("ATGCATGCAACTGTAGC"))

print(get_at_content("aactgtagctagctagcagcgta"))
```

##### Example 2
```
def get_at_content(dna, sig_figs):
    # Convert the DNA string to uppercase for case-insensitive counting
    dna = dna.upper()
    
    # Get the length of the DNA string
    length = len(dna)
    
    # Count the occurrences of 'A' and 'T'
    a_count = dna.count('A')
    t_count = dna.count('T')
    
    # Calculate the AT content
    at_content = (a_count + t_count) / length
    
    # Return the AT content rounded to the specified number of decimal places
    return round(at_content, sig_figs)

# Test DNA sequence
test_dna = "ATGCATGCAACTGTAGC"

# Calling the function with different numbers of decimal places
print(get_at_content(test_dna, 1))  # Round to 1 decimal place
print(get_at_content(test_dna, 2))  # Round to 2 decimal places
print(get_at_content(test_dna, 3))  # Round to 3 decimal places
```

##### Output
>0.5

>0.53

>0.533

## Testing functions 
#### These are used to check that code does what was intended to do so. An assertion consists of the word assert followed by a call to our function the two equals signs then the result that we expect.
#### For example we know that if we run our get_at content function on the DNA sequence "ATGC", we should get an answer of 0.5
```
assert get_at_content("ATGC")==0.5
```

## Conditional statements
#### Are features of python that allow us to build decision points in our code and allow our programs to decide which out of a number of possible courses of action to take
#### Condition is a simply a bit of code that can produce a true or false answer.
##### Example
```
print(3 == 5)
print(3 > 5)
print(3 <=5)
print(len("ATGC") > 5)
print("GAATTC".count("T") > 1)
print("ATGCTT".startswith("ATG"))
print("ATGCTT".endswith("TTT"))
print("ATGCTT".isupper())
print("ATGCTT".islower())
print("V" in ["V", "W", "L"])
```
##### Output
>True/False

### The basic building blocks of the conditions
>equals (represented by ==)

>greater and less than (represented by > and <)

>greater and less than or equal to (represented by >= and <=)

>not equal (represented by!=)

>is a value in a list (represented by in)

>are two objects the same (represented by is)

>Strings have a startswith method that returns true if the string starts with the string given as an argument.

>Note that the test for equality is TWO equals signs, not one. Forgetting the second equals sign will cause an error.

## If statements 
#### This is the simplest condition statement
##### THe syntax is as follows
```
expression_level = 125

if expression_level > 100:
    print("gene is highly expressed")
```

##### Output
>gene is highly expressed

##### Example 
```
accs = ['ab56', 'bh84', 'hv76', 'ay93', 'ap97', 'bd72']

# Iterate over each accession in the list
for accession in accs:
    # Check if the accession starts with 'a'
    if accession.startswith('a'):
        print(accession)
```

## else statement
##### Example 
```
expression_level = 125

if expression_level > 100:
    print("gene is highly expressed")
else:
    print("gene is lowly expressed")
```

##### Output
>gene is highly expressed

>gene is lowly expressed


##### Example 
```
# Open files 
file1=open("one.txt", "w") 
file2=open("two.txt", "w")
    # List of accession codes
    accs = ['ab56', 'bh84', 'hv76', 'ay93', 'ap97', 'bd72']
    
    # Iterate through each accession code
    for accession in accs:
        # If the accession starts with 'a', write it to 'one.txt'
        if accession.startswith('a'):
            file1.write(accession + "\n")
        # Otherwise, write it to 'two.txt'
        else:
            file2.write(accession + "\n")
```

## elif statements
#### What if we have more than two possible branches.
##### Example 
```
# Open the files 
file1=open("one.txt", "w") 
file2=open("two.txt", "w") 
file3=open("three.txt", "w")
    # List of accession codes
    accs = ['ab56', 'bh84', 'hv76', 'ay93', 'ap97', 'bd72']
    
    # Iterate through each accession code
    for accession in accs:
        # If the accession starts with 'a', write it to 'one.txt'
        if accession.startswith('a'):
            file1.write(accession + "\n")
        # If the accession starts with 'b', write it to 'two.txt'
        elif accession.startswith('b'):
            file2.write(accession + "\n")
        # Otherwise, write it to 'three.txt'
        else:
            file3.write(accession + "\n")
```

## While loops
#### Used to run until some condition met.
##### Example
```
count = 0
while count < 10:
    print(count)
    count = count + 1
```

##### Output
>0

>1

>2

>3

>4

>5

>6

>7

>8

>9

## Building up complex conditions using "and"
##### Example
```
accs = ['ab56', 'bh84', 'hv76', 'ay93', 'ap97', 'bd72']
for accession in accs:
	if accession.startswith('a') and accession.endswith('3'):
	print(accession)
```

## Building up complex conditions using "or"
##### Example
```
accs = ['ab56', 'bh84', 'hv76', 'ay93', 'ap97', 'bd72']
for accession in accs:
	if accession.startswith('a') or accession.startswith('b'):
	print(accession)
```

## Building up complex conditions using "not"
##### Example
```
accs = ['ab56', 'bh84', 'hv76', 'ay93', 'ap97', 'bd72']
for acc in accs:
	if acc.startswith('a') and not acc.endswith('6'):
	print(acc)
```

## Writing True/False function
##### Example 
```
def is_at_rich(dna):
    # Get the length of the DNA string
    length = len(dna)
    
    # Count occurrences of 'A' and 'T' (case insensitive)
    a_count = dna.upper().count('A')
    t_count = dna.upper().count('T')
    
    # Calculate the AT content
    at_content = (a_count + t_count) / length
    
    # Return True if the AT content is greater than 65%, else False
    return at_content > 0.65
```

## Extracting the part of the string that matched
##### Example
```
import re

# DNA sequence
dna = "ATGACGTACGTACGACTG"

# Store the match object in the variable m
m = re.search(r"GA[ATGC]{3}AC", dna)

# Check if a match was found before accessing the group
if m:
    print(m.group())
else:
    print("No match found.")
```
##### Explanation
>re.search(r"GA[ATGC]{3}AC", dna): This searches for the pattern GA followed by exactly three characters from the set [ATGC] (which represents the four DNA bases) and ending with AC. The r before the pattern indicates a raw string literal, which helps avoid issues with escape characters.

>m.group(): If a match is found, m.group() returns the matched string.

>if m:: Before calling m.group(), we check if m is not None, which ensures we only try to access .group() when a match is found.

##### Output
>GACGTAC

##### If the pattern is not found, the output will be:
>No match found.

## Getting the position of the match
##### Example
```
import re

# DNA sequence
dna = "ATGACGTACGTACGACTG"

# Store the match object in the variable m
m = re.search(r"GA([ATGC]{3})AC([ATGC]{2})AC", dna)

# Check if a match was found
if m:
    print("start: " + str(m.start()))
    print("end: " + str(m.end()))
else:
    print("No match found.")
```

##### Output
>start: 0

>end: 11

##### If specific pattern does not match
>No match found.

## Finding nultiple matches
### Using re.findall() method
#### The re.findall() method will return a list of substrings that match the specified pattern.
##### Example
```
import re

# DNA sequence
dna = "ACTGCATTATATCGTACGAAATTATACGCGCG"

# Find all occurrences of substrings containing 'A' or 'T' with length between 4 and 100
runs = re.findall(r"[AT]{4,100}", dna)

# Print the results
print(runs)
```

##### Output
>['ATTAT', 'AAATT', 'ATTAT']

### Using re.finditer() method
#### This function returns an iterator yielding match objects for all non-overlapping matches of the regular expression in the string. Each match object provides methods to retrieve information about the match.
##### Example
```
import re

# DNA sequence
dna = "ACTGCATTATATCGTACGAAATTATACGCGCG"

# Find all occurrences of substrings containing 'A' or 'T' with length between 3 and 100
runs = re.finditer(r"[AT]{3,100}", dna)

# Iterate over each match found
for match in runs:
    run_start = match.start()  # Start index of the match
    run_end = match.end()      # End index of the match
    print("AT rich region from " + str(run_start) + " to " + str(run_end))
```
##### Explanation
>match.start(): Returns the start index of the match.

>match.end(): Returns the end index (exclusive) of the match.

>The for match in runs: loop iterates through each match object returned by re.finditer(), and we print the starting and ending indices for each match.

##### Output
>AT rich region from 3 to 8

>AT rich region from 7 to 12

>AT rich region from 18 to 23

>AT rich region from 25 to 30

## Dictionary
#### 
>We might want to store paired data, such as:

> protein sequence names and their sequences

> DNA restriction enzyme names and their motifs

> codons and their associated amino acid residues

> colleagues' names and their email addresses

> sample names and their co-ordinates

> words and their definitions

> All these are examples of key-value pairs. In each case we have pairs of keys and values:


### Creating a dictionary
##### Example
```
enzymes = { 
    'EcoRI': r'GAATTC',  # EcoRI recognition sequence
    'AvaII': r'GG(A|T)CC',  # AvaII recognition sequence, with a choice between A or T
    'BisI': 'GC[ATGC]GC'  # BisI recognition sequence, where the middle base can be A, T, G, or C
}
```

### Retriving a bit of data from a dictionary
#### To retrieve a bit of data from the dictionary, i.e. to look up the motif for a particular enzyme – we write the name of the dictionary,followed by the key in square brackets
##### Example
```
print(enzymes['BisI'])
```

### Restrictions of dictionaries
>The only types of data we are allowed to use as keys are strings and numbers, thus, we cant create a dictionary where the keys are file objects.

>Values can be whatever type of data we like.

> Also, keys must be unique, i.e., we can't store multiple values for the same key.

### Deleting a key in a dictionary
#### We use the pop method which returns the value and deletes the key at the same time
##### Example
```
enzymes = {
	'EcoRI' : r'GAATTC',
	'AvaII' : r'GG(A|T)CC',
	'BisI' : r'GC[ATGC]GC'
}
# remove the EcoRI enzyme from the dict
enzymes.pop('EcoRI')
```

### Using the get method
#### The dictionary's get method usually works just like using square brackets, e.g.: the following two lines do exactly the same thing
>print(counts['TGA'])

>print(counts.get('TGA'))

### Iterating over a dictionary using the keys method
#### When used on a dictionary, the keys method returns a list of all the keys in the dictionary,
##### Example 
```
counts = {'a': 1, 'b': 2, 'c': 3}
print(counts.keys())
```

##### Output
>dict_keys(['a', 'b', 'c'])

##### If you want to access these keys as a list
```
print(list(counts.keys()))
```


