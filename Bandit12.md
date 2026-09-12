# Bandit 12 -> Bandit 13

## Description

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Resolution

1. SSH connection
```bash 
sshpass -p '[pass]' ssh bandit12@bandit.labs.overthewire.org -p 2220
```
- When opening the file, we'll see a bunch of letters and numbers lined up.

This letters are hexadecimal and thier representation on the right side.

The first characters on hexadecimal are the "Magic Numbers" and identify the tipe of file we're dealing with.

- Copy the content of "data.txt" on your machine.

2. Change the hexadecimal text into a binary

```bash 
cat data | xxd -r | sponge data

```
`xxd` to decode hexadecimal.
`sponge` for writing over the files original info without breaking it.

3. Use file to see info on the binary

```bash
file data
```
It says is a compresed file called "data2.bin" on a gzip, and some other info.
> Now you could either search for each extensions tool, but using 7z usually works for every compressed file.

4. change the files extension
```bash
cp data data.gz
```

5. Decompressor Script

```bash 
#!/bin/bash

function ctrl_c() {
    echo -e "\n\n[+] Ending script...\n"
    exit 1
}

trap ctrl_c INT

filename=$1
toDecompress=$(7z l $filename | tail -n 3 | head -n 1 | awk 'NF{print $NF}')
7z x $filename &>/dev/null

while [ "$toDecompress" ]; do
    echo -e "[+] File decompressed: $toDecompress"
    7z x "$toDecompress" &>/dev/null
    toDecompress=$(7z l "$toDecompress" | tail -n 3 | head -n 1 | awk 'NF{print $NF}')
done
```
---

**Password:** `qQYQiHOBPR8zR61qxYqX45quvihF2uzk`