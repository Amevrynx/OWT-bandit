---
layout: default
title: bandit3
---
---
layout: default
title: bandit3
---

## bandit3

````markdown
## Access Information

SSH Portal:
ssh bandit3@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 3 → 4

### Steps to solve
```bash
ls
cd inhere
ls -la
cat < ...Hiding-From-You

```
---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit3/image.png">

---

### explanation

This level requires navigating into a subdirectory and revealing hidden files before reading the password file. Explanation of the commands used above:

- `ls` — Lists visible files and directories in the current working directory.
- `cd inhere` — Changes into the `inhere` directory where the password file is located.
- `ls -la` — Shows a long listing (`-l`) and includes hidden files (`-a`, files beginning with `.`). Hidden files are common in Linux for configuration or to hide content; `ls` alone will not show them.
- `cat <filename>` — Outputs the contents of `<filename>` to the terminal. Replace `<filename>` with the exact filename shown by `ls -la` (for example, `...Hiding-From-You`). If the filename begins with a dash (`-`), precede it with `./` or use `--` (e.g., `cat ./-` or `cat -- -`) to prevent the shell or command from interpreting it as an option.

---
- `cd inhere` — Changes into the `inhere` directory where the password file is located.
