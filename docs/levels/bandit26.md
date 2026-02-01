---
layout: default
title: bandit26
---

## bandit26

````markdown
## Access Information

SSH Portal:
ssh bandit26@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 26 → 27

### Steps to solve
```bash
for this increase the terminal font size to its maximum
then login using the sshkey provided in the previous exercise

when you see the MORE option press "v"

it goes into vi editor, then:

:set shell=/bin/bash
:shell

after getting the shell, use the binary provided to get the password 

./bandit27-do cat /etc/bandit_pass/bandit27
```

<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit26/image.png">

### explanation

This level uses the provided SSH private key to authenticate as `bandit26` and demonstrates a pager→editor→shell escape to obtain an interactive shell.

- SSH key usage:

	- `ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220` — specify the private key with `-i`.
	- Ensure the key file has restrictive permissions: `chmod 600 bandit26.sshkey` (OpenSSH rejects keys that are world-readable).

- Pager → editor → shell escape (how to get a shell from the MORE prompt):

	- When viewing long output you may see a pager prompt like `-- MORE --`. Press `v` to open the pager buffer in the system editor (usually `vi`/`vim`).
	- Inside `vi`, run `:set shell=/bin/bash` to set the shell, then run `:shell` to spawn a subshell (a usable `bash` prompt).
	- From that shell you can run the provided helper binary to read the next password:

		- `./bandit27-do cat /etc/bandit_pass/bandit27` — the helper executes the requested command and prints the password to stdout.

---
````
