## Oracle Cloud

### SSH Configure

To set up SSH agent to avoid retyping passwords, you can do:

$ ssh-agent bash
$ ssh-add ~/.ssh/id_rsa

ref: https://docs.ansible.com/ansible/latest/user_guide/connection_details.html

### To run playbook in dir playbook:

ansible-playbook dev.yml db.yml -i inventory

### To use 

create file all.yml in inventory folder

``---
``all:
``  hosts:
``    dev:
``      hosts: 
``        <ip>
``    db:
``      hosts:
``        <ip>

create file main.yml in vars folder

``user: <user>
``dev_ip: <ip>
``db_ip: <ip>

create files felipeschirmann.dev.br.key and felipeschirmann.dev.br.pem in folder templates/nginx/ssl with public and private keys 