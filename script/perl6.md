# Comments

    # comment

## Choosing shell for execution

A path to the shell can be specified after a shebang `#!` in the first line of the script.

    #!/usr/bin/env perl6

# Variables

**Note:** A sigil is the prefix of a variable. Perl offers `$` for simple variables, `@` for arrays, `%` for hash maps and `&` for callables.

## Working

```
my $var = 10;

my Int $typed = 10;

my @array = 1, 2, 3;

my %hash = Key => 'Val', Key2 => 'Val2';

# lets you create a variable without sigil
my \variable = 10;
say variable;
```

# Branching

## `if`

    if <expression> {
        # do something
    } elsif <expression> { 
        # do elseif
    } else { 
        # do else
    }

## `unless`

    unless <expression> {
        # execute if expression is false
    }

# IO

## Output 
    
    # output a constant
    say 'Hello World'

    # output a variable
    say $var
