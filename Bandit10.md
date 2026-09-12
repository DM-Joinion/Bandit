# Bandit 10 -> Bandit 11

## Description

The password for the next level is stored in the file data.txt, which contains base64 encoded data.

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit10@bandit.labs.overthewire.org -p 2220
```

- In the same directory we find a `data.txt`
- Opening the file we'll find that is encoded on base64

2. Use `base64` to decode the file

```bash 
cat data.txt | base64 -d
```
> The flag -d allows to decode the result

---

**Password:** `pYF0Y6HwUsDj5rL9UvyhU7MCmv8vN5Ro`