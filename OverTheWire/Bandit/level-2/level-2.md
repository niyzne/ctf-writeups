# Bandit Level 2

## Challenge Description

### Level Goal

The password for the next level is stored in a file called **-** located in the home directory

``` highlight
host: bandit.labs.overthewire.org
port: 2220
Username: bandit1
Password: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR


URL: https://overthewire.org/wargames/bandit/bandit2.html
```

### Commands you may need to solve this level

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html), [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html), [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html), [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html), [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html), [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
### Helpful Reading Material

- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](https://linux.die.net/abs-guide/special-chars.html)

---
## Steps 1

exit out from the previous step (might need to do that often)

## Step 2

ssh with `ssh bandit1@bandit.labs.overthewire.org -p 2220` and password from level 1

## Step 3

Find `-` with ls

```txt
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ 
```

## Step 4

Using `cat` on `-` won't do much because it's expecting a command

```txt
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$ 
```

## Step 5

use the file's full path to print the `-` file contents

```txt
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat ~/-
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
bandit1@bandit:~$ 
```

---
## Password

```txt
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
```
