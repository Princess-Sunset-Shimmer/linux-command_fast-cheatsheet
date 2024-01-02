# linux command fast-cheatsheet
Terminal is the middle between the user and shell, shell is interpreter that execute command line you type or shell script, shell script is script that contain command line, bash is one of shell exit in `/bin/bash`. Here is a fast command cheatsheet reference for your daily drive
- [General Command](#General-Command "goto General-Command")
- [use Terminal as File explorer](#use-Terminal-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
- [use Terminal as Package manager](#use-Terminal-as-Package-manager "goto use-Terminal-as-Package-manager")
- [use Terminal as Downloader](#use-Terminal-as-Downloader "goto use-Terminal-as-Downloader")
- [use Terminal as Storage manager](#use-Terminal-as-Storage-manager "goto use-Terminal-as-Storage-manager")
- [use Terminal as Archive manager](#use-Terminal-as-Archive-manager "goto use-Terminal-as-Archive-manager")
- [use Terminal as Disk cleaner](#use-Terminal-as-Disk-cleaner "goto use-Terminal-as-Disk-cleaner")
- [use Terminal as User manager](#use-Terminal-as-User-manager "goto use-Terminal-as-User-manager")
- [use Terminal as Multitask manager](#use-Terminal-as-Multitask-manager "goto use-Terminal-as-Multitask-manager")
- [use Terminal as Network manager](#use-Terminal-as-Network-manager "goto use-Terminal-as-Network-manager")
- [use Terminal as Service manager](#use-Terminal-as-Service-manager "goto use-Terminal-as-Service-manager")
- [use Terminal as Text editor](#use-Terminal-as-Text-editor "goto use-Terminal-as-Text-editor")
# General Command
- [syntax style](#syntax-style "goto syntax-style")
- [multi command special character](#multi-command-special-character "goto multi-command-special-character")
- [single command special character](#single-command-special-character "goto single-command-special-character")
- [system and info](#system-and-info "goto system-and-info")
## syntax style
```lua
        command_name --options parameters /source_directories/files /destination_directory/file
```
```lua
        command 1> /redirection_directory/written_file
        command 1>> /append_redirection_directory/written_file
```
- - - -
file discriptor
- - `0` stands for standard-input
- - `1` stands for standard-output
- - `2` stands for standard-error
- - - -
## multi command special character
```bash
        command ; command    # multiple command
```
```bash
        command | command    # command pipeline, standard output to standard input
        command $(command)   # command substitution, standard output to argument input
```
## single command special character
```bash
        ~               # home directory
        .               # current directory
        ..              # previous directory
```
```py
        *               # any characters
        ?               # any single character
        {jpg, bmp, png} # set of characters
```
- - - -
example
- - `*.jpg` for all jpg files
- - `*.{jpg, pdf}` for all jpg and pdf files
- - - -
## system and info
```py
        type command_name    # show command type
        man command_name     # documentation about the command
        command_name --help  # quick help for the command
```
```py
        history              # print command line history
```
- - - -
`ctrl` + `R` search command history by keywork, `Enter` to execute it, `─>` to confirm but not execute it, `ctrl` + `R` again to switch the saerch
- - - -
```py
        uname -a             # print system kernel version
        fastfetch            # print system information
```
```py
        lsusb -t             # print all usb devices
        lspci -tv            # print all PCIe devices
```
# use Terminal as File explorer
- [view and manage Directory and File](#view-and-edit-Directory-or-File "goto view-and-edit-directory-or-File")
- [permission control](#permission-control "goto permission-control")
- [linux file system fast view](#linux-file-system-fast-view "goto linux-file-system-fast-view")
## view and manage Directory and File
```py
        pwd                                               # show current directory
        cd /directory/                                    # change directory
```
```py
        find /starting_directory/ -name "*mlp-fim*"       # search file contain keyword mlp-fim from starting-directory
        find /starting_directory/ -iname "mlp-fim"        # search file ignore case
        find /starting_directory/ -type d -name "mlp-fim" # search directory contain keyword mlp-fim from starting-directory
```
```py
        sha256sum /directory/file                         # check file SHA256
        file /directory/file                              # show file attributes
```
```py
        ls -al /directory/or_file                         # list all files in the directory or specific files
        ls -al /directory/file | wc -l                    # count files and directory
```
- - - -
```asm
        .rw-r--r-- 3.6 MB user 14 Jul 02:43 file-name.pdf
        │ │  │  │          └─ file-owner
        │ │  │  └─ world-permission
        │ │  └─ group-permission
        │ └─ owner-permission
        └─ file-type
```
file type
- - `.` for regular file
- - `c` for character device file
- - `b` for block device file
- - `l` for symbolic link
- - `d` for directory
file permission
- - `r` for readable
- - `w` for writeable
- - `x` for executable
- - `-` for unable
- - - -
```py
        mkdir /new_directory/     # create directory
```
```py
        cp -r /source_directory/ /destination_directory/        # copy directory
        cp /source_directory/file /destination_directory/file   # copy file to new file
```
- - - -
add option `-i` for interactively confirm the copying action
- - - -
```py
        mv /source_directory/ /destination_directory/           # move directory
        mv /source_directory/file /destination_directory/       # move file
        mv file.c file.h                                        # rename file
```
```py
        rm -r /directory/        # remove directory and its contents
        rm /directory/file       # remove file
```
- - - -
add option `-f` to add force to remove it
- - - -
## permission control
```py
        sudo chown user_name /directory/file        # change file to new owner
        sudo chmod 750                              # set file permission to rwxr-x---
```
- - - -
file mode oct number
- - `7` for rwx
- - `6` for rw\-
- - `5` for r\-x
- - `4` for r\-\-
- - `0` for \-\-\-
- - - -
## linux file system fast view
```c#
   /─┬─home  /* branch user directory */
     ├─root  /* root user directory */
     ├─boot  /* boot loader and linux kernel are here */
     ├─etc   /* config files are here */
     ├─dev   /* device files are here */
     ├─proc  /* process files are */
     ├─var   /* various databases files are here */
     ├─tmp   /* temp files are here */
     └─usr─┬─bin      /* executable files are here */
           ├─lib      /* library files are here */
           ├─include  /* header files are here */
           ├─share
           └─local
```
# use Terminal as Package manager
- [Arch linux pacman](#Arch-linux-pacman "goto Arch-linux-pacman")
- [Fedora linux dnf](#Fedora-linux-dnf "goto Fedora-linux-dnf")
- [Debian linux apt](#Debian-linux-apt "goto Debian-linux-apr")
## Arch linux pacman
```py
        pacman -Qet                        # list explicit installed package
        pacman -Qs installed_package_name  # search explicit installed package by name
        pacman -Qii installed_package_name # check detail info about this installed package
```
```py
        pacman -Ss package_name            # search package online
        pacman -Si package_name            # print detail info about this package online
```
```py
        pacman -Syu package_name           # install the package
        pacman -Syu                        # update the system
```
```py
        pacman -Rsn package_name           # remove the package
        pacman -Qdt                        # list all unneeded packages
        pacman -Rsn $(pacman -Qdtq)        # remove all unneeded packages
        pacman -Scc                        # remove all package caches
```
## Fedora linux dnf
## Debian linux apt
# use Terminal as Downloader
```py
        wget https://downloading.link/url                                         # download to current directory
        wget -c https://downloading.link/url                                      # continune the download
        wget -P /directory_to_save_downloading_file/ https://downloading.link/url # assign saving directory
```
# use Terminal as Storage manager
- [manage single storage device](#manage-single-storage-device "goto manage-single-storage-device")
- [use Disk Destroyer to make bootable usb](#use-Disk-Destroyer-to-make-bootable-usb "goto use-Disk-Destroyer-to-make-bootable-usb")
- [raid](#raid "goto raid")
## manage single storage device
```py
        lsblk                                          # list block devices
        lsblk -f                                       # list partition file_system Format
        lsblk --discard                                # check Trim support, DISC-GRAN and DISC-MAX are 0B means Not support Trim
```
```py
        fdisk -l /dev/block_device_name                # print sector size
        fdisk /dev/block_device_name                   # CLI partition editor
        cfdisk /dev/block_device_name                  # TUI partition editor
```
```py
        mkfs.ext2 /dev/block-device_partition_name     # format partition ext2
        mkfs.ext4 /dev/block_device_partition_name     # format partition ext4
        mkfs.btrfs /dev/block_device_partition_name    # format partition btrfs
        mkfs.ntfs /dev/block_device_partition_name     # format partition ntfs
        mkfs.fat -F32 /dev/block_device_partition_name # format partition fat32
```
```py
        mount /dev/block_device_partition_name /mount_point_directory/
        umount /dev/block_device_partition_name
```
```py
        fsck /dev/block_device_partition_name          # fix file system corruption
```
## use Disk Destroyer to make bootable usb
```js
        dd if=/iso_directory/linux_distro.iso of=/dev/block_device_name status=progress
```
## raid

# use Terminal as Archive manager
```py
        tar cf /directory/archive.tar /directory/ # creat archive.tar
        tar tf /directory/archive.tar             # list archive.tar contents
        tar xf /directory/archive.tar             # extract archive.tar
```
```py
        zip -r /directory/archive.zip /directory/ # creat archive.zip
        unzip -l /directory/archive.zip           # list archive.zip contents
        unzip /directory/archive.zip              # extract archive.zip
```
# use Terminal as Disk cleaner
# use Terminal as User manager
```py
        who                                     # show current user name
        passwd -Sa                              # show all user names
```
```py
        su -l username                          # switch user as username
        su                                      # switch user as root
        sudo command                            # super user do command
        exit                                    # logout
```
- - - -
`Ctrl` + `D` also can exit
- - - -
```py
        useradd new_user_name                   # add new user only
        useradd -m new_user_name                # add new user and its directory
```
```py
        usermod -l new_user_name old_user_name  # change user name
        usermod -d /new_directory/ user_name    # change user directory
        usermod -d /new_directory/ -m user_name # change user directory and move its contents
```
```py
        usermode -g new_group_name user_name    # change primary group
        usermode -aG group_name user_name       # add user to new secoundary group
```
```py
        passwd                                  # change current user password
        passwd user_name                        # change user password
```
```py
        userdel user_name                       # delete user only
        userdel -r user_name                    # delete user and its directory
```
- - - -
user account file `/etc/passwd` example
```c
        geoclue:x:967:967:Geoinformation service:/var/lib/geoclue:/usr/bin/nologin
        │       │ │   │   │                      │                └─ shell directory
        │       │ │   │   │                      └─ home directory
        │       │ │   │   └─ comment
        │       │ │   └─ group ID
        │       │ └─ user ID
        │       └─ encrypted password
        └─ user name
```
- - - -
# use Terminal as Multitask manager
```py
        top    # open TUI process monitor
```
- - - -
`Q` quit tasks monitor\
`H` help\
`1` total or separate CPU states\
`SPACEBAR` update immediately\
`D` change update delay, `Esc` cancel changing\
`Shift` + `M` sort by Memory usage\
`Shift` + `P` sort by current CPU usage\
`Shift` + `T` sort by total CPU usage\
`I` active tasks or all tasks\
`X` hilight sort by what\
`Y` hilight running tasks\
`B` hilight or bold\
`Z` color or monochrome\
`Shift` + `Z` change color mapping\
`K` kill a process by PID, `Esc` cancel killing\
`shift` + `W` save current display toggle
- - - -
```py
        command &
```
- - - -
`Ctrl` + `C` terminate task (`INT` interrupt signal)\
`Ctrl` + `Z` pause task (`TSTP` terminal stop signal)
- - - -
```py
        jobs
        fg %1
        bg %2
```
```py
        kill %3
        killall command_name
```
# use Terminal as Network manager
simple network connection steps
1. list network interface
2. connect network interface to router
3. set ip address
4. set routing address
5. set DNS
6. confirm connection
```py
        umtui                         # TUI network manager
```
# use Terminal as Service manager
```py
        systemctl status service_name # print service status
        systemctl status *.service    # print all services status
```
```py
        systemctl start service_name
        systemctl stop service_name
        systemctl restart service_name
```
```py
        systemctl enable service_name
        systemctl disable service_name
```
# use Terminal as Text editor
- [simple editing](#simple-editing "goto simple-editing")
- [vim](#vim "goto vim")
## simple editing
```py
        cat /directory/file          # print file contents
        grep keyword                 # print line that contain keyword in the standard input file
        grep keyword /directory/file # print line that contain keyword in the file
```
```py
        cat > /directory/file        # redirect standard input file to /directory/file
```
- - - -
`Ctrl` + `D` send `eof` to input
- - - -
```py
        cat /directory/file_0 /directory/file_1 ... > /directory/new_file
        cat /directory/file_0 /directory/file_1 ... >> /directory/new_file
```
## vim
- - - -
[click here](https://github.com/Princess-Sunset-Shimmer/vim_fast-cheatsheet.git) to view vim fast-cheatsheet
- - - -

- - - -
Licence: [CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/)
