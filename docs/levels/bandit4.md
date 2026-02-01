---
layout: default
title: bandit4
---
---
layout: default
title: bandit4
---

## bandit4

````markdown
## Access Information

SSH Portal:
ssh bandit4@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 4 → 5

### Steps to solve
```bash
ls
cd inhere
ls 
file ./-file*
        or
strings ./-file*

```
---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit4/image.png">

---

### explanation

- `ls` — Lists visible files and directories in the current directory.
- `cd inhere` — Change into the `inhere` directory where the target file is located.
- `ls` (or `ls -la`) — Use `ls -la` to see hidden files and full details; many challenges place files with odd names or permissions that are not obvious with a plain `ls`.
- `file ./-file*` — The `file` command inspects the file type. Because the filename begins with `-`, prefix with `./` (or use `--`) so the shell treats it as a pathname rather than an option. The glob `-file*` matches files starting with `-file`.
- `strings ./-file*` — If `file` indicates a binary or non-text file, `strings` extracts printable text sequences which often reveal hidden passwords embedded in binaries.

Reading the file:

- If `file` reports a plain text file, use `cat ./-file` (or `cat -- -file`) to output its contents.
- If the filename contains spaces or special characters, quote it: `cat "./my file"` or escape characters with backslashes.
---
````

