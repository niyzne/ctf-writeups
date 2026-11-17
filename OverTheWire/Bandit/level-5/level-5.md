# Bandit Level 5

## Challenge Description

### Level Goal

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

``` highlight
host: bandit.labs.overthewire.org
port: 2220
Username: bandit4
Password: xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq

URL: https://overthewire.org/wargames/bandit/bandit5.html
```

### Commands you may need to solve this level

[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html), [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html), [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html), [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html), [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html), [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

---
## Step 1

navigating to `inhere` will present multiple files `-file0{0..9}`

```txt
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
```

## Step 2

One of the ways to read each file at once is with `cat *` and since these files have a `-` you will need to use `--` to indicate that all arguments after that are filenames

and so. `cat -- *` can be used to read all the files at once

```txt
bandit4@bandit:~/inhere$ cat -- *
����f�Gy���}��nS��2����[a�����fݡkK����Vʁ�3)��h�,����c����;�
�J�ç�����t1ht����@���9
                      f�;��t��X�
p���i~���C��Eh�3�6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG7�k�?g*�g�H|�7�#n�4�`�,���ĳ�PC��I7
fU�^��ʩq,�W�M���M�ÿ@ЬD^V�H�<qQ[Q�΄���6:�
                                        ���}bandit4@bandit:~/inhere$ 
bandit4@bandit:~/inhere$ 
```

---
## Password

```txt
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
```
