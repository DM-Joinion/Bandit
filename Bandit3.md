# Bandit 3 -> Bandit 4

## Description
The password for the next level is stored in a hidden file in the inhere directory.

## Resolution

1. SSH connection

```bash 
sshpass -p '[pass]' ssh bandit3@bandit.labs.overthewire.org -p 2220
```

2. Enumerate directory

```bash 
ls
```
Directory called `inhere`

3. Access directory + enumerate

```bash 
cd inhere
#Then
ls
```

There is nothing shown on the directory

4. Enumerate with `ls + flags`

```bash
ls -a
```
The flag `-a`allows to see hiden files, which results in a file `...Hiding-From-You`

Open the file and take the pass.

---

**Password:** `xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq`