# Shell, permissions

This is a manual description of some scripts and permissions in shell.

## Task 0. My name is Betty

This script switches the current user to the user `betty`.

```bash
su betty
```

## Task 1. Who am I

This script prints the effective username of the current user.

```bash
whoami
```


## Task 2. Groups

This script prints all the groups the current user is part of.

```bash
groups
```

## Task 3. New owner

This script changes the owner of the file hello to the user `betty`.

```bash
sudo chown betty hello
```

## Task 4. Empty!

This script creates an empty file called `hello`.

```bash
touch hello
```


## Task 5. Execute

This script adds execute permission to the owner of the file `hello`.
* The file `hello` will be in the working directory

```bash
chmod u+x hello
```

## Task 6. Multiple permissions

This script adds execute permission to the owner and the group owner, and read permission to other users, to the file `hello`.
* The file `hello` will be in the working directory

```bash
chmod u+x,g+x,o+r hello
```


## Task 7. Everybody!

This script adds execution permission to the owner, the group owner and the other users, to the file `hello`.
* The file `hello` will be in the working directory
* You are not allowed to use commas for this script

```bash
chmod u+x,g+x,o+r hello
```

## Task 8. James Bond

This script sets the permission to the file `hello`.
* Owner: no permission at all
* Group: no permission at all
* Other users: all the permissions
* The file `hello` will be in the working directory
* You are not allowed to use commas for this script

```bash
chmod 007 hello
```



## Task 9. John Doe

This script sets the mode of the file `hello` to this :
```bash
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
```
* The file `hello` will be in the working directory
* You are not allowed to use commas for this script

```bash
chmod 753 hello
```




## Task 10. Look in the mirror

This script sets the mode of the file `hello` the same as `olleh`'s mode :
```bash
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
```
* The file `hello` will be in the working directory
* The file `olleh` will be in the working directory

```bash
chmod --reference=olleh hello
```




## Task 11. Directories

This script adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.


```bash
chmod -R ugo+X .
```


## Task 12. More directories

This script creates a directory called `my_dir` with permissions 751 in the working directory.


```bash
mkdir -m 751 my_dir
```

## Task 13. Change group

This script changes the group owner to `school` for the file `hello`
* The file `hello` will be in the working directory


```bash
chgrp school hello
```

## Task 14. Owner and group

This script changes the owner to `vincent` and the group owner to `staff` for all the files and directories in the working directory.


```bash
chown -hR vincent:staff .
```



## Task 15. Symbolic links

This script changes the owner and the group owner of `_hello` to `vincent` and `staff` respectively.
* The file `_hello` is in the working directory
* The file `_hello` is a symbolic link

```bash
chown -h vincent:staff _hello
```

## Task 16. If only

This script changes the owner of the file `hello` to `betty` only if it is owned by the user `guillaume`.

* The file `hello` will be in the working directory
```bash
chown --from=guillaume betty hello
```


## Task 17. Star Wars

This script will play the StarWars IV episode in the terminal.

```bash
telnet towel.blinkenlights.nl
```
