# Basic Unix Command Lines

These command line are very powerful and easy and will be used a lot when you are in Unix-Like operating system

### File
* `ls`: lists your files 
* `ls -l`:  --- lists your files in 'long format', which contains lots of useful information
* `ls -a`: lists all files, including the ones whose filenames begin in a dot
* `more <file>`: shows the first part of a file
* `cat <file> `: show the tails of a file
* `mv <file> <file>`: moves a file (i.e. gives it a different name, or moves it into a different directory
* `cp <file> <file>`: copies a file
* `rm <file>`: remove file
* `wc <file>`: tells you how many lines, words, and characters there are in a file
* `diff <file> <file>`: compares files, and shows where they differ
* `gzip <file>`: compresses files
* `gunzip <file>`: uncompresses files compressed by gzip
* `gzcat <file>`: look at a gzipped file without actually having to gunzip it 
* `split <file>`: split file to files. `split -l 5000 <file>` will split to files which is 5000 lines each 
* `cat <file1> <file2> > <file3>`: combile 2 files together to 1 file
### Directory
* `mkdir <dir>`: create an empty dir
* `cd <dir>`: change directory. You basically 'go' to another directory.
* `pwd`: tells you where you currently are.
* `rm -rf <dir>`: remove the whole dir and files inside
* `sort <file> |uniq |tee <newfile>`: remove duplicated lines
* `sort <file> |uniq -u|tee <newfile>`: remove duplicated lines and remain one for the duplicate lines

### Account
* `w`: tells you who's logged in, and what they're doing. 
* `who`: tells you who's logged on, and where they're coming from.
* `whoami`: returns your username
* `passwd`: lets you change your password,

### Processes
* `kill <PID>`:  kills (ends) the processes with the ID you gave 
* `ps aux`: list all the processes
* `ps -u <username>`: lists your processes

### Others
* `date`: shows the current date and time.
* `cal`: shows a calendar of the current month.
* `which <command>`: show the location for the running command. 
---
* [Stanford.edu - Computing: Basic Unix](http://mally.stanford.edu/~sr/computing/basic-unix.html) 