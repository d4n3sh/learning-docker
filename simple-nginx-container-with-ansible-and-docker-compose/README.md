# Simple Nginx container with Ansible and Docker Compose

This playbook will:  

1. copy over the docker-compose.yml file from files/docker-compose.yml to /opt/containers/nginx/docker-compose.yml
2. change ownership of the docker-compose.yml file to uid 1000.  
3. Start the nginx service defined in the compose file.  
  
```bash
ansible-playbook -i 192.168.56.101, run-nginx-compose-container.yml -K

BECOME password: 

PLAY [Create and run a nginx container with docker compose] ****************************************************************

TASK [Gathering Facts] *****************************************************************************************************
ok: [192.168.56.101]

TASK [Setup compose file] **************************************************************************************************
changed: [192.168.56.101]

TASK [Run nginx] ***********************************************************************************************************
changed: [192.168.56.101]

PLAY RECAP *****************************************************************************************************************
192.168.56.101             : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```
