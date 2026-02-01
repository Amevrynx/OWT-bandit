<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit9/image.png">

---

## bandit9

````markdown
## Access Information

SSH Portal:
ssh bandit9@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 9 → 10

### Steps to solve
```bash
ls
strings data.txt | grep '=='
```
---
<img src="image.png">

---

### explanation

These commands extract printable text from `data.txt` and search for lines containing the string `==`:

- `ls` — lists files in the current directory so you can confirm `data.txt` is present.
- `strings data.txt` — extracts printable character sequences from a file (useful when the file contains binary data or non-printable bytes). It outputs sequences of readable characters found in the file.
- `strings data.txt | grep '=='` — pipes the printable strings into `grep`, which filters and prints only lines containing `==`. The `==` token often appears in base64 output as padding or in other encoded markers.

---
````
