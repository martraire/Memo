## Compress and Extract data
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

### Use bzip2 Compression Instead of gzip
While gzip compression is most frequently used to create *.tar.gz* or *.tgz* files, **tar** also supports **bzip2 compression**. This allows you to create **bzip2-compressed files**, often named **.tar.bz2**, **.tar.bz**, or **.tbz files**. To do so, just replace the `-z` for gzip in the commands here with a `-j` for bzip2.

Gzip is faster, but it generally compresses a bit less, so you get a somewhat larger file. Bzip2 is slower, but it compresses a bit more, so you get a somewhat smaller file. Gzip is also more common, with some stripped-down Linux systems including gzip support by default, but not bzip2 support. In general, though, gzip and bzip2 are practically the same thing and both will work similarly.

For example, instead of the first example we provided for compressing the *stuff directory*, you’d run the following command:

`tar -cjvf archive.tar.bz2 stuff`


### How to extract data?
Once you have an archive, you can extract it with the **tar command**. The following command will extract the contents of *archive.tar.gz* to the current directory.

`tar -xzvf archive.tar.gz`

It’s the same as the archive creation command we used above, except the `-x` switch replaces the `-c` switch. This specifies you want to extract an archive instead of create one.

You may want to extract the contents of the archive to a specific directory. You can do so by appending the `-C` switch to the end of the command. For example, the following command will extract the contents of the *archive.tar.gz* file to the */tmp directory*.

`tar -xzvf archive.tar.gz -C /tmp`

N.B: If the file is a bzip2-compressed file, replace the `-z` in the above commands with a `-j`.

