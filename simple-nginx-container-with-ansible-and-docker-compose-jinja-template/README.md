# Simple Nginx container with Ansible and Docker Compose

This playbook will:  

1. Assign values to varibles to be used in the jinja2 template file in step 2.
2. Copy over the docker-compose.yml.j2 jinja2 template file from files/docker-compose.yml.j2 to /opt/containers/nginx/docker-compose.yml
3. Create application directory /opt/containers/nginx/
4. Change ownership of the docker-compose.yml file to uid 1000.  
5. Start the nginx service defined in the compose file.  
  
```bash
ansible-playbook -i 192.168.56.101, run-nginx-compose-container.yml -K
BECOME password: 

PLAY [Create and run a nginx container with docker compose generated with Jinja2] ******************************************

TASK [Create application directory] ****************************************************************************************
ok: [192.168.56.101]

TASK [Setup compose file] **************************************************************************************************
changed: [192.168.56.101]

TASK [Run nginx] ***********************************************************************************************************
ok: [192.168.56.101]

PLAY RECAP *****************************************************************************************************************
192.168.56.101             : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
