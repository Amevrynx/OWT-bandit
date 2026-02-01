## Access Information

SSH Portal:
ssh bandit1@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

---


## Level 1 → 2

### Objective
Log in via SSH and retrieve the password for the next level.


### Steps to solve
```bash
ls
cat ./-
```
---
<img src="image.png">

---

### explanation

- `ls`  lists the subfiles
- in this exercise the file itself is named `-` which gets treated as a command/execution flag like in `ls -la`
- so using `cat` like `cat ./-` allows it to treat it like an individual file instead of a flag

### explanation

- `ls` lists files in the directory
- in this exercise the file itself is named `-` which can be interpreted as an option/flag by commands (e.g., `ls -la`)
- to read a file named `-` use `cat ./-` or `cat -- -` so the filename is treated as a pathname instead of an option
---