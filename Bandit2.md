# Bandit 2 -> Bandit 3

## Description
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

## Resolution

1. SSH connection

```bash 
sshpass -p '[pass]' ssh bandit2@bandit.labs.overthewire.org -p 2220
```

2. Enumerate directory

```bash 
ls
```
This time is the same with "-", but the name has spaces on its name

3. See content

```bash
cat ./--spaces\ in\ this\ filename--
```
This time we are doing the same, but also using `\` to avoid the spaces.

---

**Password:** `7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME`