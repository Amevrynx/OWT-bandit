<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit20/image.png">
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit20/image2.png">

### explanation
## bandit20

````markdown
## Access Information

SSH Portal:
ssh bandit20@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 20 → 21

### Steps to solve
```bash
ls
nc -l 12345

now on another ssh instance

./suconnect 12345
```
---
<img src="image.png">
<img src="image2.png">

### explanation

This level demonstrates a local network/listener workflow: one process opens a TCP listener with `nc` and another process (here `./suconnect`) connects to it to forward or exchange data.

- `nc -l 12345` — start a TCP listener on port `12345` that prints whatever it receives to stdout. Note: some `nc` implementations require `nc -l -p 12345` instead; check your `nc` version if the command fails.

- In another SSH session on the same machine, run `./suconnect 12345` — this program connects to the listener at port `12345` and forwards data between its stdin/stdout and the listener socket. In this challenge the helper is designed to connect and allow you to receive the password output produced by the listening side.

workflow:

- Terminal A: run the listener to wait for an inbound connection and capture output:

	- `nc -l 12345 > output.txt`  # save whatever the connector sends

- Terminal B (another SSH session): run the connector that connects to the listener and triggers the remote action:

	- `./suconnect 12345`  # connects back to the listener; the helper may read a file and send its contents over the socket

- After the connector runs, inspect `output.txt` or the listener terminal to see the transmitted data (the password).
---
````
