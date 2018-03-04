The scripting language of the [fish shell](https://github.com/fish-shell/fish-shell). It is pretty similar to bash scripting, but offers a cleaner syntax. Fish scripts end with `.fish`. 

# Comments

    # comment

## Choosing shell for execution

A path to the shell can be specified after a shebang `#!` in the first line of the script.

    #!/bin/bash

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

# Branching

## `if`
    
    # TODO
    
## `switch`

    # TODO
    
# Looping

## `for`

    # for ... in ...
    for i in `seq 1 10`
        # ...
    end

# IO

## Input
    
    # TODO
    
## Output 
    
    # output a constant
    echo "Hello World"

    # output a variable
    echo $var
