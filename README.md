# linux command fast-cheatsheet
Terminal is the middle between the User and Operating System. Shell is Interpreter that allow Operating System understand `Shell Script` and `Command Line` you type at Command Prompt, Command Line is just a line of Shell Script that calls program. Bash is one of shell exist in `/bin/bash`. Here is a fast Command Line cheatsheet reference for your daily drive
- [General Command](#General-Command "goto General-Command")
- [use Terminal as File explorer](#use-Terminal-as-File-explorer "goto use-Terminal-emulator-as-File-explorer")
- [use Terminal as Package manager](#use-Terminal-as-Package-manager "goto use-Terminal-as-Package-manager")
- [use Terminal as Downloader](#use-Terminal-as-Downloader "goto use-Terminal-as-Downloader")
- [use Terminal as Storage manager](#use-Terminal-as-Storage-manager "goto use-Terminal-as-Storage-manager")
- [use Terminal as Archive manager](#use-Terminal-as-Archive-manager "goto use-Terminal-as-Archive-manager")
- [use Terminal as Disk cleaner](#use-Terminal-as-Disk-cleaner "goto use-Terminal-as-Disk-cleaner")
- [use Terminal as User manager](#use-Terminal-as-User-manager "goto use-Terminal-as-User-manager")
- [use Terminal as Multitask manager](#use-Terminal-as-Multitask-manager "goto use-Terminal-as-Multitask-manager")
- [use Terminal as Service manager](#use-Terminal-as-Service-manager "goto use-Terminal-as-Service-manager")
- [use Terminal as Network manager](#use-Terminal-as-Network-manager "goto use-Terminal-as-Network-manager")
- [use Terminal as Text editor](#use-Terminal-as-Text-editor "goto use-Terminal-as-Text-editor")
# General Command
- [syntax style](#syntax-style "goto syntax-style")
- [multi command special character](#multi-command-special-character "goto multi-command-special-character")
- [single command special character](#single-command-special-character "goto single-command-special-character")
- [system info](#system-info "goto system-info")
- [system control](#system-control "goto system-control")
## syntax style
```lua
        command_name --options parameters /source_directories/files /destination_directory/file
```
```lua
        command 1> /directory/file   # redirection
        command 1>> /directory/file  # append redirection
```
- - - -
| file discriptor | stands for      |
| --------------: | --------------: |
| `0`             | standard-input  |
| `1`             | standard-output |
| `2`             | standard-error  |

run `ls /directory/file` to ensure the file you want to redirect
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
        ~                    # home directory
        .                    # current directory
        ..                   # previous directory
```
```py
        *                    # any characters
        ?                    # any single character
        {jpg, bmp, png}      # set of characters
```
- - - -
example\
`*.jpg` for all jpg files\
`*.{jpg, pdf}` for all jpg and pdf files
- - - -
## system info
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
        sysctl -a            # print kernel parameters
        hostnamectl status   # print host name info
        fastfetch            # print system info
```
```py
        lspci -tv            # print all PCIe devices
        lsusb -t             # print all usb devices
```
- - - -
`tip`: you can add `alias lspci='lspci -tv'` to your `.bashrc` to comfort your lspci using
- - - -
## system control
```py
        reset                # reset terminal
        clear                # clear terminal
```
- - - -
`Ctrl` + `L` fast clear terminal
- - - -
```
        reboot
        shutdown
        shutdown now
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
        find /starting_directory/ -name "*mlp-fim*"       # search file contain keyword mlp-fim from starting_directory
        find /starting_directory/ -iname "mlp-fim"        # search file ignore case
        find /starting_directory/ -type d -name "mlp-fim" # search directory contain keyword mlp-fim from starting_directory
```
```py
        sha256sum /directory/file                         # check file SHA256
        file /directory/file                              # show file attributes
```
```py
        ls -al /directory/or_file                         # list all files
        ls -al /directory/or_file | wc -l                 # count files and directories
```
- - - -
`tip`: you can add `alias ls='ls --color=auto -al'` to your `.bashrc` to comfort your ls using
```asm
        .rw-r--r-- 3.6~MB user root 14-Jul-02:43 file_name.pdf
        │ │  │  │          │    └─ group-owner
        │ │  │  │          └─ user-owner
        │ │  │  └─ world-permission
        │ │  └─ group-permission
        │ └─ owner-permission
        └─ file-type
```
| file type | mean                  |
| --------: | --------------------: |
| `.`       | regular file          |
| `c`       | character device file |
| `b`       | block device file     |
| `l`       | symbolic link         |
| `d`       | directory             |

| file permission | mean       |
| --------------: | ---------: |
| `r`             | readable   |
| `w`             | writeable  |
| `x`             | executable |
| `-`             | unable     |
- - - -
```py
        mkdir /new_directory/                                  # create directory
        ln -s /directory/file /directory/symbolic_link_file    # create symbolic link
```
```py
        mv /source_directory/ /destination_directory/          # move directory
        mv /source_directory/file /destination_directory/      # move file
        mv old_file_name new_file_name                         # rename file
```
```py
        cp -r /source_directory/ /destination_directory/       # copy directory
        cp /source_directory/file /destination_directory/file  # copy file to new file
```
- - - -
add option `-i` for interactively confirm the copying action
- - - -
```py
        rm -r /directory/                                      # remove directory and its contents
        rm /directory/file                                     # remove file
```
- - - -
add option `-f` to add force to remove it\
run `ls /directory/file` to ensure the file you want to remove
- - - -
## permission control
```py
        chown user_name /directory/file                        # change owner to new user
        chown user_name:group_name /directory/file             # change owner to new user and new group
        chmod 750 /directory/file                              # set file permission to rwxr-x---
```
- - - -
| oct number | file mode |
| ---------: | --------: |
| `7`        | rwx       |
| `6`        | rw\-      |
| `5`        | r\-x      |
| `4`        | r\-\-     |
| `0`        | \-\-\-    |
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
        pacman -Q                          # print all installed packages
        pacman -Qet                        # print explicit installed packages
        pacman -Qs installed_package_name  # search explicit installed package by name
        pacman -Qii installed_package_name # print detail info about this installed package
```
```py
        pacman -Ss package_name            # search package online
        pacman -Sii package_name           # print detail info about this package online
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
        wget -c https://downloading.link/url                                      # continune download
        wget -P /directory_to_save_downloading_file/ https://downloading.link/url # assign saving directory
```
- - - -
`tip`: you can add `alias wget='wget -c'` to your `.bashrc` to comfort wget using
- - - -
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
        mkfs.ext2 /dev/block_device_partition_name     # format partition ext2
        mkfs.ext3 /dev/block_device_partition_name     # format partition ext3
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
        usermod -g new_group_name user_name     # change primary group
        usermod -aG group_name user_name        # add user to new secondary group
        usermod -G new_group_name user_name     # change secondary group
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
`1` show total or separate threads states\
`T` toggle CPU usage graph\
`E` toggle Memory usage unit\
`M` toggle Memory usage graph\
`SPACEBAR` update immediately\
`D` change update delay, `Esc` cancel changing\
`C` toggle COMMAND colum tasks name\
`Shift` + `V` show COMMAND hierarchy\
`V` fold COMMAND hierachy\
`Shift` + `E` toggle Memory usage unit of task table\
`Shift` + `M` show tasks by Memory usage\
`Shift` + `P` show tasks by current CPU usage\
`Shift` + `T` show tasks by total CPU usage\
`I` show active tasks only or all tasks\
`X` hilight tasks sorting column\
`Y` hilight running tasks row\
`B` toggle hilight or bold\
`Z` toggle color or monochrome\
`Shift` + `Z` change color mapping\
`shift` + `W` save current display toggle\
`K` kill a process, `Esc` cancel killing\
`R` change task [nice value](https://en.wikipedia.org/wiki/Nice_(Unix)), `Esc` cancel change
- - - -
```py
        command &    # run command at background
```
- - - -
`Ctrl` + `C` terminate foreground task (`INT` interrupt signal)\
`Ctrl` + `Z` pause foreground task (`TSTP` terminal stop signal)
- - - -
```py
        jobs         # print running jobs
        ps -uf       # print current user's running processes
        ps -xuf      # print current user's all processes
        ps -auf      # print all user's running processes
        pa -axuf     # print all user's all processes
        pstree       # print processes tree
```
```py
        fg %1        # move task foreground by jobspec number
        bg %2        # move task background by jobspec number
```
```py
        kill %3      # terminate task by jobspec number
        killall task_name
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
# use Terminal as Network manager
- [network manager](#network-manager "goto network-manager")
- [ip command](#ip-command "goto ip-command")
- [diagnostic](#diagnostic "goto diagnostic")

simple network connection steps
1. show network interface
2. connect network interface to router
3. setup ip address
4. setup routing address
5. setup DNS
6. confirm connection
## network manager
```py
        umtui                         # TUI network manager
```
- - - -
`NetworkManager` is network manager service name, you can use `systemctl` manage it
- - - -
## ip command
```py
        ip link show                  # print interface link state
        ip address show               # print interface ip address
        ip route show                 # print interface routing table
        ip neighbor show              # print interface ARP table
```
- - - -
`tip`: you can add `alias ip='ip --color=auto'` to your `.bashrc` to comfort your ip command using
- - - -
## diagnostic
```py
        ping host.name                # send ICMP to host
        traceroute host.name          # trace routing path to host
```
# use Terminal as Text editor
- [simple viewing](#simple-viewing "goto simple-viewing")
- [simple editing](#simple-editing "goto simple-editing")
- [vim](#vim "goto vim")
## simple viewing
```py
        cat /directory/file                      # print file contents
        head /directory/file                     # print top 10 lines of file contents
        head -n 15 /directory/file               # print top 15 lines of file contents
        tail /directory/file                     # print buttom 10 lines of file contents
        tail -n 15 /directory/file               # print buttom 15 lines of file contents
        grep keyword /directory/file             # print line that contain keyword in file
        diff /directory/file_1 /directory/file_2 # print difference between two files
        sort /directory/file                     # print sorted file contents by alphabet
        sort -r /directory/file                  # print sorted file contents by reversed alphabet
        sort -n /directory/file                  # print sorted file contents by size of number
        sort -rn /directory/file                 # print sorted file contents by reversed size of number
        sort -k 2 /directory/file                # sort by secound column 
```
```py
        command | grep keyword                   # print line that contain keyword in pipeline
```
## simple editing
```py
        echo "contents" > /directory/file        # redirect contents immediately to file
        echo "contents" >> /directory/file       # append contents immediately to file
        echo -e "contents\n" > /directory/file   # redirect contents with escape char
        echo -e "contents\n" >> /direcotry/file  # append contents with escape char
        cat > /directory/file                    # redirect standard input to file
        cat >> /directory/file                   # append standard input to file
```
- - - -
`Ctrl` + `D` send `eof` to input
- - - -
```py
        cat /directory/file_0 /directory/file_1 ... > /directory/file
        cat /directory/file_0 /directory/file_1 ... >> /directory/file
```
## vim
- - - -
[click here](https://github.com/Princess-Sunset-Shimmer/vim_fast-cheatsheet.git) to view vim fast-cheatsheet
- - - -

- - - -
Licence: [CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/)
