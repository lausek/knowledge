# Comments

    # comment

## Choosing shell for execution

A path to the shell can be specified after a shebang `#!` in the first line of the script.

    #!/bin/bash

# Variables

**Note:** Bash is space sensitive - each space separates a token

## Working

```
# set variable
var=value

# calculate something
let var=5+4
# or
let "var = 5 + 4"

# variables need quotes if spaces are needed
var='Debian'

# double quotes allow interpolation
var="$var 9"

# assign program output to variable  
var=$( ls /etc )

# get variable
echo $var

# make variable available to child process
export $var
# call ... 
```

## Special variables

- `$0` - The name of the Bash script

- `$1 - $9` - The first 9 arguments to the Bash script

- `$#` - How many arguments were passed to the Bash script?

- `$@` - All the arguments supplied to the Bash script

- `$?` - The exit status of the most recently run process

- `$$` - The process ID of the current script

- `$USER` - The username of the user running the script

- `$HOSTNAME` - The hostname of the machine the script is running on

- `$SECONDS` - The number of seconds since the script was started

- `$RANDOM` - Returns a different random number each time is it referred to

- `$LINENO` - Returns the current line number in the Bash script

# Branching

## `if`

    if [ <expression> ]
    then
        # do something
    elif [ <expression> ]
    then
        # do elseif
    else
        # do else
    fi

**Note:** `then` can be moved to the same line if a semicolon is used after the brackets. 

## `if` - double-parenthesis

In simple parenthesis, it is possible to use regular comparison operators and logical connections (`&&`, `||`).

    if (( <expression> )); then
        # ...
    fi

### Operators

- `!<expression>` - negate result of expression
- `-n <string>` - string is not empty 
- `-z <string>` - string is empty

- **compare strings**
    - `=` - equal
    - `!=` - not equal

- **compare integers**
    - `-eq` - equal
    - `-gt` - greater than 
    - `-lt` - less than

- **file operations**
    - `-e` - exists 
    - `-d` - exists and is a directory
    - `-r` - exists and read is allowed
    - `-w` - exists and write is allowed
    - `-x` - exists and execution is allowed
    - `-s` - exists and file is not empty 

## `case`

    case <value> in
    <expression>)

        ;;
    <expression>)

        ;;
    *)
        # default branch
    esac

# Looping

## `for`
    
    # loop over a series of words
    for w in $( ls ); do
        # ...
    done

    # for ... in ...
    for i in `seq 1 10`; do
        # ...
    done

## `while`
    
    # loop while expression is true
    while [ <expression> ]; do
        # ...
    done

## `until`
    
    # loop until expression is true
    until [ <expression> ]; do
        # ...
    done

# Functions
    
    function func_name {
        # ...     
    }


## C-Style

    func_name () {
        # ...    
    }

# IO

## Input

    # take input from user
    # no $ here (write)
    read var

    # specify prompt
    read -p 'What's your name? ' var
   
    # silent input for passwords
    read -s password

**Note:** `read` splits on whitespace 

    read var1 var2 var3
    # input: foo bar baz
    # var1=foo
    # var2=bar
    # var3=baz

## Output 
    
    # output a constant
    echo "Hello World"

    # output a variable
    echo $var
