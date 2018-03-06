# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

1. `cwd`: Show path of current working directory.
2. `mkdir` dir_name: Create a directory.
3. `rm -R dir_path`: Delete a directory and contents.
4. `touch file_name`: Create a file.
5. `rm file_path`: Delete a file.
6. `mv orig_name new_name`: Rename a file.
7. `ls -1a | egrep "^\."`: List hidden files.
8. `cp source_path target_path`: Copy a file.
9. `egrep regex file`: Search file for lines matching a regex pattern.
10. `open file`: Opens the file in its default application (at least in MacOS).

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`
`ls -l`
`ls -lh`
`ls -lah`
`ls -t`
`ls -Glp`

1. `ls`: List files in the current working directory.  
2. `ls -a`: List files including hidden files.
3. `ls -l`: List files in long format, one per line.
4. `ls -lh`: List files in long format with human readable file sizes.
5. `ls -lah`: List files in long format with human readable file sizes including hidden files.
6. `ls -t`: List files sorted by time modified.
7. `ls -Glp`: List files in long format using colors with slashes after directory names.

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

1. `ls -1`: List one file name per line.
2. `ls *`: List files and their subdirectories (down one level).
3. `ls *.py`: List only Python source files.
4. `ls -m`: List files as a flat comma separated list.
5. `ls -R`: List files recursively.

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

It breaks apart standard input using space, newline, and tab characters as delimiters. Then it uses the resulting strings as the arguments to the given utility. If there are too many arguments for one call, it will call the utility multiple times.

An example could be something like `find . -name \*.png | xargs rm`, which would recursively delete .png files. This would only work if their names didn't contain spaces. It looks like some versions of `xargs` support a `-d` flag that allows you to override the delimiter, but the version of `xargs` I have on my Mac doesn't support the `-d` flag. (Passing `-delete` or `-exec rm {} +` to `find` would probably be a better way to do this anyway.)



 

