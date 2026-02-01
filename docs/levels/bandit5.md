---
layout: default
title: bandit5
---

## bandit5

````markdown
## Access Information

SSH Portal:
ssh bandit5@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 5 → 6

### Steps to solve
```bash
ls
cd inhere
ls 
find ./ -type f -size 1033c
cat /path/to/file

```
---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit5/image.png">

---

### explanation

The commands locate a file by exact byte size and display its contents:

- `ls` — Lists visible files and directories.
- `cd inhere` — Change into the `inhere` directory where candidate files reside.
- `find ./ -type f -size 1033c` — Search recursively for regular files (`-type f`) whose size is exactly 1033 bytes; the `c` suffix means size in bytes. The command prints matching path(s).
- next you know what to do

---
````
