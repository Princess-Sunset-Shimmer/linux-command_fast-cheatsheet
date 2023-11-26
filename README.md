# linux command fast-cheatsheet
- [General Command](#General-Command "goto General-Command")
- [use Terminal emulator as File explorer](#use-Terminal-emulator-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
# General Command
- [format style](#format-style "goto format-style")
- [preprocess](#preprocess "goto preprocess")
- [system and command info](#system-and-command-info "goto system-and-command-info")
## format style
```lua
        opname --options parameters /source_directories/files /destination_directory/file
```
```lua
        command 1> /redirection_directory/written_file
        command 1>> /append_redirection_directory/written_file
```
- - - -
- - '1' is file discriptor stands for standard-output
- - '0' stands for standard-input
- - '2' stands for standard-error
- - - -
```py
        command ; command    # multiple command
```
```py
        command | command    # command pipeline, standard output to standard input
        command $(command)   # command substitution, standard output to argument input
```
## preprocess
```lua
        *               --> any characters
        ?               --> any single character
        {jpg, bmp, png} --> set of characters
```
- - - -
- example:
- - \*.jpg /* all jpg files */
- - \*.{jpg, pdf} /* all jpg and pdf files */
- - - -
```lua
        ~               --> home directory
        .               --> current directory
        ..              --> previous directory
```
## system and command info
```py
        whoami             # show user name
        uname -a           # show system kernel version
        fastfetch
```
```py
        man opname         # documentation about the command
        type opname        # show command type
```
# use Terminal emulator as File explorer
- [view and edit Directory or File](#view-and-edit-Directory "goto view-and-edit-directory")
- [permission control](#permission-control "goto permission-control")
## view and edit Directory or File
```py
        pwd                            # show current directory
        cd /directory/                 # change directory
```
```py
        ls -al /directory/file         # list all files
        ls -al /directory/file | wc -l # count files and directory
        find /starting_directory/ -name "*mlp-fim*"    # search file that contain keyword mlp-fim from starting-directory
        file /directory/file                           # show file attributes
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
```py
        mkdir /new_directory/        # create directory
```
```py
        cp -r /source_directory/ /destination_directory/        # copy directory
        cp /source_directory/file /destination_directory/file   # copy file to new file
        mv /source_directory/ /destination_directory/           # move directory
        mv /source_directory/file /destination_directory/       # move file
        mv file.c file.h                                        # rename file
```
- - - -
- - add option \-i for interactively confirm the copying action
- - - -
```py
        rm -r /directory_be_removed/        # remove directory
        rm /directory/file                  # remove file
```
- - - -
- - add option \-f to add force to remove it
- - - -


## .permission control
