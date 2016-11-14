# Bootstrap a nodejs server

[![Build Status](https://travis-ci.org/NicolasRitouet/ansible-playbooks.svg?branch=master)](https://travis-ci.org/NicolasRitouet/ansible-playbooks)

> This ansible playbook will secure a new server, install a few utilities and nvm/node on it.

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

```bash
ansible-galaxy install jdauphant.nginx
ansible-playbook playbook.yml -u root -K
```

## Make it yours

- modify the email and the password in `vars/main.yml`
- change the public keys in `vars/ssh-public-key.yml`
- change the node version you want to install in `vars/nvm.yml`
- add your server IPs in `hosts`
- `ansible-playbook bootstrap.yml -u root -K`

## Requirements

- Ansible

## TODO

- add letsencrypt tasks

## Credits

https://plusbryan.com/my-first-5-minutes-on-a-server-or-essential-security-for-linux-servers


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details