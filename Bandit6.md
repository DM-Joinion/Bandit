# Bandit 6 -> Bandit 7

## Description

The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

## Resolution

- For this resolution we won't be needing more steps than a one-linner that searches by the properties specified:

In this case the file is not on users directory, therefore we must search from the root `\`. To avoid filling the terminal with error messages, direct `stderr` to /dev/null so it doesn't show.

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
- Then open de file and take the pass

--- 
## Note

Using `xargs` with pipes we can open the file directly

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null | xargs cat
```
---

**Password:** `Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3`