<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit11/image.png">

---

## bandit11

````markdown
## Access Information

SSH Portal:
ssh bandit11@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 11 → 12

### Steps to solve
```bash
ls
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
---
<img src="image.png">

---

### explanation

These commands apply a ROT13 transformation to the contents of `data.txt` and output the result:

- `ls` — lists files in the current directory so you can confirm `data.txt` is present.
- `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` — `cat` streams the file contents to `tr`, which performs a ROT13 substitution (A↔N, B↔O, ..., a↔n, etc.). ROT13 is a simple letter substitution cipher often used to obfuscate text.
---
````
