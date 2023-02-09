## pwd: Where am I

`pwd`: print working directory, shows where you are now

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ pwd
/home/ytq
```

## ls: What are in the location

`ls`: list, what are in this current location

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq      模板  文档  桌面
idea.desktop      PycharmProjects  ytq.txt  视频  下载
IdeaProjects      snap             公共的   图片  音乐
```

`ls [options][location]`

`ls -l`: show what are in this current location, and their detailed information

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -l
总用量 68
-rw-r--r-- 1 ytq ytq 8980 4月  13  2022 examples.desktop
-rwxrw-r-- 1 ytq ytq  228 4月  29  2022 idea.desktop
drwxr-xr-x 3 ytq ytq 4096 4月  16  2022 IdeaProjects
drwxrwxr-x 4 ytq ytq 4096 2月   9 14:08 Linux-Tutorial
drwxrwxr-x 3 ytq ytq 4096 5月   2  2022 PycharmProjects
drwx------ 3 ytq ytq 4096 4月  16  2022 snap
```

* First character indicates whether it is a normal file *(-)* or directory *(d)*
* Next 9 characters are *permissions* for the file or directory
* The next field is the number of blocks
* The next field is the owner of the file or directory
* The next field is the group the file or directory belongs to
* The next field is the file size
* Next is the last file modification time
* Next is the actual name of the file or directory

`ls [location]`: list not current directory but instead to list locations' contents

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -l Linux-Tutorial/
总用量 12
-rw-rw-r-- 1 ytq ytq  431 2月   9 14:20 Linux_tutorial.md
drwxrwxr-x 2 ytq ytq 4096 2月   9 00:32 pictures
-rw-rw-r-- 1 ytq ytq   16 2月   9 00:30 README.md
```

## Path

