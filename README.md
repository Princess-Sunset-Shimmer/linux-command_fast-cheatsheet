# linux command fast-cheatsheet
- [General Command](#General-Command "goto General-Command")
- [use Terminal emulator as File explorer](#use-Terminal-emulator-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
# General Command
- [format style](#format-style "goto format-style")
- [preprocess](#preprocess "goto preprocess")
- [system and command info](#system-and-command-info "goto system-and-command-info")
## .format style
```lua
        opname --options parameters /directories/files
```
```lua
        command 1> /redirection-directory/written-file
        command 1>> /append-redirection-directory/written-file
```
- - - -
- - '1' is file discriptor stands for standard-output
- - '0' stands for standard-input
- - '2' stands for standard-error
- - - -
```c
        command ; command    /* multiple command */
```
```c
        command | command    /* command pipeline, standard output to standard input*/
        command $(command)   /* command substitution, standard output to argument input */
```
## .preprocess
```lua
        '*'               --> any characters
        '?'               --> any single character
        "{jpg, bmp, png}" --> set of characters
```
- - - -
- example:
- - \*.jpg /* all jpg files */
- - \*.{jpg, pdf} /* all jpg and pdf files */
- - - -
```lua
        '~'               --> home directory
        '.'               --> current directory
        ".."              --> previous directory
```
## .system and command info
```c
        whoami             /* show user name */
        uname -a           /* show system kernel version */
        fastfetch
```
```c
        man opname         /* documentation about the command */
        type opname        /* show command type */
```
# use Terminal emulator as File explorer
- [view and edit Directory](#view-and-edit-Directory "goto view-and-edit-directory")
- [view and edit File](#view-and-edit-File "goto view-and-edit-File")
- [permission control](#permission-control "goto permission-control")
## .view and edit Directory
```c
        pwd                 /* show current directory */
        cd /directory/      /* change directory */
```
```c
        ls -al /directory/file         /* list all files */
        ls -al /directory/file | wc -l /* count files and directory */
```
- - - -
```asm
        .rw-r--r-- 3.6 MB user 14 Jul 02:43 file-name.pdf
        │ │  │  │          └─file-owner
        │ │  │  └─world-permission
        │ │  └─group-permission
        │ └─owner-permission
        └─file-type
```
- file type:
- - '.' for regular file
- - 'c' for character file
- - 'b' for block file
- - 'd' for directory
- - 'l' for symbolic link
- file permission:
- - 'r' for readable
- - 'w for writeable
- - 'x' for executable
- - '\-' for unable
- - - -
```
        mkdir /directory-to-create/
```
```
        cp -r /source-directory/ /destination-directory/
        mv /soutce-directory/ /destination-directory/
```
- - - -
- - add option \-i for interactively confirm the copying action
- - - -
```
        rm -r /directory-be-removed/
```
- - - -
- - add option \-f to add force to remove it
- - - -
## .view and edit File

## .permission control
