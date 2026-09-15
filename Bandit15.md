# Bandit 15 -> Bandit 16

## Description

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit15@bandit.labs.overthewire.org -p 2220
```

2. Connect to port 30001 using `ncat` on SSL encryption

```bash 
ncat --ssl localhost 30001
```

3. Paste de levels password.

---

**Password:** `kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V`