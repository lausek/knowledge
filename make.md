**Note:** makefiles ***must*** use tabs.

# Rules

A rule is like a build step that requires all right hand side rules to be fulfilled

    rulename: source1 source2

## Standard rules

    - `clean` removes the build folder and deletes already created object files
    - `run` compile project and execute

## Special rules

    - `.PHONY` contains all command that can be supplied to the makefile
