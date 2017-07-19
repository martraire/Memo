# Linux commands
In this memo, I give some of the most useful command on linux.


## 1. Compress and Extract data
The **tar command** on Linux is often used to create **.tar.gz** or **.tgz** archive files, also called *"tarballs"*. This command has a large number of options, but you just need to remember a few letters to quickly create archives with **tar**. The **tar** command can extract the resulting archives, too.

The GNU tar command included with Linux distributions has integrated compression. It can create a **.tar archive** and then compress it with *gzip* or *bzip2* compression in a single command. 
That is why the resulting file is a *.tar.gz* file or *.tar.bz2* file.


### How to compress data?
Use the following command to compress an entire directory or a single file on Linux. It will also compress every other directory inside a directory you specify–in other words, it works recursively.

`tar -czvf name-of-archive.tar.gz /path/to/directory-or-file`

Here is what those switches actually mean:
- `-c`: **C**reate an archive.
- `-z`: Compress the archive with g**z**ip.
- `-v`: Display progress in the terminal while creating the archive, also known as "**v**erbose" mode. The **v** is always optional in these commands, but it is helpful.
- `-f`: Allows you to specify the **f**ilename of the archive.

### Example
Let’s say you have a directory named *"stuff"* in the current directory and you want to save it to a file named *archive.tar.gz*. You’d run the following command:

`tar -czvf archive.tar.gz stuff`

Or, let’s say there’s a directory at */usr/local/something* on the current system and you want to compress it to a file named *archive.tar.gz*. You’d run the following command:

`tar -czvf archive.tar.gz /usr/local/something`

### Exclude Directories and Files
In some cases, you may wish to compress an entire directory, but not include certain files and directories. You can do so by appending an **--exclude** switch for each directory or file you want to exclude.

For example, let’s say you want to compress */home/ubuntu*, but you don’t want to compress the */home/ubuntu/Downloads* and */home/ubuntu/.cache* directories. Here’s how you’d do it:

`tar -czvf archive.tar.gz /home/ubuntu --exclude=/home/ubuntu/Downloads --exclude=/home/ubuntu/.cache`

The **--exclude** switch is very powerful. It doesn’t take names of directories and files–it actually accepts patterns. There is a lot more you can do with it. 
For example, you could archive an entire directory and exclude all *.mp4* files with the following command:

`tar -czvf archive.tar.gz /home/ubuntu --exclude=*.mp4`


### How to extract data?

