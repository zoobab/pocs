# CVE-2019-5736 POC

# Usage
Edit HOST inside `payload.c`, compile with `make`. Start `nc` and run `pwn.sh` inside the container.

# Notes
- This exploit is destructive: it'll overwrite `/usr/bin/docker-runc` binary *on the host* with the
payload. It'll also overwrite `/bin/sh` inside the container.
- Tested only on Debian 9.
- No attempts were made to make it stable or reliable, it's only tested to work when a `docker exec
<id> /bin/sh` is issued on the host.

More complete explanation [here](https://github.com/lxc/lxc/commit/6400238d08cdf1ca20d49bafb85f4e224348bf9d).
