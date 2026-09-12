# Bandit 4 -> Bandit 5

## Description
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

## Resolution

1. SSH connection

```bash 
sshpass -p '[pass]' ssh bandit3@bandit.labs.overthewire.org -p 2220
```

2. Enumerate and access the directory `inhere`

3. While enumerating this directory we encounter many files

Only one of all the files is "human readable". 
To see the type of a file, we can use the command `file`.

4. Enumerate file types

Instead of going file for file, using '*' we can refer to every file on the directory.

```bash
file ./* #Use "./" to avoid the -fileXX format
```
```
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: OpenPGP Public Key
./-file07: ASCII text
./-file08: data
./-file09: Motorola S-Record; binary data in text format
```

--- 

## note

We could also use a one liner

```bash
find . -type f | grep "/-file" | xargs file
``` 

from the start

---

**Password:** `6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG`