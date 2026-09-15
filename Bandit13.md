# Bandit 13 -> Bandit 14

## Description
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.
If you need help with this level: a hint file can be found in the home directory.
Make sure to read the error messages as they are informative.

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit13@bandit.labs.overthewire.org -p 2220
```

We encounter a private key on the bandit13s directory.

2. Use it to connect on `localhost`

```bash 
ssh -i sshkey.private bandit14@localhost -p 2220
```
Will result on an error as stated on the description.

3. Copy the private key on client's machine

```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private
```
Or just use ctrl+alt+C

4. Change permissions

```bash
chmod 700 sshkey.private
```

5. Connect via ssh

```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

6. Access the password's file `/etc/bandit_pass/bandit14`

---

**Password:** `aaWecNkG4FhxJQxz07uiwzVP6bJiYS65`