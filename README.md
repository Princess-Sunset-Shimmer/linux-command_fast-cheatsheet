# linux command fast-cheatsheet
- [General Command](#General-Command "goto General-Command")
- [use Terminal emulator as File explorer](#use-Terminal-emulator-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
# General Command
- [format style](#format-style "goto format-style")
- [preprocess](#preprocess "goto preprocess")
- [system and command info](#system-and-command-info "goto system-and-command-info")
## .format style
```lua
        opname --options parameters /directories
```
```lua
        command 1> /redirection-directory
        command 1>> /append-redirection-directory
```
- - - -
- - '1' is file discriptor stands for standard-output
- - '0' stands for standard-input
- - '2' stands for standard-error
- - - -
```
        command ; command    /* multiple command */
        command | command    /* command pipeline */
        command $(command)   /* command substitution */
```
## .preprocess
```asm
        "*"               /* any characters */
        "?"               /* any single character */
        "{jpg, bmp, png}" /* set of characters */
```
- - - -
- example:
- - \*.jpg /* all jpg files */
- - \*.{jpg, pdf} /* all jpg and pdf files */
- - - -
```asm
        "~"               /* home directory */
        "."               /* current directory */
        ".."              /* previous directory */
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
## .view and edit Directory
```
        pwd                 /* show current directory */
        cd /directory/      /* change directory */
```
```
        ls -al /directory/          /* list all files at directory, show files at current directory while /directory/ is not indicated */
        ls -al /directory/ | wc -l  /* count files at /directory/ */
```
- - - -
```asm
        .rw-r--r-- 3.6M user 14 Jul 02:43 file-name.pdf
        │ │  │  │        └─file-owner
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
## .view and edit File
