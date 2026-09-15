# Bandit 14 -> Bandit 15

## Description

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit14@bandit.labs.overthewire.org -p 2220
```

2. Submit to port 30000

```bash 
echo "[pass-bandit-14]" | nc localhost 30000
```
---

**Password:** `pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7`