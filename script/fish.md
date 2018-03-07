The scripting language of the [fish shell](https://github.com/fish-shell/fish-shell). It is pretty similar to bash scripting, but offers a cleaner syntax. Fish scripts end with `.fish`. 

# Comments

    # comment

## Choosing shell for execution

A path to the shell can be specified after a shebang `#!` in the first line of the script.

    #!/usr/bin/fish

# Functions

`$argv` is an array that contains all variables passed to a function.

``` fish
# declare ll as a function that calls ls with parameters
function ll 
    ls -l $argv
end

# declare an alias for ls with standard parameters
# 'command' is needed because we want to redefine ls 
function ls
    # will also display hidden files in a list
    command ls -la $argv
end
```

## Autoloading functions

Functions defined under `$fish_function_path` are automatically added to each fish shell and - if redefined - the functionality will change too. 

**Note:** Those function definition files should only contain the function and nothing else!

Functions, that should be available for all users, might be placed in the `vendor` directory.

# Variables

## Working

```
# set variables
set a 5
set b 10
set c $b 

# arr is a list of values
set arr a b c

# variables can be scoped
begin
    set intern 500
end

# $intern is not visible anymore
```

## Special variables

- `$history` - history of executed commands 

- `$_` - The name of the fish script

- `$argv` - The arguments passed to the script (use `count $argv` for `argc`) 

- `$status` - The exit status of the most recently run process

- `%self` - The process ID of the current script

- `$USER` - The username of the user running the script

# Branching

**Note:** `or` and `and` can be used to connect expressions

## `if`
    
    if <expression>
        # do if
    else if <expression>
        # do else if
    else
        # do else
    end

    if test -f file.txt
        and test -r file.txt
        # file exists and is readable
    end
    
## `switch`

    switch <value>
        case <other_value1>
            # value1 
        case <other_value2> <other_value3>
            # either value2 or value3
        case '*'
            # default branch
    end
 
# Looping

## `for`

    # for ... in ...
    for i in `seq 1 10`
        # ...
    end

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
