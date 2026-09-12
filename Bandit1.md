# Bandit 1 -> Bandit 2

## Description
The password for the next level is stored in a file called - located in the home directory

## Resolution

1. SSH connection

```bash 
sshpass -p '[pass]' ssh bandit1@bandit.labs.overthewire.org -p 2220
```

2. Enumerate directory

```bash 
ls
```
There is only one file called "-"

The problem is that if try to open it normally `cat -`, the file takes the argument as a flag.

3. See content

```bash
cat ./-
```

This command allows to open the file by using the path

---

**Password:** `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB`