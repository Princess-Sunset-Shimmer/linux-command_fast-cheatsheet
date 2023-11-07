# linux command fast-cheatsheet
- [General Command](#General-Command "goto General-Command")
- [use Terminal emulator as File explorer](#use-Terminal-emulator-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
# General Command
- [format style](#format-style "goto format-style")
- [preprocess](#preprocess "goto preprocess")
- [system and command info](#system-and-command-info "goto system-and-command-info")
## .format style
```
        opname --options parameters /directories
```
```
        command 1> /redirection-directory
        command 1>> /append-redirection-directory
```
- - - -
- '1' is file discriptor stands for standard-output
- '0' stands for standard-input
- '2' stands for standard-error
- - - -
```
        command ; command    /* multiple command */
        command | command    /* command pipeline */
        command $(command)   /* command substitution */
```
## .preprocess
```
        *               /* any characters */
        ?               /* any single character */
        {jpg, bmp, png} /* set of characters */
```
```
        ~               /* home directory */
        .               /* current directory */
        ..              /* previous directory */
```
## .system and command info
```
        whoami             /* show user name */
        uname -a           /* show system kernel version */
```
```
        man opname         /* documentation about the command */
        type opname        /* show command type */
```
# use Terminal emulator as File explorer
- [view and edit Directory](#view-and-edit-Directory "goto view-and-edit-directory")
- [view and edit File](#view-and-edit-File "goto view-and-edit-File")
