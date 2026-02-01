<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit12/image.png">
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit12/image2.png">
---

## bandit12

````markdown
## Access Information

SSH Portal:
ssh bandit12@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 12 → 13

### Steps to solve
```bash
ls
mktemp -d
cp data.txt /path/to/tempdir
file data.txt
xxd -r data.txt > data.bin
```
Then proceed according to these screenshots
---
<img src="image.png">
<img src="image2.png">

---

### explanation

This level provides a safe workflow for converting a hex/text representation back into binary and inspecting the result:

- `ls` — confirm `data.txt` is present in the working directory.
- `mktemp -d` — create a temporary directory (prints its path). This avoids working directly in the current directory and prevents accidental overwrites.
- `cp data.txt /path/to/tempdir` — copy `data.txt` into the temporary directory created by `mktemp -d` (use the exact path returned). Working inside a tempdir keeps the workspace clean.
- `file data.txt` — detect the file type. `file` helps determine whether `data.txt` is hex text, ASCII, base64, or already binary.
- `xxd -r data.txt > data.bin` — `xxd -r` reverses a hexdump-like (hexadecimal) representation and writes the raw bytes to `data.bin`. If `data.txt` is plain hex, this reconstructs the original binary.

After `xxd -r`:

- Run `file data.bin` to see what kind of binary was produced (image, archive, executable, compressed stream, etc.).
- If `file` indicates a compressed archive (gzip, tar, etc.), use the appropriate tool to inspect or extract it (e.g., `tar -tzf`, `gunzip`, etc.).
---
````
