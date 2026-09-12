# Bandit 5 -> Bandit 6

## Description

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:


    human-readable
    1033 bytes in size
    not executable


## Resolution

- For this resolution we won't be needing more steps than a one-linner that searches by the properties specified:

```bash
find . -type f -readable -size 1033c ! -executable
```

- Then open the file and take the pass

--- 

## Note

Using `xargs` with pipes we can open the file directly

```bash
find . -type f -readable -size 1033c ! -executable | xargs cat
```

---

**Password:** `pXa26xhMWaC2SvDotA4r9EgZkulOeSBW`