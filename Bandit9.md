# Bandit 9 -> Bandit 10

## Description

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit5@bandit.labs.overthewire.org -p 2220
```

- In the same directory we find a `data.txt`
- Opening the file we'll find that is encoded on what seems to be with random characters(a binary).


2. Use `strings`, it allows to take the readable lines from any file.

```bash 
strings data.txt
```
Even though we can already see the password, lets sanitize the result a bit

3. Filter

```bash
strings data.txt | grep "=="
```

**Output**

```bash
======the
======password
======is
======<the password>
```
4. Sanitize

```bash
strings data.txt | grep "==" | tail -n 1 | awk '{print $2}'
```

---

**Password:** `B0s2khmbT9u0geKu0oVGW3JZKhndE3BG`