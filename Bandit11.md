# Bandit 11 -> Bandit 12

## Description

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit11@bandit.labs.overthewire.org -p 2220
```
- In the same directory we find a `data.txt`
- Opening the file we'll find that is encoded on rot13.

>Rot13 is a simple cipher that replaces one letter with the corresponding on 13 positions forward on the alfabet.

2. Use `tr` to decode the file
>You could also search rot13 decoder on a navigator.

```bash 
cat data.txt | tr '[G-ZA-Fg-za-f]' '[T-ZA-St-za-s]'
```
---

**Password:** `GROozWPO8QyN0mGrjUkID0WCYkZiQxrN`