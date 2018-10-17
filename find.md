# Options

    -type <t>

Filters for a specific file type e.g. `f` for regular file or `d` for directory.

# Useful

## Recursively execute command on files

    find . -type f -exec chmod 604 "{}" \;
