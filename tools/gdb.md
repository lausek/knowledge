# Enable debugging for a program

    gcc <program> -o<target> -ggdb

# Commands

**Note:** most simple commands can be called by just their first letter!

Initialize gdb session
    
    gdb <program>

Start program

    run

Continue program

    continue

Step into next function

    step

Step over next function

    next

Step out of function

    finish

Display variable

    print <name>

Show program code

    list

Set breakpoint on line
    
    break <linenumber>

Delete breakpoint
    
    del <number> [-<to_number>]

Close debugger

    quit

# Informations

Print function arguments

    info args

Print breakpoints and watchpoints

    info breakpoints
