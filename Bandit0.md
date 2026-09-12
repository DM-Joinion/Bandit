# Bandit 0 -> Bandit 1

## Description
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Resolution

1. SSH connection

```bash 
sshpass -p 'bandit0' ssh bandit0@bandit.labs.overthewire.org -p 2220
```

2. Enumerate directory

```bash 
ls
```

There only is one file called "readme"

3. See content

```bash
cat readme
```
---

**Password:** `6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR`


