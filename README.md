# Ansible Role: psdash

[![Build Status](https://travis-ci.org/robgmills/ansible-psdash.svg?branch=master)](https://travis-ci.org/robgmills/ansible-psdash)

Installs [psdash](https://github.com/Jahaja/psdash) on a Debian-based distro.

This role installs and configures the latest version of [psdash](https://github.com/Jahaja/psdash) via pip.

## Requirements (on host that executes the role)

* virtualenv
* pip

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

None.

## Dependencies

None.

## Example Playbook

    - hosts: server
      roles:
        - role: robgmills.psdash

## Try It!

From the root of the project:

    vagrant up

...then...

    ansible-playbook -i inventory -b -u vagrant -k playbook.yml

...then use your favorite browser to connect to `http://192.168.50.30:5000`

## License

MIT / BSD

## Author Information

This role was created in 2016 by [Rob Mills](https://robgmills.com/).

[vault]: http://docs.ansible.com/ansible/playbooks_vault.html
