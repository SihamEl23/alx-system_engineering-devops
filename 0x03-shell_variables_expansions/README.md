# 0x03. Shell, init files, variables and expansions

In this project we used for each task those scripts :

## Task 0. <o>

This script creates an alias.
* Name: ls
* Value: rm *

```bash
alias ls="rm *"
```

## Task 1. Hello you

This script prints `hello user`, where user is the current Linux user.

```bash
echo "hello $USER"
```

## Task 2. The path to success is to take massive, determined action

This script add `/action` to the `PATH`. `/action` should be the last directory the shell looks into when looking for a program.

```bash
PATH=$PATH:/action
```

## Task 3. If the path be beautiful, let us not ask where it leads

This script counts the number of directories in the `PATH`.

```bash
echo $PATH | tr ':' '\n' | wc -l
```

## Task 4. Global variables

This script lists environment variables.

```bash
printenv
```


## Task 5. Local variables

This script lists all local variables and environment variables, and functions.

```bash
set
```


## Task 6. Local variable

This script creates a new local variable.

* Name: `BEST`
* Value: `School`

```bash
BEST="School"
```

## Task 7. Global variable

This script creates a new global variable.

* Name: `BEST`
* Value: `School`

```bash
export BEST="School"
```



## Task 8. Every addition to true knowledge is an addition to human power

This script prints the result of the addition of 128 with the value stored in the environment variable `TRUEKNOWLEDGE`, followed by a new line.


```bash
echo $((128 + $TRUEKNOWLEDGE))
```


## Task 9. Divide and rule 

This script prints the result of `POWER` divided by `DIVIDE`, followed by a new line.

* `POWER` and `DIVIDE` are environment variables


```bash
echo $((POWER/DIVIDE))
```



## Task 10. Love is anterior to life, posterior to death, initial of creation, and the exponent of breath

This script displays the result of `BREATH` to the power `LOVE`
* `BREATH` and `LOVE` are environment variables
* The script should display the result, followed by a new line


```bash
echo $((BREATH**$LOVE))
```



## Task 11. There are 10 types of people in the world -- Those who understand binary, and those who don't

This script converts a number from base 2 to base 10.

* The number in base 2 is stored in the environment variable `BINARY`
* The script should display the number in base 10, followed by a new line


```bash
echo $((2#$BINARY))
```


## Task 12. Combination

This script prints all possible combinations of two letters, except `oo`.

* Letters are lower cases, from `a` to `z`
* One combination per line
* The output should be alpha ordered, starting with `aa`
* Do not print `oo`
* Your script file should contain maximum 64 characters

```bash
echo {a..z}{a..z} |tr ' ' '\n' | grep -v "oo"
```





## Task 13. Floats

This script prints a number with two decimal places, followed by a new line.

* The number will be stored in the environment variable `NUM`.

```bash
printf '%.2f\n' $NUM
```



## Task 14. Decimal to Hexadecimal

This script converts a number from base 10 to base 16.

* The number in base 10 is stored in the environment variable `DECIMAL`
* The script should display the number in base 16, followed by a new line

```bash
printf '%x\n' $DECIMAL
```


## Task 15. Everyone is a proponent of strong encryption

This script encodes and decodes text using the rot13 encryption. Assume ASCII.


```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m'
```


## Task 16. The eggs of the brood need to be an odd number

This script prints every other line from the input, starting with the first line.


```bash
paste -d, - - | cut -d, -f1
```


## Task 17. I'm an instant star. Just add water and stir.

This script adds the two numbers stored in the environment variables `WATER` and `STIR` and prints the result.

* `WATER` is in base `water`
* `STIR` is in base `stir`.
* The result should be in base `bestchol`


```bash
printf "%o\n" $(( $((5#$(echo $WATER | tr water 01234))) + $((5#$(echo $STIR | tr stir. 01234))) )) | tr 01234567 bestchol
```

