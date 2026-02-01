## Access Information

SSH Portal:
ssh bandit7@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 7 → 8

### Steps to solve
```bash
ls
cat data.txt | grep millionth
            or
grep millionth data.txt

```
---
<img src="image.png">

---

### explanation

The commands show and search the contents of `data.txt` for the line containing the word "millionth":

- `ls` — lists files in the current directory so you can confirm `data.txt` is present.
- `cat data.txt | grep millionth` — `cat` outputs the file contents, the pipe `|` forwards that output to `grep`, and `grep millionth` filters and prints only lines that contain the string `millionth`.

---