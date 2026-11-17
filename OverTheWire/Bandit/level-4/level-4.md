# Bandit Level 4

## Challenge Description

### Level Goal

The password for the next level is stored in a hidden file in the **inhere** directory.

``` highlight
host: bandit.labs.overthewire.org
port: 2220
Username: bandit3
Password: 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

URL: https://overthewire.org/wargames/bandit/bandit4.html
```

### Commands you may need to solve this level

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html), [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html), [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html), [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html), [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html), [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

---
## Step 1

`ls` and then `ls inhere/` and we notice that, it returns nothing

```txt
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ ls inhere/
bandit3@bandit:~$
```

## Step 2

`ls -la` to see more file contents

```txt
bandit3@bandit:~$ ls -la inhere/
total 12
drwxr-xr-x 2 root    root    4096 Oct 25 13:37 .
drwxr-xr-x 3 root    root    4096 Oct 25 13:37 ..
-rw-r----- 1 bandit4 bandit3   33 Oct 25 13:37 ...Hiding-From-You
```

## Step 3

`cat` the hidden file

```txt
bandit3@bandit:~$ cat ~/inhere/...Hiding-From-You 
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
bandit3@bandit:~$ 
```

---
## Password

```txt
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
```
