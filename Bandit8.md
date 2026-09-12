# Bandit 8 -> Bandit 9

## Description

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

## Resolution

- SSH connection
```bash 
sshpass -p '[pass]' ssh bandit8@bandit.labs.overthewire.org -p 2220
```

- In the same directory we find a `data.txt`
- Opening the file we'll find multiple lines with random characters, all seem to be the password.
>As the description says, the line only ocurs once.

1. Use `sort`to make groups of the same lines, using pipes

```bash 
cat data.txt | sort
```

2. Using `uniq` command, we'll get the only non-repeated line
>This command doesn't solely perform that function, which is why a flag is included.

```bash 
cat data.txt | sort | uniq -u
```
We need to use this order so that `uniq` works
---

**Password:** `EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl`