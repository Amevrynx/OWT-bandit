---
layout: default
title: bandit27
---

## bandit27

````markdown
## Access Information

SSH Portal:
ssh bandit27@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 27 → 28

### Steps to solve
```bash
clone the repo using the given link but add the port after the domain address

git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
cd repo
cat README
```

<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit27/image.png">

### explanation

This level requires cloning a Git repository served over SSH on a non-standard port and reading the `README` file inside the repository:

- Use the provided SSH-accessible Git URL including the port:

    - `git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo`

    The `ssh://user@host:port/path` form lets you specify a custom SSH port for Git to use. Git will use SSH to authenticate as `bandit27-git` and fetch the repository.

- After cloning:

    - `cd repo`
    - `cat README`  # read the repository README which contains the next-level instructions/password
---
````