Absolute paths specify a location (file or directory) in relation to **the root directory**. You can identify them easily as they always begin with a forward slash ( **/** )

Relative paths specify a location (file or directory) in relation to **where we currently are** in the system. They will not begin with a slash.

`~`: home directory

`.`: current directory

`..`: the parent directory

## cd: Move to certain location

`cd [location]`: move to the certain location

if only `cd` without `location`, it will take you back to home directory

## Files

If you look at a file, in the end it is always an extension followed, like:

* file**.exe**: an executable file, or program
* file.**txt**: a plain text file
* file.**png**: an image

But in Linux, it's quite different. Linux ignores the extension, and looks inside the file to determine what type of file it is. So *myself.png* actually could be a text file rather than image to me.

`file [path]`: find out what exactly the file is

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ file Linux-Tutorial/Linux_tutorial.md
Linux-Tutorial/Linux_tutorial.md: UTF-8 Unicode text
```

Windows are case insensitive, but Linux is not. Like when we have two or mor files and directories with the same name but letters of different case. Linux sees these all as distinct and separate files.

### Hidden Files and Directories

`ls -a`: shows all files and directories, including hidden

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -a
.              .config           .local                     ytq
..             .dbus             .mozilla                   ytq.txt
.android       examples.desktop  .pki                       .zoom
.ansible       .gconf            .profile                   公共的
.anyconnect    .gnupg            PycharmProjects            模板
.bash_history  .gvfs             .rpmdb                     视频
.bash_logout   .ICEauthority     snap                       图片
.bashrc        idea.desktop      .ssh                       文档
.bashrc.swp    IdeaProjects      .sudo_as_admin_successful  下载
.cache         .java             .thunderbird               音乐
.cisco         Linux-Tutorial    .viminfo                   桌面
```

Files and directories start with **.** , mean they are hidden.

## Assistance

`man <command to look up>`: manual page

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ man ls
LS(1)                           User Commands                           LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about the FILEs (the current directory by default).
       Sort entries alphabetically if none of -cftuvSUX nor --sort is  speci‐
       fied.

       Mandatory  arguments  to  long options are mandatory for short options
       too.

       -a, --all
              do not ignore entries starting with .

       -A, --almost-all
              do not list implied . and ..

       --author
              with -l, print the author of each file

       -b, --escape
              print C-style escapes for nongraphic characters

       --block-size=SIZE
              scale   sizes   by   SIZE   before   printing    them;    e.g.,
              '--block-size=M'  prints sizes in units of 1,048,576 bytes; see
              SIZE format below

       -B, --ignore-backups
              do not list implied entries ending with ~

       -c     with -lt: sort by, and show, ctime (time of  last  modification
              of  file  status  information); with -l: show ctime and sort by
              name; otherwise: sort by ctime, newest first

       -C     list entries by columns

       --color[=WHEN]
              colorize the output; WHEN can be 'always' (default if omitted),
              'auto', or 'never'; more info below

       -d, --directory
              list directories themselves, not their contents

       -D, --dired
              generate output designed for Emacs' dired mode

       -f     do not sort, enable -aU, disable -ls --color

```

## File Manipulation

### Create directory

`mkdir [options] <Directory>`: making a directory

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq      模板  文档  桌面
idea.desktop      PycharmProjects  ytq.txt  视频  下载
IdeaProjects      snap             公共的   图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir experiment
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     snap     公共的  图片  音乐
experiment        Linux-Tutorial   ytq      模板    文档  桌面
idea.desktop      PycharmProjects  ytq.txt  视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir Linux-Tutorial/test
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls Linux-Tutorial/
Linux_tutorial.md  pictures  README.md  test
```

`mkdir -p <Directory>`: no error if existing, but if there is no such parent directories, creating a new parent directory

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     qty   ytq      模板  文档  桌面
experiment        Linux-Tutorial   snap  ytq.txt  视频  下载
idea.desktop      PycharmProjects  test  公共的   图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir fredrick/test
mkdir: 无法创建目录"fredrick/test": 没有那个文件或目录
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -p fredrick/test
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  idea.desktop    PycharmProjects  test     公共的  图片  音乐
experiment        IdeaProjects    qty              ytq      模板    文档  桌面
fredrick          Linux-Tutorial  snap             ytq.txt  视频    下载
```

`mkdir -v <Directory>`: when making directories, telling us what it is doing

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  idea.desktop    PycharmProjects  test     公共的  图片  音乐
experiment        IdeaProjects    qty              ytq      模板    文档  桌面
fredrick          Linux-Tutorial  snap             ytq.txt  视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -pv test2
mkdir: 已创建目录 'test2'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -pv fredrick/test3
mkdir: 已创建目录 'fredrick/test3'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -v test3
mkdir: 已创建目录 'test3'
```

### Delete directory

`rmdir [options] <Directory>`: remove the directory

`rmdir -p <Directory>` and `rmdir -pv <Directory>` and `rmdir -v <Directory>` are very similar with `mkdir [options] <Directory>` 

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     snap   ytq      视频  音乐
experiment        Linux-Tutorial   test   ytq.txt  图片  桌面
fredrick          PycharmProjects  test2  公共的   文档
idea.desktop      qty              test3  模板     下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir qty
rmdir: 删除 'qty' 失败: 目录非空
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir experiment/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     qty   test2  ytq.txt  视频  下载
fredrick          Linux-Tutorial   snap  test3  公共的   图片  音乐
idea.desktop      PycharmProjects  test  ytq    模板     文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir -pv fredrick/test2
rmdir: 正在删除目录 'fredrick/test2'
rmdir: 删除 'fredrick/test2' 失败: 没有那个文件或目录
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls fredrick/
test  test3
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir -pv fredrick/test
rmdir: 正在删除目录 'fredrick/test'
rmdir: 正在删除目录 'fredrick'
rmdir: 删除目录 'fredrick' 失败: 目录非空
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cd fredrick/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/fredrick$ rmdir test
rmdir: 删除 'test' 失败: 没有那个文件或目录
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/fredrick$ cd ..
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir -pv fredrick/test3/
rmdir: 正在删除目录 'fredrick/test3/'
rmdir: 正在删除目录 'fredrick'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   snap   test3    公共的  图片  音乐
idea.desktop      PycharmProjects  test   ytq      模板    文档  桌面
IdeaProjects      qty              test2  ytq.txt  视频    下载
```

If the directory we want to delete is not empty, we can't delete this directly.

### Create a blank file

`touch [options] <filesname>`: create a blank file

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   snap     公共的  图片  音乐
idea.desktop      PycharmProjects  ytq      模板    文档  桌面
IdeaProjects      qty              ytq.txt  视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ touch test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   snap      ytq.txt  视频  下载
idea.desktop      PycharmProjects  test.txt  公共的   图片  音乐
IdeaProjects      qty              ytq       模板     文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ file test.txt 
test.txt: empty
```

### Copy a File or Directory

`cp [options] <source> <destination>`: copy a file or directory to the destination.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq.txt   视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp test.txt ytq
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq/
test.txt
```

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq.txt   视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp test.txt ytq/ytq1/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq/ytq1/
test.txt
```

`cp -r <source> <destination>`: copy directories or files

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  模板  文档  桌面
idea.desktop      PycharmProjects  ytq       视频  下载
IdeaProjects      snap             公共的    图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp -r ytq Linux-Tutorial/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cd Linux-Tutorial/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/Linux-Tutorial$ ls
Linux_tutorial.md  pictures  README.md  test  ytq
```

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp ytq2 ytq
cp: -r not specified; omitting directory 'ytq2'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp -r ytq2 ytq
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq2    视频  下载
IdeaProjects      snap             公共的  图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq/
test.txt  ytq1  ytq2
```

### Move a file or directory

`mv [options] <source> <destination>`: move a file or directory to the destination

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  模板  文档  桌面
idea.desktop      PycharmProjects  ytq       视频  下载
IdeaProjects      snap             公共的    图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mv test.txt Linux-Tutorial/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     视频  下载
idea.desktop      PycharmProjects  公共的  图片  音乐
IdeaProjects      snap             模板    文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls Linux-Tutorial/
Linux_tutorial.md  pictures  README.md  test  test.txt  ytq
```

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq2    视频  下载
IdeaProjects      snap             公共的  图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mv ytq2 ytq
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     视频  下载
idea.desktop      PycharmProjects  公共的  图片  音乐
IdeaProjects      snap             模板    文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq
test.txt  ytq1  ytq2
```

`mv` can also rename files and directories

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq2    视频  下载
IdeaProjects      snap             公共的  图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mv ytq2 ytq3
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq3    视频  下载
IdeaProjects      snap             公共的  图片  音乐
```

### Remove a file (and not empty directories)

`rm [options] <file>`: remove a file

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq3      视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rm test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq3    视频  下载
IdeaProjects      snap             公共的  图片  音乐
```

`rm -r <non empty Directories>`: remove a non empty directories

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq3      视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rm test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq3    视频  下载
IdeaProjects      snap             公共的  图片  音乐
```

