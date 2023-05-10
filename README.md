## Oracle Cloud

### SSH Configure

To set up SSH agent to avoid retyping passwords, you can do:

```
$ ssh-agent bash
$ ssh-add ~/.ssh/id_rsa
```

ref: https://docs.ansible.com/ansible/latest/user_guide/connection_details.html

### Include hostnames in /etc/hosts
add in /etc/hosts
```
[ip]  dev
[ip]  db
```

### To run playbook in dir playbook:

```
ansible-playbook dev.yml db.yml -i inventory
```

#### note: in mac ansible 6.6.0 > the message is encountered
Ansible: Unsupported parameters for (ansible.legacy.command) module: warn
fix:
```
brew install ansible@6
```
refs:
https://stackoverflow.com/questions/74544930/ansible-unsupported-parameters-for-ansible-legacy-command-module-warn
https://medium.com/nerd-for-tech/install-old-versions-of-apps-with-ansible-and-homebrew-9ba612fa6679

### To use 

#### create file all.yml in inventory folder

```
---
all:
  hosts:
    dev:
      hosts: 
        <ip>
    db:
      hosts:
        <ip>
```

#### create file main.yml in vars folder

```
user: <user>
dev_ip: <ip>
db_ip: <ip>
```

#### create files felipeschirmann.dev.br.key and felipeschirmann.dev.br.pem in folder templates/nginx/ssl with public and private keys 

### Check Ingress Rules to redirect subdomain to ports only of ngnix

### Root certificate Cloudfare
https://developers.cloudflare.com/ssl/origin-configuration/origin-ca/#4-required-for-some-add-cloudflare-origin-ca-root-certificates
