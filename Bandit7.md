# Bandit 7 -> Bandit 8

## Description

The password for the next level is stored in the file data.txt next to the word millionth

## Resolution

- SSH connection
```bash 
sshpass -p '[pass]' ssh bandit7@bandit.labs.overthewire.org -p 2220
```

We find a file called `data.txt`. 

- Open the file using pipes with grep on the word "millionth".

```bash 
cat data.txt | grep "millionth"
```
The password comes next to the word millionth.

---

**Password:** `VR1ljMayciFxbnUokuQmJFw6QC9VKtub`