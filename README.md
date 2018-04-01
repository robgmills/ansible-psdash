# Ansible Role: psdash

[![Build Status](https://travis-ci.org/robgmills/ansible-psdash.svg?branch=master)](https://travis-ci.org/robgmills/ansible-psdash)

Installs [psdash](https://github.com/Jahaja/psdash) on a Debian-based distro.

This role installs and configures the latest version of [psdash](https://github.com/Jahaja/psdash) via pip.

## Requirements (on host that executes the role)

* systemd

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    psdash_port: 5000

The port that psdash should listen on.

    psdash_mode: web

The operating mode for psdash.  Should be one of `web` or `agent`.  If `agent`, you must specify a `psdash_master` variable.

    psdash_master: undefined

The URL for the psdash node running in `web` mode - i.e. `http://10.0.0.1:5000`

    psdash_config: ""

The configuration values for psdash.  It supports all [configuration options available to psdash](https://github.com/Jahaja/psdash#configuration).  For example, to change the URL prefix that psdash responds at to `/psdash` use the following config:

    psdash_config: |
      PSDASH_URL_PREFIX='/psdash'

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
