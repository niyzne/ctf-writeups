# Natas Level 1 → Level 2

## Challenge Description

``` highlight
Username: natas2
URL: http://natas2.natas.labs.overthewire.org
```

---
## Steps 1

Login to the website:

```
Username: natas2
Password: vsDOxoXyq3wckCP1ZmTZ71ngIA606odB
```

---
## Step 2

![image1](assets/image1.png)

---
## Step 3

![image2](assets/image2.png)

Interesting file found

---
## Step 4

`http://natas2.natas.labs.overthewire.org/files/pixel.png` has not much interesting.

![image3](assets/image3.png)

Just a one pixel dot

---
## Step 5

`http://natas2.natas.labs.overthewire.org/files/`

![image4](assets/image4.png)

Going down a directory reveals `users.txt` alongside `pixel.png`

---
## Step 6

`http://natas2.natas.labs.overthewire.org/files/users.txt`

`users.txt` contains:

```txt
# username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:K30JrSRHzjxq3paUQuwozY4MNvmNFyhI
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```

Password found

---
## Password

```
K30JrSRHzjxq3paUQuwozY4MNvmNFyhI
```
