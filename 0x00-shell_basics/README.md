# Scripts description

In this project we used the commands bellow :

## Task 0. Where am I?
This script prints the absolute path name of the current working directory.

```bash
pwd
```
## Task 1. What’s in there?
This script displays the contents list of your current directory.

```bash
ls
```

## Task 2. There is no place like home
This script changes the working directory to the user’s home directory.

```bash
cd ~
```

## Task 3. The long format
This script displays current directory contents in a long format

```bash
ls -l
```

## Task 4. Hidden files
This script displays current directory contents, including hidden files (starting with .). Use the long format.

```bash
ls -la
```

## Task 5. I love numbers
This script displays current directory contents.

* Long format
* with user and group IDs displayed numerically
* And hidden files (starting with .)

```bash
ls -lan
```

## Task 6. Welcome
This script create a directory named my_first_directory in the /tmp/ directory.

```bash
mkdir /tmp/my_first_directory
```


## Task 7. Betty in my first directory
This script moves the file betty from /tmp/ to /tmp/my_first_directory.

```bash
mv /tmp/betty /tmp/my_first_directory
```



## Task 8. Bye bye Betty
This script delete the file betty.

* The file betty is in /tmp/my_first_directory

```bash
rm /tmp/my_first_directory/betty
```

## Task 9. Bye bye My first directory
This script delete the directory my_first_directory that is in the /tmp directory.

```bash
rm -r /tmp/my_first_directory
```

## Task 10. Back to the future
This script changes the working directory to the previous one.

```bash
cd -
```

## Task 11. Lists
This script is lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the /boot directory (in this order), in long format.

```bash
ls -al . .. /boot
```

## Task 12. File type
This script prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.

```bash
file /tmp/iamafile
```

## Task 13. We are symbols, and inhabit symbols
This script create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory.

```bash
ln -s /bin/ls __ls__
```

## Task 14. Copy HTML files
This script copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.


```bash
cp -un *.html ../
```

## Task 15. Let’s move
This script moves all files beginning with an uppercase letter to the directory /tmp/u.


```bash
mv [[:upper:]]* /tmp/u
```

## Task 16. Clean Emacs
This script deletes all files in the current working directory that end with the character ~.


```bash
rm *~
```

## Task 17. Tree
This script creates the directories welcome/, welcome/to/ and welcome/to/school in the current directory.


```bash
mkdir -p welcome/to/school
```


## Task 18. Life is a series of commas, not periods
This script writes a command that lists all the files and directories of the current directory, separated by commas (,).

* Directory names should end with a slash (/)
* Files and directories starting with a dot (.) should be listed
* The listing should be alpha ordered, except for the directories . and .. which should be listed at the very beginning
* Only digits and letters are used to sort; Digits should come first
* You can assume that all the files we will test with will have at least one letter or one digit
* The listing should end with a new line


```bash
ls -amvp
```

## Task 19. File type: School
This script creates a magic file school.mgc that can be used with the command file to detect School data files. School data files always contain the string SCHOOL at offset 0.

```bash
0 string SCHOOL School data 
!:mime School
```

