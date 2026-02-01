## Access Information

SSH Portal:
ssh bandit31@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 31 → 32

### Steps to solve
```bash
clone the repo using the given link but add the port after the domain address

git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo
cat README

echo "May I come in?" > key.txt
# Option A: edit .gitignore to allow .txt files (e.g. remove or comment out the "*.txt" line)
#   nano .gitignore
# Option B: force-add the file without changing .gitignore
git add -f key.txt
git commit -m "add key"
git push -u origin main

```

### explanation

This level requires adding a `key.txt` file to the repository and pushing it back to the remote. The remote repo is writable for your SSH key user; once `key.txt` is pushed the server-side hook/README will reveal the next password.

- Clone using the provided SSH URL and port (adjust user/host/path if different):

    - `git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo`

- Typical workflow to add and push the key:

    - `cd repo`
    - `echo "May I come in?" > key.txt`
    - If `.gitignore` prevents adding `*.txt` files, either edit it (e.g. `nano .gitignore`) to remove/comment that line, or force-add:
      - `git add -f key.txt`
    - `git commit -m "add key"`
    - `git push -u origin main`
    
---