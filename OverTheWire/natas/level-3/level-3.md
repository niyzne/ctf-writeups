# Natas Level 2 → Level 3

## Challenge Description

``` highlight
Username: natas3
URL: http://natas3.natas.labs.overthewire.org
```

---
## Steps 1

Login to the website:

```
Username: natas3
Password: K30JrSRHzjxq3paUQuwozY4MNvmNFyhI
```

---
## Step 2

`http://natas3.natas.labs.overthewire.org`

![image1](assets/image1.png)

Not even google can find. They say

---
## Step 3

`http://natas3.natas.labs.overthewire.org/robots.txt`

```txt
User-agent: *
Disallow: /s3cr3t/
```

`robots.txt` has led to a interesting discovery


---
## Step 4

`http://natas3.natas.labs.overthewire.org/s3cr3t/`

![image2](assets/image2.png)

Nice, another directory found, with another `users.txt`

---
## Step 5

`http://natas3.natas.labs.overthewire.org/s3cr3t/users.txt`

```txt
natas4:JDrPnuZAKyl6MkiqQGFIddrqpvgOASth
```

Password found

---
## Password

```
JDrPnuZAKyl6MkiqQGFIddrqpvgOASth
```

---
