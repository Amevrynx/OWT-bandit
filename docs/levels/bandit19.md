<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit19/image.png">

### explanation

## bandit19

````markdown
## Access Information

SSH Portal:
ssh bandit19@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 18 → 19

### Steps to solve
```bash
ls
./bandit20-do cat /etc/bandit_pass/bandit20
```
---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit19/image.png">

### explanation

This level uses a local helper binary (`bandit20-do`) that runs a requested command (here `cat /etc/bandit_pass/bandit20`) and prints the result. The typical invocation is:

- `./bandit20-do cat /etc/bandit_pass/bandit20` — the helper executes `cat /etc/bandit_pass/bandit20` on your behalf and outputs the password to stdout.

What this means:

- The helper uses setuid privilages so it can read files you normally cannot. It accepts a command and path and runs them with the helper's privileges.
---
````
