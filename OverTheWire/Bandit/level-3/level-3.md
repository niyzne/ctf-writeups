# Bandit Level 3

## Challenge Description

### Level Goal

The password for the next level is stored in a file called `--spaces in this filename--` located in the home directory

``` highlight
host: bandit.labs.overthewire.org
port: 2220
Username: bandit2
Password: PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

URL: https://overthewire.org/wargames/bandit/bandit3.html
```

### Commands you may need to solve this level

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html), [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html), [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html), [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html), [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html), [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
### Helpful Reading Material

- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)

---
## Steps 1

After ssh, `ls`

```txt
bandit2@bandit:~$ ls
--spaces in this filename--
```

## Step 2

Write the full filepath and cat it with quotes on both sides

```txt
bandit2@bandit:~$ pwd
/home/bandit2
bandit2@bandit:~$ cat '/home/bandit2/--spaces in this filename--' 
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
bandit2@bandit:~$ 
```

---
## Password

```txt
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
```
