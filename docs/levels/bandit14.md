<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit14/image.png">

---

## bandit14

````markdown
## Access Information

SSH Portal:
ssh bandit14@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 14 → 15

### Steps to solve
```bash
ls
nc localhost 30000
```

---
<img src="image.png">

---

### explanation

These steps use `nc` (netcat) to connect to a TCP service running on the local machine:

- `ls` — list files in the current directory so you can confirm where you are and what files are present.
- `nc localhost 30000` — open a TCP connection to `localhost` on port `30000`. `nc` reads from stdin and writes to the socket, and prints data received from the socket to stdout.

What to expect:

- On connecting, the remote service will usually send a prompt or the password; whatever the service writes will appear in your terminal. If the service expects input, you can type and send text to it.
- To exit the connection: press `Ctrl+C` or close the terminal session; some `nc` implementations support `Ctrl+D` or the `-q` option to quit after EOF.
---
````
