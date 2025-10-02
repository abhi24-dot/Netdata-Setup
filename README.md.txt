# Netdata Dashboard Setup using Docker on Ubuntu WSL

## Steps I Did:

1. Installed Ubuntu on Windows using WSL.
2. Ran:
   sudo apt update && sudo apt upgrade -y
3. Installed Docker:
   sudo apt install docker.io -y
   sudo systemctl enable --now docker
   docker --version
4. Pulled and ran Netdata:
   sudo docker pull netdata/netdata
   sudo docker run -d --name=netdata -p 19999:19999 \
       --cap-add SYS_PTRACE \
       --security-opt apparmor=unconfined \
       netdata/netdata
   sudo docker ps
5. Opened dashboard in browser: http://localhost:19999

## Notes:
- Initially got error: "Unable to find image 'netdata/netdata:latest' locally".
- Solved by pulling image manually.
