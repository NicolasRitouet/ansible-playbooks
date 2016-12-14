# Bootstrap a nodejs server

[![Build Status](https://travis-ci.org/NicolasRitouet/ansible-playbooks.svg?branch=master)](https://travis-ci.org/NicolasRitouet/ansible-playbooks)

> This repo contains 3 ansible playbooks, one to secure a bare server, one to install node/nginx and one for redis

:hand: This playbook has only been tested with Ubuntu 16.04 aka Xenial64.

## Details

- create a user (`deploy`) with sudo rights
- add specified public ssh keys
- disallow root login
- disallow password authentication
- install utilities
- install ufw and set it up
- install  and setup postfix and logwatch
- install nvm and node 7 as default
- install global node packages
- install and setup nginx


## Getting started

### Secure playbook

This playbook will secure a bare server by doing the following:

- install ufw, fail2ban and logwatch (daily email send to specified email address)
- create a new user
- deactivate root login
- deactivate login with password
- add specified ssh public key in authorized_keys

:warning: because we deactivate login password, make sure that your ssh public key is given in the vars (`vars/ssh-public-key.yml`) to be able to login

```bash
ansible-playbook secure.yml -u root
```

### Node playbook

- install nvm
- install node using nvm
- install nginx

```bash
ansible-galaxy install jdauphant.nginx
ansible-playbook node.yml -u deploy


### Redis playbook

```bash
ansible-galaxy install DavidWittman.redis
ansible-playbook redis.yml -u deploy
```

## Requirements

- Ansible

## TODO

- add letsencrypt tasks

## Credits

https://plusbryan.com/my-first-5-minutes-on-a-server-or-essential-security-for-linux-servers


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details