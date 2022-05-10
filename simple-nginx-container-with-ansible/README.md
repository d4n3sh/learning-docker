# Simple Nginx container with Ansible

1. Install Docker SDK for Python

```bash
# sudo dnf install python3-docker
```

2. Install the community Docker collection from Ansible galaxy.

```bash
# ansible-galaxy collection list | grep docker
community.docker              2.4.0

# ansible-galaxy collection install community.docker
Starting galaxy collection install process
...
Installing 'community.docker:2.4.0' to '/Users/danesh/.ansible/collections/ansible_collections/community/docker'
community.docker:2.4.0 was installed successfully
```

3. Run the play

```bash
# ansible-playbook -i 192.168.56.101, run-nginx-container.yml
PLAY [Create and run a nginx container with podman] **********************************************************************************************************

TASK [run nginx] *********************************************************************************************************************************************
ok: [192.168.56.101]

PLAY RECAP ***************************************************************************************************************************************************
192.168.56.101             : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

# docker ps
[danesh@docker-server ~]$ docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                  NAMES
9f407ae8f938   nginx:latest   "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   0.0.0.0:8080->80/tcp   nginx
```