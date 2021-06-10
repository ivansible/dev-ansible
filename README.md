# ivansible.dev_ansible

[![Github Test Status](https://github.com/ivansible/dev-ansible/workflows/test/badge.svg?branch=master)](https://github.com/ivansible/dev-ansible/actions)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-ivansible.dev__ansible-68a.svg?style=flat)](https://galaxy.ansible.com/ivansible/dev_ansible/)


This role will install ansible in a virtual environment under user
home directory (as described in the
[installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-pip)),
put links to ansible binaries in the `~/bin` link directory
and add this directory on path in the user profile.


## Requirements

None


## Variables

Available variables are listed below, along with default values.

    dev_ansible_dir: ~/.ansible/venv

Directory with ansible virtual environment

    dev_ansible_link_dir: ~/bin

Directory to put links to ansible binaries

    dev_ansible_update_bashrc: true

Allows to add link directory on the local profile

    dev_ansible_python: python3

Python version to use for ansible: `python` or `python3`.

    dev_ansible_apply_patches: true
This flag enables patching ansible, mitogen and molecule:
  - molecule patch adds support for `MOLECULE_TARGET` environment variable
  - ansible restconf patch fixes the "JSON object must be str" error on xenial
  - mitogen patch fixes the "pending work still existed after shutdown" warning on micro-servers


## Tags

- `dev_ansible_install` -- setup virtual environment and install ansible
- `dev_ansible_upgrade` -- upgrade old ansible 2.8 pre-installed on vagrant
- `dev_ansible_patch` -- apply patches to ansible, mitogen and molecule
- `dev_ansible_links` -- create links to ansible binaries
- `dev_ansible_bashrc` -- update path in the local profile
- `dev_ansible_syslog` -- configure syslog for ansible and mitogen
- `dev_ansible_all` -- all of above


## Dependencies

None


## Example Playbook

    - hosts: vag2
      roles:
        - role: ivansible.dev_ansible


## License

MIT


## Author Information

Created in 2018-2021 by [IvanSible](https://github.com/ivansible)
