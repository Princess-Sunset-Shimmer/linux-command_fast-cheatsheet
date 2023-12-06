# linux command fast-cheatsheet
Terminal emulator is the middle between the user and shell, shell is the program that execute command you type in standard input file or shell script, shell script is the file that contain command. Here i write a fast command cheatsheet reference for your tasks:
- [General Command](#General-Command "goto General-Command")
- [use Terminal emulator as File explorer](#use-Terminal-emulator-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
- [use Terminal emulator as Storage manager](#use-Terminal-emulator-as-Storage-manager "goto use-Terminal-emulator-as-Storage-manager")
- [use Terminal emulator as Archive manager](#use-Terminal-emulator-as-Archive-manager "goto use-Terminal-emulator-as-Archive-manager")
- [use Terminal emulator as Text editor](#use-Terminal-emulator-as-Text-editor "goto use-Terminal-emulator-as-Text-editor")
- [use Terminal emulator as Multitask manager](#use-Terminal-emulator-as-Multitask-manager "goto use-Terminal-emulator-as-Multitask-manager")
- [environment config](#environment-config "goto environment-config")
# General Command
- [syntax style](#syntax-style "goto syntax-style")
- [multi command special character](#multi-command-special-character "goto multi-command-special-character")
- [single command special character](#single-command-special-character "goto single-command-special-character")
- [system and info](#system-and-info "goto system-and-info")
## syntax style
```lua
        opname --options parameters /source_directories/files /destination_directory/file
```
```lua
        command 1> /redirection_directory/written_file
        command 1>> /append_redirection_directory/written_file
```
- - - -
- - `1` is file discriptor stands for standard-output
- - `0` stands for standard-input
- - `2` stands for standard-error
- - - -
## multi command special character
```py
        command ; command    # multiple command
```
```py
        command | command    # command pipeline, standard output to standard input
        command $(command)   # command substitution, standard output to argument input
```
## single command special character
```py
        *               # any characters
        ?               # any single character
        {jpg, bmp, png} # set of characters
```
- - - -
- example:
- - `*.jpg` for all jpg files
- - `*.{jpg, pdf}` for all jpg and pdf files
- - - -
```py
        ~               # home directory
        .               # current directory
        ..              # previous directory
```
## system and info
```py
        man opname         # documentation about the command
        type opname        # show command type
```
```py
        whoami             # show user name
        uname -a           # show system kernel version
        fastfetch
```
```py
        su -l username     # switch user and login as username user
        su                 # switch user and login as root user
        exit               # logout
        passwd             # change password
```
# use Terminal emulator as File explorer
- [view and edit Directory or File](#view-and-edit-Directory-or-File "goto view-and-edit-directory-or-File")
- [permission control](#permission-control "goto permission-control")
- [linux file system fast view](#linux-file-system-fast-view "goto linux-file-system-fast-view")
## view and edit Directory or File
```py
        pwd                            # show current directory
        cd /directory/                 # change directory
```
```py
        find /starting_directory/ -name "*mlp-fim*"    # search file that contain keyword mlp-fim from starting-directory
        file /directory/file                           # show file attributes
```
```py
        ls -al /directory/file         # list all files
        ls -al /directory/file | wc -l # count files and directory
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
- file type
- - `.` for regular file
- - `c` for character device file
- - `b` for block device file
- - `l` for symbolic link
- - `d` for directory
- file permission:
- - `r` for readable
- - `w` for writeable
- - `x` for executable
- - `-` for unable
- - - -
```py
        mkdir /new_directory/        # create directory
```
```py
        cp -r /source_directory/ /destination_directory/        # copy directory
        cp /source_directory/file /destination_directory/file   # copy file to new file
```
- - - -
- - add option `-i` for interactively confirm the copying action
- - - -
```py
        mv /source_directory/ /destination_directory/           # move directory
        mv /source_directory/file /destination_directory/       # move file
        mv file.c file.h                                        # rename file
```
```py
        rm -r /directory_be_removed/        # remove directory
        rm /directory/file                  # remove file
```
- - - -
- - add option `-f` to add force to remove it
- - - -

## permission control
```py
        sudo chown user_name /directory/file        # change file to new owner
        sudo chmod 750                              # set file permission to rwxr-x---
```
- - - -
- file mode oct number
- - `7` for rwx
- - `6` for rw\-
- - `5` for r\-x
- - `4` for r\-\-
- - `0` for \-\-\-
- - - -
## linux file system fast view
```c#
root─┬─home  /* store your pictures documents films here */
     ├─boot  /* boot loader is here */
     ├─etc   /* config files are here */
     ├─dev   /* device files are here */
     ├─proc  /* process files are */
     ├─var   /* variable files are here */
     ├─tmp   /* temp files are here */
     └─usr─┬─bin      /* executable files are here */
           ├─lib      /* library files are here */
           ├─include  /* header files are here */
           ├─share
           └─local
```
# use Terminal emulator as storage manager
# use Terminal emulator as Archive manager
# use Terminal emulator as Text editor
- [simple editing](#simple-editing "goto simple-editing")
- [vim](#vim "goto vim")
## simple editing
```py
        cat /directory/file    # check file contents
        cat > /directory/file  # redirect standard input file to /directory/file, Ctrl + D to finish
```
```py
        cat /directory/source_file_0 /directory/source_file_1 ... > /directory/new_file
        cat /directory/source_file_0 /directory/source_file_1 ... >> /directory/new_file
```
## vim
- - - -
[click here to vim fast-cheatsheet](https://github.com/Princess-Sunset-Shimmer/vim_fast-cheatsheet.git)
- - - -
# use Terminal emulator as Multitask manager



