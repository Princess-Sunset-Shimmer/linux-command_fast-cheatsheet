# linux command fast-cheatsheet
- [general command](#general-command "goto general-command")
# general command
- [format style](#format-style "goto format-style")
- [preprocess](#preprocess "goto preprocess")
## .format style
- **opname** --options parameters /directories
- - - -
- ***command*** 1> /redirection-directory
- ***command*** 1>> /append-redirection-directory
```
    '1' is file discriptor stands for standard-output
    '0' stands for standard-input
    '2' stands for standard-error
```
- - - -
- ***command*** ; ***command***    /* multiple command */
- ***command*** | ***command***    /* command pipeline */
- ***command*** $(***command***)   /* command substitution */
## .preprocess

- **"\*"**              /* any characters */
- **"?"**               /* any single character */
- **"{jpg,bmp,png}"**   /* set of characters */
- - - -
- **"~"**               /* home directory */
- **"."**               /* current directory */
- **".."**              /* previous directory */
## .system and command info
