---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit17/image.png">

### explanation

## bandit17

````markdown
## Access Information

SSH Portal:
ssh bandit17@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 17 → 18

### Steps to solve
```bash
ls
diff passwords.old passwords.new
```
---
<img src="image.png">

### explanation

This level compares two password snapshot files and highlights the differences so you can find the new password entry.

- `diff passwords.old passwords.new` — compares the two files line-by-line and prints the differences. By default, `diff` marks lines present only in the first file with `<` and lines present only in the second file with `>`.

How to interpret `diff` output:

- A line starting with `>` indicates it exists in `passwords.new` but not in `passwords.old` — this is typically where a newly added password will appear.
- Conversely, a line starting with `<` exists only in `passwords.old`.

Commands to extract the added password(s):

- Print lines that appear in `passwords.new` but not in `passwords.old`:

    - `grep -Fxv -f passwords.old passwords.new`  # prints lines unique to `passwords.new`

- Use a unified diff for cleaner context:

    - `diff -u passwords.old passwords.new`
````
